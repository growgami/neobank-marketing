---
name: udaap-review
description: UDAAP pre-publish review for every consumer-facing claim. Auto-triggers when neobank copy is being drafted or finalized. Catches deceptive, unfair, or abusive claims before they ship.
argument-hint: "[copy to review, channel, product context]"
user-invocable: true
disable-model-invocation: false
---

# UDAAP Pre-Publish Review

## Why this exists (first principles)

CFPB UDAAP enforcement is the single largest fine category for consumer fintech. The math is simple: a missed review costs mid-six to low-seven figures.

Real enforcement, real dollars:

- **Chime, May 7 2024**: $4.55M CFPB civil money penalty for delayed refunds to closed-account customers. Consent order required restitution and process changes.
- **Chime / Sendwave, October 18 2023**: Sendwave (Chime acquired) hit with CFPB action including $1.5M penalty over deceptive "instant" transfer claims and fee disclosures. Pattern: speed claims that did not hold up under load.
- **Beam Financial, March 2021**: FTC banned founder Yinan Du from operating financial products for life. Beam claimed "24/7 access" and "FDIC insured" while customers could not withdraw funds for months.
- **FDIC Q1-Q2 2024 enforcement wave**: cease-and-desist letters to multiple fintechs misrepresenting deposit insurance status post-Synapse collapse.

Every claim that ships without this review is a coin flip on six figures.

## When to run this

Auto-run before any consumer-facing copy is published. That includes: landing page copy, paid ad creative, push notifications, transactional and lifecycle email, in-app banners, app store listings, social posts, support macros, and creator briefs.

## The 7-pass checklist

Run every pass. Mark pass / fail / rewrite.

### Pass 1: Banned word scan

Cross-check every line against `reference/banned-words.md`. Catch the obvious traps: "free" without footnote, "guaranteed," "FDIC insured" without partner bank, "instant," "best APY," "risk-free," "no fees," "0% fees forever."

Output: list every banned phrase found with line reference.

### Pass 2: Substantiation log

Every quantitative claim needs a source on file. "Save $300 a year" needs the methodology document. "5x faster" needs the benchmark. "Trusted by 1M users" needs the dated active-user count.

Output: claim / source / source date. Flag any claim without a substantiation row.

### Pass 3: Comparison fairness

Every competitor claim must be from the competitor's own published disclosure as of a specific date. Pulling APY from a screenshot taken six months ago is a UDAAP exposure.

Output: comparison / competitor source URL / date pulled. Anything older than 30 days needs refresh.

### Pass 4: Disclosure adequacy

Required footnotes present? Sized at minimum 8pt or platform equivalent? Color contrast meets WCAG AA against background? Disclosure within reasonable proximity to the claim it qualifies?

Output: claim / matched disclosure / proximity / size and contrast check.

### Pass 5: Dark pattern audit

Kill on sight:

- Fake countdown timers
- Hidden or low-contrast close buttons
- Pre-checked opt-in boxes for marketing, data sharing, or paid features
- False scarcity ("only 4 spots left" without inventory truth)
- Drip disclosure (revealing fees only after signup)
- Roach motel flows (easy to subscribe, hard to cancel)
- Confirmshaming ("No thanks, I hate saving money")

Output: pattern / location / kill or fix.

### Pass 6: Channel-specific check

- **App store (Apple, Google)**: financial app rules require accurate descriptions of FDIC status, fees, and rate disclosures in the listing itself, not buried in the app.
- **Meta and Google paid ads**: financial services is a special-category vertical. Targeting limits, mandatory disclosures, and prohibited claims (returns, get-rich language) apply at the ad-account level.
- **Email**: CAN-SPAM. Working unsubscribe, accurate from line, physical address, no deceptive subject lines.
- **SMS**: TCPA. Express written consent for marketing texts, opt-out instructions in every message, quiet hours.

Output: channel / requirement / pass or fail.

### Pass 7: Regulator screenshot test

Imagine the claim screenshotted and dropped into a CFPB consent order without surrounding context. Would it survive? If the answer is "only with the disclaimer," the disclaimer is doing too much work. Rewrite the claim.

Output: pass or rewrite. Include the rewrite.

## Output format

```
UDAAP REVIEW: [asset name] | [channel] | [date]

PASS 1 BANNED WORDS: [pass / N issues]
  Line X: "phrase" (see banned-words.md row Y). Rewrite: "..."

PASS 2 SUBSTANTIATION: [pass / N missing]
  Claim: "..." | Source: [doc or missing]

[continue through Pass 7]

VERDICT: SHIP / FIX / KILL
REQUIRED FIXES:
  1. ...
  2. ...
ESCALATE TO COMPLIANCE COUNSEL: yes / no / specific items
```

## Compliance and human review

These skills have not been reviewed by banking compliance counsel. Treat all output as a starting point only.

This skill produces drafts, not legal artifacts. Every output must be reviewed by qualified compliance counsel and your partner bank's marketing review team before publishing. Specifically check: CFPB UDAAP (12 USC 5531 and 5536), FTC Section 5, state UDAP statutes. This pack does not constitute legal advice and Growgami is not liable for outputs.
