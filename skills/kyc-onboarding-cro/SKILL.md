---
name: kyc-onboarding-cro
description: KYC and identity-verification funnel optimization for B2C neobanks. Auto-triggers when working on signup completion, identity verification drop-off, document capture flows, or activation rate. Maps drop-off by KYC stage and prescribes intervention by drop mode.
argument-hint: "[funnel stage data, vendor in use, ICP segment]"
user-invocable: true
disable-model-invocation: false
---

# KYC and Onboarding CRO

## Why this exists (first principles)

KYC drop-off is the largest single CAC sink in B2C neobanking. CAC for a US consumer pre-KYC runs $150-400 between paid acquisition, referral incentive, and welcome bonus. A 40% KYC abandonment rate means 40% of acquisition spend produces zero retained customers. The funnel does not just leak revenue, it leaks the most expensive part of the funnel.

The numbers:

- **Fenergo 2025 study**: 67% of global banks experience KYC abandonment as a material problem.
- **Signicat European fintech research**: 63% of European consumers have abandoned a fintech signup specifically due to identity verification friction.
- **Same Signicat data**: 38% of abandoners said they did not have their documents ready. 21% said the process took too long.
- **Industry benchmarks**: B2C neobank KYC completion rates run 40-70%. Top quartile is 75%+.

Generic onboarding-CRO frameworks miss this. The failure modes here are identity-verification specific. You cannot fix a low-light selfie rejection with a better empty-state illustration. The intervention must match the drop mode.

## The KYC funnel: 5 stages, 5 drop modes

Every B2C neobank funnel collapses to these stages. Map your analytics to them before doing anything else.

**Stage 1: Personal info entry** (name, DOB, SSN or last 4, address)
- Drop signal: high field-level abandonment, especially on SSN.
- Drop cause: field bloat, trust deficit, no explanation of why SSN is needed.

**Stage 2: Document upload** (government ID front and back)
- Drop signal: capture started, never completed, or rejected on submit.
- Drop cause: ID not at hand, expired ID, glare, blur, vendor rejection of valid ID.

**Stage 3: Selfie / liveness check**
- Drop signal: started, abandoned mid-capture, or rejected.
- Drop cause: low light, glasses, mask, demographic bias in the vendor's model.

**Stage 4: Bank link or initial deposit**
- Drop signal: completed identity, never funded.
- Drop cause: Plaid friction, no eligible external bank, second auth step, mistrust of micro-deposits.

**Stage 5: Card activation / digital wallet add**
- Drop signal: funded but never transacted.
- Drop cause: physical card delay (5-10 business days), no virtual card surfaced, Apple Pay / Google Pay add not prompted.

## Drop-mode-specific tactics

### Document at-hand problem

The single highest-leverage intervention in the whole funnel. 38% of abandoners (per Signicat) drop because they do not have their ID handy.

Fix:
- **Pre-flight question** on the screen before document upload: "Do you have a valid government ID handy right now?" with a "Save and resume later" path that emails a magic link.
- **Email reminder cadence**: T+2 hours, T+24 hours, T+7 days. Top-quartile abandoned-application recovery rates run 15-25% with this cadence.
- **Mobile push fallback** if app installed: T+2 hours, T+24 hours.
- **Friction reduction**: do not require login to resume. Magic link straight back into the exact step the user left.

### Low-light or rejected selfie

Real-time coaching copy on the capture screen, not after rejection:
- "Move to a brighter spot. Window light works best."
- "Take off your glasses for this photo."
- "Hold the phone at eye level."

After a single rejection, **retry, do not restart**. Burning a user back to step 1 of a 5-step funnel after a selfie fail is the worst pattern in this category. Allow 3 retries. After the third, route to manual review with a clear "we will review this within 24 hours" message and an email confirmation.

Vendor demographic bias is real. Test rejection rates by self-reported race, age, and gender of internal testers and friends-and-family. If rejection rates skew, escalate to vendor and consider a second vendor for fallback.

### Name mismatch handling

Mandatory: never auto-reject. Required cases:
- Recent immigrants whose ID name does not match address records.
- Married women with name changes not yet fully propagated.
- Trans users with chosen names where ID has not yet been updated.
- Users with hyphenated, compound, or non-Latin names that vendor parsers mishandle.

