---
name: Verify a bank account with IQ11
description: Instantly verify and tokenize a customer's bank account using VoPay's IQ11 embedded experience, then read balance/ownership data.
api: openapi/vopay-iq11.json
operations: [Iq11GenerateEmbedUrlPost, Iq11TokenInfoGet, Iq11BalanceGet, Iq11EnrichDataPOST, Iq11EnrichDataStatusGet]
---

# Verify a bank account with IQ11

Use this skill to run instant bank-account verification and tokenization via IQ11.

## Auth
Standard VoPay auth: `AccountID` + `Key` + `Signature = SHA1(Key + SharedSecret + YYYY-MM-DD)`
(`authentication/vopay-authentication.yml`).

## Steps
1. **Generate the embed URL** — `Iq11GenerateEmbedUrlPost` (`/iq11/generate-embed-url`). Returns a
   hosted iFrame URL. Embed it in your app (`components/vopay-components.yml`); the customer
   selects their institution and authenticates. In sandbox a fictitious "VoPay Bank" is shown.
2. **Receive the token** — on completion VoPay fires the `bankaccount` webhook carrying the
   bank-account `Token` and account details. Verify `ValidationKey = SHA1(SharedSecret + Token)`.
3. **Read token info** — `Iq11TokenInfoGet` (`/iq11/token-info`) for institution / account holder.
4. **Check balance (optional)** — `Iq11BalanceGet` (`/iq11/balance`) for real-time balance.
5. **Enrich (optional)** — `Iq11EnrichDataPOST` then poll `Iq11EnrichDataStatusGet` for KYC/data
   enrichment on the connected account.

## Result
Use the returned `Token` as the payment method for subsequent EFT/Interac transactions
(`skills/vopay-eft-collect-funds.md`).

## Errors
Failures return HTTP 200 with `Success:false` + `ErrorCode` (`errors/vopay-error-codes.yml`).
