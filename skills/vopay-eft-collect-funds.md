---
name: Collect funds by EFT (Canada)
description: Pull funds from a customer's Canadian bank account by EFT and confirm settlement, with idempotency and webhook confirmation.
api: openapi/vopay-payment-rails-api-reference.json
operations: [AuthPingPost, EftFundPost, EftFundStatusGet, EftFundTransactionGet]
---

# Collect funds by EFT (Canada)

Use this skill to debit a Canadian bank account via VoPay's EFT rail (funding direction).

## Auth
Every call needs `AccountID`, `Key`, and a `Signature = SHA1(Key + SharedSecret + YYYY-MM-DD)`.
See `authentication/vopay-authentication.yml`. The signature is only valid for the current
calendar day. In sandbox, use your sandbox keys from https://vopay.com/api-sandbox/.

## Steps
1. **Verify connectivity + credentials** — `AuthPingPost` (`/auth/ping`). Confirm `Success:true`.
2. **Initiate the EFT debit** — `EftFundPost` (`/eft/fund`). Supply the bank-account `Token` (or
   financial institution / transit / account number), `Amount`, `Currency`, and a
   `ClientReferenceNumber`. **Always pass a unique `IdempotencyKey`** so a retried request
   returns the original transaction instead of creating a duplicate (see
   `conventions/vopay-conventions.yml`).
3. **Record the `TransactionID`** from the response.
4. **Poll status** — `EftFundStatusGet` (`/eft/fund/status`) or fetch full detail with
   `EftFundTransactionGet`. Do not poll aggressively; prefer the webhook below.
5. **Confirm via webhook** — subscribe to the `transaction` event
   (`asyncapi/vopay-webhooks-asyncapi.yml`). Verify each payload with
   `ValidationKey = SHA1(SharedSecret + TransactionID)` before trusting it.

## Errors & returns
- API-level failures come back as HTTP 200 with `Success:false` + `ErrorCode`
  (`errors/vopay-error-codes.yml`) — e.g. `3001` transaction limit exceeded, `3000` rail not enabled.
- A returned EFT surfaces a 9xx return code (`errors/vopay-decline-codes.yml`) — e.g. `901` NSF,
  `905` account closed, `912` invalid account number.

## Sandbox testing
The cents portion of `Amount` drives the simulated outcome: `.01–.09` immediate failure,
`.60–.99`/integers settle successfully (`sandbox/vopay-sandbox.yml`).