Required flow: human review path with target SLA (24 hours), email confirmation, and a status page the user can check. Do not silently fail. Auto-rejection of these cohorts is both an ECOA exposure (disparate impact on protected class) and a brand exposure (these users post about it).

### SSN-only vs full-document path

Some vendors and partner banks support SSN-only verification (no government ID required). Lower friction by 30-50% but higher fraud risk and limited to certain product types.

Use SSN-only when:
- Product is low risk (savings only, no card, no instant transfer).
- Partner bank's risk team has approved it for the program.
- Fraud loss is below threshold for the cohort.

Do not use SSN-only when:
- Product includes credit, instant transfer, or P2P at scale.
- ICP is high-fraud-risk (bonus harvesters, certain referral programs).

### Bank link friction (Stage 4)

Plaid is industry standard but not free of friction. ~10-15% of US consumers either do not have an eligible external bank or refuse to link via OAuth.

Fallback path: manual ACH (routing + account number) with verifying micro-deposits. Slower (1-3 days) but recovers the segment Plaid loses. Always offer both, default to Plaid.

### Card activation delay (Stage 5)

Issue a virtual card immediately upon KYC pass. Surface it on the home screen with a "Add to Apple Pay" or "Add to Google Pay" CTA before the physical card arrives. Activation rate jumps materially (Chime, Cash App, Current all do this).

## Vendor selection

Top US KYC vendors for B2C neobanks:

- **Persona**: flexible, developer-friendly, good UX. Pricing: $1.50-3 per verification depending on volume and add-ons. Strong recovery UX.
- **Jumio**: enterprise legacy, broad geographic coverage, slower latency. Pricing: $2-4 per verification.
- **Onfido (Entrust)**: strong document and biometric, decent API. Pricing: $2-4 per verification.
- **Socure**: data-first (SSN, address, device), lower friction for US, strong fraud signal. Pricing: per-check, varies.

Selection criteria, in order:
1. **Demographic accuracy**: ask each vendor for false-rejection rates by race and age cohort. If they cannot share, that is the answer.
2. **Recovery UX**: how does a rejected user retry without restart?
3. **Latency**: P95 verification time. Anything over 30 seconds compounds drop-off.
4. **Price per verification at projected volume**.
5. **Partner bank approval**: your partner bank may have a pre-approved list. Check first.

## Output format

When this skill runs, produce a KYC funnel audit:

```
KYC FUNNEL AUDIT: [brand] | [date]

CURRENT FUNNEL
  Stage 1 personal info: [start] -> [completed] = X%
  Stage 2 document upload: [start] -> [completed] = X%
  Stage 3 selfie: [start] -> [completed] = X%
  Stage 4 fund / link: [start] -> [completed] = X%
  Stage 5 card active: [start] -> [completed] = X%
  Total signup -> active: X%

BENCHMARK GAP
  Top quartile B2C target: 75%+ signup -> active.
  Gap to close: X percentage points.

DROP MODE DIAGNOSIS
  Largest leak: Stage [N] at X% drop.
  Hypothesized cause: [field bloat / at-hand / lighting / vendor / Plaid / card delay].

INTERVENTION MAP
  Priority 1: [specific tactic from drop-mode section]
  Priority 2: [...]
  Priority 3: [...]

VENDOR REVIEW
  Current: [vendor]
  Issue: [false rejection rate / latency / recovery UX]
  Recommend: [keep / negotiate / replace]

EXPECTED LIFT
  Conservative: +X percentage points completion.
  Implied CAC reduction: $X per acquired customer.
```

## Compliance and human review

This skill produces drafts, not legal artifacts. Every output must be reviewed by qualified compliance counsel and your partner bank's marketing review team before publishing. Specifically check: BSA (31 USC 5311 et seq.), CIP rule (31 CFR 1020.220), OFAC sanctions screening requirements, ECOA (15 USC 1691) and note that KYC variance must not correlate with protected class, FCRA (15 USC 1681) if any third-party data check is involved. This pack does not constitute legal advice and Growgami is not liable for outputs.
