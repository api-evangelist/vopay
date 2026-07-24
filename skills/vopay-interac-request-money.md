---
name: Request money by Interac e-Transfer
description: Send an Interac e-Transfer money request to a Canadian individual or business and track collection to settlement.
api: openapi/vopay-payment-rails-api-reference.json
operations: [AuthPingPost, InteracMoneyRequestPost, InteracMoneyRequestTransactionGet, InteracMoneyRequestTransactionsCancelPost]
---

# Request money by Interac e-Transfer

Use this skill to collect funds in near real time via Interac e-Transfer "Request Money".

## Auth
Standard VoPay auth: `AccountID` + `Key` + `Signature = SHA1(Key + SharedSecret + YYYY-MM-DD)`
(`authentication/vopay-authentication.yml`).

## Steps
1. **Confirm credentials** — `AuthPingPost` (`/auth/ping`).
2. **Send the money request** — `InteracMoneyRequestPost` (`/interac/money-request`). Supply the
   recipient email/phone, `Amount`, `Currency`, and a `ClientReferenceNumber`. Pass a unique
   `IdempotencyKey` to avoid duplicate requests (`conventions/vopay-conventions.yml`).
3. **Record the `TransactionID`** from the response.
4. **Track status** — `InteracMoneyRequestTransactionGet` (`/interac/money-request/transaction`),
   or wait for the `transaction` webhook (`asyncapi/vopay-webhooks-asyncapi.yml`), verifying
   `ValidationKey = SHA1(SharedSecret + TransactionID)`.
5. **Cancel if needed** — `InteracMoneyRequestTransactionsCancelPost`
   (`/interac/money-request/transactions/cancel`) while the request is still pending.

## Errors & returns
API errors: HTTP 200 with `Success:false` + `ErrorCode` (`errors/vopay-error-codes.yml`).
Declines/returns surface a 9xx return code (`errors/vopay-decline-codes.yml`), e.g. `988`
Paylink declined by receiver.

## Sandbox
Outcome is driven by the cents portion of `Amount` (`sandbox/vopay-sandbox.yml`).
