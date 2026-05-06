---
name: bank-aso
description: App Store and Google Play optimization for B2C neobanks. Triggers when auditing a finance-app listing, writing screenshots/title/subtitle copy, planning In-App Events, or handling 1-star fraud complaint reviews.
argument-hint: "[neobank app name + store + audit goal]"
user-invocable: true
disable-model-invocation: false
---

# Bank ASO

## Why this exists (first principles)

B2C neobanks are mobile-first with near-zero branch discovery. After referrals, the App Store and Google Play are the largest acquisition surface a neobank has. A user searching "banking app" or "no fee checking" on an iPhone is in the highest-intent state they'll ever be in.

Finance category is a knife fight. Chime, Dave, Current, Varo, Cash App, SoFi, Revolut, Albert, Brigit are all bidding on the same head terms. Generic ASO advice does not work here for two reasons:

1. Apple's App Store financial-app review is materially stricter than the rest of the store. Submissions get rejected for unsubstantiated APY claims, vague "FDIC insured" wording, mock screenshots, or feature mismatches.
2. Google Play's Designated Countries policy for financial services requires registration in many markets and the Personal Loans / Banking taxonomy has its own disclosure rules.

ASO for a neobank is half keyword work, half disclosure work.

## Title and subtitle keyword strategy

Apple title: 30 characters. Subtitle: 30 characters. Indexed for search.

Primary keyword in title. Brand first if brand has search volume. Keyword first if not.

Good vs bad title:
- Good: `Chime: Mobile Banking`
- Good: `Dave: Banking & Cash Advance`
- Good: `Varo Bank: Mobile Banking`
- Bad: `Banking App` (no brand, no differentiator, will not rank)
- Bad: `Chime` (wastes 25 indexable characters)

Subtitle pattern: secondary high-volume keyword + benefit
- `Get paid early. No fees.`
- `Direct deposit, instant.`
- `Bank, save, send money fast.`

Keyword field (iOS, hidden, 100 chars): comma-separated, no spaces, no plurals (Apple handles them), no brand names of competitors (rejection), no "free" (separate Apple rule).

Google Play short description: 80 characters. Long description: 4000 characters, indexed. Keyword density matters more here than on iOS.

## Screenshot trust hierarchy

Order matters. Users swipe in sequence. First three screenshots carry the entire conversion.

1. **Trust signal**: FDIC partner bank disclosure, security/encryption iconography, real-feeling bank UI. Not a feature. Not a benefit. Trust. Example: "Banking services provided by [Partner Bank], Member FDIC."
2. **Primary benefit**: the single highest-converting promise. For most neobanks: "Get paid up to 2 days early with direct deposit." Hero image of paycheck-arriving notification + dollar amount.
3. **Social proof / rating**: review quote, app rating callout, user count. "Trusted by 20M+ members" or "4.8 stars, 1.2M ratings." Real numbers only.
4. **Secondary feature**: savings, round-ups, SpotMe / overdraft, credit-builder. The next reason to install.
5. **CTA / brand close**: "Open in 2 minutes. No minimum." with the brand mark.

Rules:
- No mock APYs that exceed actual rates
- No mock balances that imply unrealistic outcomes
- Every claim shown in a screenshot must be substantiated in the description
- Partner bank disclosure visible somewhere in screenshots 1-3

## Description structure

Hook line first. Apple shows the first ~170 characters above the fold before "more." Google Play shows the first short description above the fold.

Order:
1. Hook line, under 170 chars, the primary benefit
2. 4-6 benefit bullets covering DD early, no monthly fees, fee-free ATM network, savings, etc.
3. Partner bank disclosure block: `Banking services provided by [Bank], Member FDIC. The [Card Name] [Debit/Credit] Card is issued by [Bank], pursuant to a license from [Visa/Mastercard].`
4. Fee schedule link or fee summary
5. Support contact (email, phone, hours)
6. Legal language for any speed claim, APY, or guarantee

## In-App Events (iOS)

In-App Events are time-bound surfaces in the App Store that show a card from your listing for up to 14 days. Free distribution. Strong for neobanks.

