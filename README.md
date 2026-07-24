# VoPay (vopay)

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
