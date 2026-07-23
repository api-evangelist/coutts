---
name: Retrieve account and transaction information (AIS)
description: Set up an account-access consent, obtain PSU authorisation, then read a Coutts customer's accounts, balances and transactions through the OBIE Account and Transaction Information API.
api: openapi/coutts-account-info-openapi.yaml
method: generated
generated: '2026-07-23'
operations:
  - CreateAccountAccessConsents
  - GetAccountAccessConsentsConsentId
  - GetAccounts
  - GetAccountsAccountIdBalances
  - GetAccountsAccountIdTransactions
---

# Retrieve account and transaction information (AIS)

Coutts is an ASPSP on NatWest Group's Bank of APIs. Only an FCA-authorised AISP with an OBIE/eIDAS certificate can call this API. All requests go to the mutual-TLS gated gateway host `api.coutts.com` under `/open-banking/v3.1/aisp` and must carry the FAPI headers `x-fapi-interaction-id`, `x-fapi-auth-date` and `x-fapi-customer-ip-address`.

## Steps

1. **Get a client-credentials token.** Authenticate as the TPP (`TPPOAuth2Security`, `client_credentials`, scope `accounts`) over mutual TLS to obtain an access token for the consent operations.
2. **Create the consent** — `CreateAccountAccessConsents`. POST the `Permissions` you need (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`) plus optional `ExpirationDateTime`. The response returns a `ConsentId` with `Status: AwaitingAuthorisation`.
3. **Redirect the PSU for SCA.** Send the customer through the `PSUOAuth2Security` `authorization_code` flow (OIDC hybrid) so they authorise the consent with strong customer authentication. This upgrades the consent to `Status: Authorised`.
4. **Confirm the consent** — `GetAccountAccessConsentsConsentId` to verify `Status: Authorised` before reading data.
5. **List accounts** — `GetAccounts` returns the `AccountId`(s) covered by the consent.
6. **Read balances / transactions** — `GetAccountsAccountIdBalances` and `GetAccountsAccountIdTransactions`. Page transactions with `?page=N` and filter with `fromBookingDateTime`/`toBookingDateTime`; follow `Links.Next` until absent.

## Rules

- Requested data must fall within the granted `Permissions` or the ASPSP returns `UK.OBIE.Resource.ConsentMismatch`.
- Reads are idempotent GETs — no `x-idempotency-key`.
- Errors use the OBIE `OBErrorResponse1` envelope (see `errors/coutts-problem-types.yml`); correlate support cases via the `x-fapi-interaction-id` echoed as `Id`.
