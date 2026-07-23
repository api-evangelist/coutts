# Coutts (coutts)

Coutts & Co is a British private bank and wealth manager founded in 1692, a wholly owned subsidiary of NatWest Group (a UK CMA9 banking group). As an FCA-authorised Account Servicing Payment Service Provider (ASPSP), Coutts participates in UK Open Banking under PSD2, exposing its Read/Write APIs through NatWest Group's "Bank of APIs" developer platform. Those APIs conform to the Open Banking Implementation Entity (OBIE) Read/Write Standard and are secured with FAPI OAuth2/OIDC, mutual-TLS and PSD2 strong customer authentication.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/coutts/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/coutts/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Private Bank
- Wealth Management
- Open Banking
- PSD2
- OBIE
- FAPI
- Payments
- Account Information
- United Kingdom

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Coutts Account and Transaction Information API

OBIE Read/Write Account and Transaction Information (AIS) API for Coutts, letting FCA-authorised AISPs retrieve account, balance, transaction, party, standing order, direct debit, beneficiary, product and statement data with customer consent. Secured with FAPI OAuth2/OIDC, mTLS and PSD2 SCA.

- **Human URL:** [https://www.bankofapis.com/products/coutts-open-banking](https://www.bankofapis.com/products/coutts-open-banking)
- **Base URL:** `https://api.coutts.com/open-banking/v3.1/aisp`

#### Tags

- Account Information
- AIS
- Open Banking

#### Properties

- [OpenAPI](openapi/coutts-account-info-openapi.yaml) — OBIE Read/Write Account & Transaction standard spec
- [Documentation](https://www.bankofapis.com/products/coutts-open-banking)
- [API Reference](https://www.bankofapis.com/documentation)

### Coutts Payment Initiation API

OBIE Read/Write Payment Initiation (PIS) API for Coutts, letting FCA-authorised PISPs initiate domestic, scheduled, standing-order, international and file payments on behalf of the account holder. Secured with FAPI OAuth2/OIDC, mTLS and PSD2 SCA.

- **Human URL:** [https://www.bankofapis.com/products/coutts-open-banking](https://www.bankofapis.com/products/coutts-open-banking)
- **Base URL:** `https://api.coutts.com/open-banking/v3.1/pisp`

#### Tags

- Payment Initiation
- PIS
- Payments

#### Properties

- [OpenAPI](openapi/coutts-payment-initiation-openapi.yaml) — OBIE Read/Write Payment Initiation standard spec
- [Documentation](https://www.bankofapis.com/products/coutts-open-banking)
- [API Reference](https://www.bankofapis.com/documentation)

### Coutts Confirmation of Funds API

OBIE Read/Write Confirmation of Funds (CBPII) API for Coutts, letting authorised Card Based Payment Instrument Issuers check whether sufficient funds are available before a transaction. Secured with FAPI OAuth2/OIDC, mTLS and PSD2 SCA.

- **Human URL:** [https://www.bankofapis.com/products/coutts-open-banking](https://www.bankofapis.com/products/coutts-open-banking)
- **Base URL:** `https://api.coutts.com/open-banking/v3.1/cbpii`

#### Tags

- Confirmation of Funds
- CBPII
- Open Banking

#### Properties

- [OpenAPI](openapi/coutts-confirmation-funds-openapi.yaml) — OBIE Read/Write Confirmation of Funds standard spec
- [Documentation](https://www.bankofapis.com/products/coutts-open-banking)
- [API Reference](https://www.bankofapis.com/documentation)

### Coutts Open Data API

OBIE Open Data API publishing PUBLIC, unauthenticated reference data for Coutts commercial/business current account products, following the Open Banking Open Data Standard. As a private bank Coutts runs no retail ATM/branch network, so it publishes product reference data rather than ATM/Branch locator data. The exact live open-data URL was not confirmed unauthenticated (the api.coutts.com gateway is mutual-TLS gated).

- **Human URL:** [https://www.bankofapis.com/products/coutts-open-banking](https://www.bankofapis.com/products/coutts-open-banking)
- **Base URL:** `https://api.coutts.com/open-banking/v2.3/business-current-accounts`

#### Tags

- Open Data
- Business Current Accounts
- Open Banking

#### Properties

- [Documentation](https://www.bankofapis.com/products/coutts-open-banking)
- [API Reference](https://documenter.getpostman.com/view/35240/TVCiUmZV)

## Common Properties

- [Website](https://www.coutts.com/)
- [Developer Portal](https://www.bankofapis.com/products/coutts-open-banking)
- [Documentation](https://www.bankofapis.com/documentation)
- [Sandbox](https://developer.coutts.useinfinite.io/)
- [GitHub Organization](https://github.com/bankofapis)
- [LinkedIn](https://www.linkedin.com/company/coutts-and-co)
- [Blog](https://www.coutts.com/insights.html)
- [Support](https://www.coutts.com/help-centre.html)
- [Status Page](https://www.bankofapis.com/performance/service-interruptions)
- [Terms of Service](https://www.coutts.com/important-information.html)
- [Privacy Policy](https://www.coutts.com/privacy-and-cookie-policy.html)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
