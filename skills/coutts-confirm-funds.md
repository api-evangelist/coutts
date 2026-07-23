---
name: Confirm available funds (CBPII)
description: Establish a funds-confirmation consent, obtain PSU authorisation, then check whether sufficient funds exist on a Coutts account through the OBIE Confirmation of Funds API.
api: openapi/coutts-confirmation-funds-openapi.yaml
method: generated
generated: '2026-07-23'
operations:
  - CreateFundsConfirmationConsents
  - GetFundsConfirmationConsentsConsentId
  - CreateFundsConfirmations
---

# Confirm available funds (CBPII)

Only an authorised Card Based Payment Instrument Issuer (CBPII) with an OBIE/eIDAS certificate can call this API, over the mutual-TLS gated `api.coutts.com` gateway under `/open-banking/v3.1/cbpii`. Send the standard FAPI headers on every request.

## Steps

1. **Get a client-credentials token** — `TPPOAuth2Security` (`client_credentials`, scope `fundsconfirmations`) over mutual TLS.
2. **Create the funds-confirmation consent** — `CreateFundsConfirmationConsents`. POST `Data.DebtorAccount` (the account to be checked) and optional `ExpirationDateTime`. The response returns a `ConsentId` with `Status: AwaitingAuthorisation`.
3. **Redirect the PSU for SCA** — `PSUOAuth2Security` `authorization_code` flow so the account holder authorises the standing funds-confirmation consent; it becomes `Status: Authorised`.
4. **Confirm the consent** — `GetFundsConfirmationConsentsConsentId` to verify `Status: Authorised`.
5. **Check funds** — `CreateFundsConfirmations` with the `ConsentId` and an `InstructedAmount`/currency. The response `Data.FundsAvailableResult.FundsAvailable` is a boolean; no monetary balance is disclosed.

## Rules

- The consent is a standing authorisation — repeat `CreateFundsConfirmations` calls reuse the same authorised `ConsentId` until it expires or is revoked.
- The API returns only a yes/no funds indicator, never the account balance.
- Errors use the OBIE `OBErrorResponse1` envelope (see `errors/coutts-problem-types.yml`).
