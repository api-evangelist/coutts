---
name: Initiate a domestic payment (PIS)
description: Register a domestic payment consent, obtain PSU authorisation, then execute and track a single immediate domestic payment through the Coutts OBIE Payment Initiation API.
api: openapi/coutts-payment-initiation-openapi.yaml
method: generated
generated: '2026-07-23'
operations:
  - CreateDomesticPaymentConsents
  - GetDomesticPaymentConsentsConsentId
  - CreateDomesticPayments
  - GetDomesticPaymentsDomesticPaymentId
---

# Initiate a domestic payment (PIS)

Only an FCA-authorised PISP with an OBIE/eIDAS certificate can call this API, over the mutual-TLS gated `api.coutts.com` gateway under `/open-banking/v3.1/pisp`. Payment writes require the FAPI headers plus a detached JWS signature (`x-jws-signature`) and support idempotent replay via `x-idempotency-key`.

## Steps

1. **Get a client-credentials token** — `TPPOAuth2Security` (`client_credentials`, scope `payments`) over mutual TLS.
2. **Create the payment consent** — `CreateDomesticPaymentConsents`. POST `Data.Initiation` (debtor/creditor accounts, `InstructedAmount`, `RemittanceInformation`) with an `x-jws-signature` over the body. The response returns a `ConsentId` with `Status: AwaitingAuthorisation`.
3. **Redirect the PSU for SCA** — `PSUOAuth2Security` `authorization_code` flow so the account holder authorises the specific payment with strong customer authentication; the consent moves to `Status: Authorised`.
4. **(Optional) confirm funds** — `GetDomesticPaymentConsentsConsentIdFundsConfirmation` to check funds availability before execution.
5. **Execute the payment** — `CreateDomesticPayments`, referencing the authorised `ConsentId`, echoing the identical `Initiation`, sending `x-jws-signature`, and setting a unique `x-idempotency-key` (max 40 chars) so a retry replays rather than duplicates.
6. **Track status** — `GetDomesticPaymentsDomesticPaymentId` and poll `Data.Status` (`AcceptedSettlementInProcess` → `AcceptedSettlementCompleted`).

## Rules

- The `Initiation` in `CreateDomesticPayments` must be byte-consistent with the consent, or the ASPSP rejects it.
- Reuse the same `x-idempotency-key` on any retry (OBIE retains it at least 24 hours) to guarantee exactly-once execution.
- Late submissions return `UK.OBIE.Rules.AfterCutOffDateTime`; signature problems return `UK.OBIE.Signature.*` (see `errors/coutts-problem-types.yml`).
