# VoPay (vopay)

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

VoPay is a Vancouver, Canada based fintech offering an API-first embedded finance and payments-as-a-service platform that lets software companies, marketplaces, lenders, and enterprises move money across Canadian and North American bank rails from a single set of REST endpoints. Its Fintech-as-a-Service suite spans EFT, Interac e-Transfer, ACH, RTP/FedNow/FedWire, VoPay Instant, card and digital-wallet payments, cross-border and global cash management, virtual accounts, ledgering, scheduled and recurring payments, bank-account verification (IQ11), KYC/AML onboarding, and dispute management.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/vopay/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/vopay/refs/heads/main/apis.yml)

## Tags

- Payments
- Canada
- Embedded Finance
- Payments as a Service
- Account-to-Account
- EFT
- Interac e-Transfer
- ACH
- Real-Time Payments
- Cross-Border
- Money Transfer
- Bank Account Verification
- KYC
- Virtual Accounts
- Open Banking

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## API Posture

VoPay ships a genuine, self-serve developer portal at [docs.vopay.com](https://docs.vopay.com/) (a ReadMe.io hub, project `vopay-api` v2.0) with a sandbox, an OpenAPI-backed API reference segmented by product, an `llms.txt` agent index, and webhooks. The API is REST over HTTPS: all methods accept HTTP POST form-encoded parameters and return JSON. Requests authenticate with an API key plus a shared secret, sending a `SHA1(apiKey + sharedSecret + date)` signature, and only whitelisted IP addresses are accepted.

Twenty-three (23) OpenAPI 3.0 definitions were harvested verbatim from the ReadMe hub (`https://docs.vopay.com/openapi/<filename>.json`) and saved under [`openapi/`](openapi/). Base URL declared across the specs is the sandbox host `https://earthnode-dev.vopay.com/api/v2`.

## APIs

Each product area below maps to a harvested OpenAPI definition in `openapi/`.

- **Payment Rails API** — EFT, Interac e-Transfer, ACH, RTP and related rails (85 paths) — [`openapi/vopay-payment-rails-api-reference.json`](openapi/vopay-payment-rails-api-reference.json)
- **Payment Methods API** — bank accounts, cards, wallets and payment method management (51 paths) — [`openapi/vopay-payment-method-api-reference.json`](openapi/vopay-payment-method-api-reference.json)
- **Accounts API** — account balances, funding, transfers and ledger (40 paths) — [`openapi/vopay-account-api-reference.json`](openapi/vopay-account-api-reference.json)
- **Client Accounts API** — sub/client account management (40 paths) — [`openapi/vopay-client-accounts.json`](openapi/vopay-client-accounts.json)
- **Global Cash Management API** — cross-border and treasury cash management (35 paths) — [`openapi/vopay-global-cash-management.json`](openapi/vopay-global-cash-management.json)
- **Integrations and Support API** — integration and support operations (32 paths) — [`openapi/vopay-integrations-and-support.json`](openapi/vopay-integrations-and-support.json)
- **Contact API** — contacts and recipients (15 paths) — [`openapi/vopay-contact.json`](openapi/vopay-contact.json)
- **Verification API** — identity and account verification (13 paths) — [`openapi/vopay-verification.json`](openapi/vopay-verification.json)
- **Dispute Management API** — disputes and chargebacks (11 paths) — [`openapi/vopay-dispute-management-api-reference.json`](openapi/vopay-dispute-management-api-reference.json)
- **Account Onboarding API** — KYC/AML onboarding (9 paths) — [`openapi/vopay-account-onboarding.json`](openapi/vopay-account-onboarding.json)
- **Bill Pay API** — bill payments (8 paths) — [`openapi/vopay-bill-pay-references.json`](openapi/vopay-bill-pay-references.json)
- **File Conversion API** — file utilities (8 paths) — [`openapi/vopay-file-conversion-api-reference.json`](openapi/vopay-file-conversion-api-reference.json)
- **IQ11 API** — bank account verification (7 paths) — [`openapi/vopay-iq11.json`](openapi/vopay-iq11.json)
- **Transaction Management API** — transaction reporting (7 paths) — [`openapi/vopay-transaction-management.json`](openapi/vopay-transaction-management.json)
- **Branding API** — white-label branding (6 paths) — [`openapi/vopay-branding-api-reference.json`](openapi/vopay-branding-api-reference.json)
- **Scheduled Payments API** — scheduled/recurring payments (5 paths) — [`openapi/vopay-scheduled-payments-api-reference.json`](openapi/vopay-scheduled-payments-api-reference.json)
- **Virtual Accounts API** — virtual accounts (5 paths) — [`openapi/vopay-virtual-account-api-reference.json`](openapi/vopay-virtual-account-api-reference.json)
- **Blocked Accounts API** — risk/compliance blocking (3 paths) — [`openapi/vopay-blocked-accounts-api-reference.json`](openapi/vopay-blocked-accounts-api-reference.json)
- **eLinx API** — eLinx payment link technology (3 paths) — [`openapi/vopay-elinx.json`](openapi/vopay-elinx.json)
- **Ping API** — health/utility (3 paths) — [`openapi/vopay-ping.json`](openapi/vopay-ping.json)
- **Convenience Fees API** — convenience fee handling (2 paths) — [`openapi/vopay-convenience-fee-api-reference.json`](openapi/vopay-convenience-fee-api-reference.json)
- **Payments API** — payments endpoint (1 path) — [`openapi/vopay-payment-api-reference.json`](openapi/vopay-payment-api-reference.json)
- **Remittance API** — remittance (1 path) — [`openapi/vopay-remittance-api-reference.json`](openapi/vopay-remittance-api-reference.json)

## Common Properties

- [Website](https://vopay.com/)
- [Developer Portal](https://docs.vopay.com/)
- [Documentation](https://docs.vopay.com/docs/api-overview)
- [API Reference](https://docs.vopay.com/reference/getting-started-with-your-api)
- [Getting Started](https://docs.vopay.com/docs/getting-started)
- [Sign Up / Sandbox](https://vopay.com/api-sandbox/)
- [Status Page](https://status.vopay.com/)
- [Pricing](https://vopay.com/pricing/)
- [Blog](https://blog.vopay.com/)
- [Support](https://vopay.com/contact/)
- [Terms of Service](https://vopay.com/legal/term-of-use/)
- [Privacy Policy](https://vopay.com/legal/privacy-policy)
- [LinkedIn](https://www.linkedin.com/company/vopay)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
