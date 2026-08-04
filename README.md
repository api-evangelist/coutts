# Coutts (coutts)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