Use cases:
- DD bonus promo: "Open an account this month, get $100 with direct deposit."
- New feature launch: "Now: SpotMe up to $200."
- Referral campaigns: "Refer a friend, both get $100."
- Tax-season cash advance pushes (January-April)
- Back-to-school savings pushes (August)

Cadence: 1-2 active events at a time. Rotate every 7-14 days. Each event: title (30 char), short description (50 char), long description (120 char), event card image.

Copy patterns:
- Title: `Get $100 with direct deposit`
- Short: `Limited-time bonus for new members.`
- Long: `Open an account and get a $100 bonus when you set up qualifying direct deposit of $200+ within 45 days. Terms apply.`

## Review management

### 1-star fraud complaint pattern

Most 1-star reviews on neobank apps are not product complaints. They are:
- Account closures the user did not understand
- Disputed transactions with outcomes the user disagreed with
- KYC failures
- Hold periods on first DD
- Failed transfers
- Suspected fraud lockouts

Response template (1-star "they froze my account"):
> "We hear you, and we want to help resolve this. Account holds are usually triggered by activity our partner bank's fraud rules flag. We can't share specifics here for your security, but our support team can walk through it. Please email [support email] with the subject line "App Store review escalation" and we'll get back to you within 1 business day. [First name], [Brand] Support"

Response cadence: every 1-star and 2-star review within 48 hours. 4-star and 5-star: optional.

### Fake review attacks

Apple's process: report via App Store Connect under "Report a Concern." Document the pattern: same wording across multiple reviews, same posting time window, accounts created same day, suspicious account behavior. Apple removes coordinated attacks but expects evidence.

Google Play: similar flagging via Play Console. Reviews tagged as policy-violating (spam, harassment, off-topic) get removed faster than reviews you simply disagree with.

## Apple and Google financial-app policy gotchas

- Claim substantiation: every benefit, fee, APY, or speed claim in the description needs to be substantiated. Apple reviewers will check.
- Screenshot accuracy: cannot show a feature that does not exist in the shipping app. Cannot show APY higher than offered. Cannot show fee-free ATMs without the network reference.
- "Free": Apple has specific rules on the word "free." Cannot say "100% free" if any fee exists. Use specific phrasing: "No monthly fees" or "No overdraft fees."
- No misleading screenshots: old UI, beta features, or aspirational mockups all trigger rejection.
- Google Play Designated Countries: financial services apps may need to register and provide additional documentation in markets including India, Brazil, Mexico, EU.
- Apple looks for a partner bank disclosure clearly stated in the app and listing. Hiding "Banking services provided by [Bank]" tends to trigger rejection.

## Localization

US-only is the default for most US neobanks. Do not localize beyond what you actually serve.

For neobanks operating across markets (Revolut, N26, Wise):
- UK: separate listing, FCA disclosures, "FSCS protected" instead of "FDIC insured"
- EU: GDPR + PSD2 disclosures, country-by-country if benefits differ
- LATAM: ES-MX, PT-BR, regional review steps vary sharply
- Canada: CDIC instead of FDIC, English + French listings

Decision rule: localize where you have a charter or partner bank, and where the reviewer will see consistent feature parity. Do not localize aspirationally.

## Output format: ASO audit report

Use this template when this skill is invoked:

```
ASO AUDIT REPORT

App: [name]
Store: [App Store / Google Play]
Audit date: [date]

Title + subtitle:
- Current:
- Issue:
- Recommended:

Keywords:
- Current targeting:
- Gaps:
- Recommended:

Screenshots:
- Order issue:
- Trust hierarchy match: [yes/no]
- Disclosure gaps (e.g. partner bank not visible in screenshots 1-3):
- Recommended order:

Description:
- Above-fold hook:
- Missing disclosures:
- Recommended structure:

In-App Events (iOS only):
- Active events:
- Recommended cadence:
- Next event copy:

Review management:
- Avg rating:
- 1-star pattern:
- Response cadence gap:
- Suspected fake-review activity:

Disclosure / claim issues found:

Priority fix list:
1.
2.
3.

Review owner before submission:
```

## Disclaimer

This skill does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything.
