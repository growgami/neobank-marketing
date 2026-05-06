---
name: direct-deposit-acquisition
description: Acquisition mechanics for getting B2C neobank users to route their payroll direct deposit. Triggers when planning a DD campaign, writing DD onboarding copy, evaluating DD switcher vendors, or designing DD-conditional bonuses.
argument-hint: "[neobank name + acquisition channel or surface]"
user-invocable: true
disable-model-invocation: false
---

# Direct Deposit Acquisition

## Why this exists (first principles)

Interchange revenue from card swipes is the primary revenue stream for B2C neobanks. Card swipes scale with primary-bank status. Primary-bank status correlates almost 1:1 with whether a user has routed their paycheck via direct deposit. A user without DD is a dormant card.

Chime's active members average around 54 swipes per month. That is a DD-routed user, not a topped-up one. Top-up users average a fraction of that and churn within 90 days. Without DD, CAC never recovers.

Every other acquisition channel (referrals, ASO, paid, content) is in service of one outcome: getting payroll routed to the neobank within the first 45 days. If a campaign does not move DD-routed activations, it is decoration.

## The 4 acquisition mechanics

### 1. "Get paid 2 days early"

Mechanism: when an employer's payroll provider sends the ACH credit notification, settlement happens 1-2 business days later. Most banks wait for settlement. Neobanks credit the user on notification. Real money. Real days. Not a marketing claim.

Copy variations:

- Hero: "Get paid up to 2 days early with direct deposit."
- Hero (benefit-led): "Your paycheck. 2 days sooner."
- Ad headline: "Why wait until Friday? Get paid Wednesday."
- Email subject: "Your paycheck could hit Wednesday instead of Friday."
- Push (post-DD setup): "Your paycheck just arrived 2 days early."

Conditions to disclose: "Early access to direct deposit funds depends on the timing of the payer's submission of the deposit. We generally make these funds available on the day the payment file is received, which may be up to 2 days earlier than the scheduled payment date."

### 2. Cash bonus for first qualifying DD

Standard range: $50 to $300. Higher bonuses correlate with stricter qualifying conditions. Lower bonuses convert more signups but produce more low-quality DDs that stop after the qualifying window.

Qualifying language pattern: "Get $100 when you receive a qualifying direct deposit of $200 or more within 45 days of opening your account."

Disclosure pattern (must appear within 1 scroll of the offer):
- Minimum DD amount and timeframe
- Account must remain open through bonus payout
- Bonus is taxable (1099-INT issued if total interest + bonuses exceed $10)
- Limit one per customer
- Not available to existing customers or those who closed accounts in past 12 months

### 3. DD switcher infrastructure

Embedded switcher is the difference between 8 percent DD activation and 25-30 percent. Manual paper-form DD setup is a funnel killer.

Vendors:
- Pinwheel: PreMatch credential-less flow, no payroll login required for matched employers, claims up to 200 percent conversion improvement vs credentialed flows
- Atomic: covers 160+ FIs and most major payroll/HRIS systems, powers Galileo's DD Switch product (so most Galileo-issued cards already have it)
- Argyle: broad payroll coverage, stronger on gig and 1099 workers, useful for neobanks targeting Uber/DoorDash/Instacart workers

Decision rule: Pinwheel for W-2 mass market, Argyle if your ICP skews 1099/gig, Atomic if you are already on Galileo. Run conversion tests against the existing flow before swapping.

### 4. Employer ID lookup

Friction killer. Pre-populate employer dropdown with autocomplete from the user's email domain or zip code. Surface a "can't find my employer?" fallback that offers manual ABA + account number entry instead of dead-ending.

Pattern: type 3 characters, see top 5 employers in their area, tap to select. Unmatched employers route to a generic ACH form with the new account's routing and account number pre-filled and a "copy" button next to each.

## Onboarding placement

Order that converts:

1. Phone + email
2. KYC (legal name, DOB, SSN, address)
3. Card design selection (low-friction commitment)
4. First deposit prompt (any source: DD switcher, debit card top-up, or external transfer)
5. DD switcher screen as primary CTA, with "skip for now" small-text fallback
6. Card activation
7. Re-prompt DD switcher at 7 days, 14 days, and on first paycheck-day if user picked top-up

Placing DD switcher before card activation matters. The card is the reward gate. Users will tolerate one more screen to get it.

## Push notification triggers

The single highest-engagement message a B2C neobank sends:

> "Your paycheck just arrived 2 days early. $X just hit your account."

Ship this on every DD credit. It reinforces the core value prop, drives app open, and primes card use within 24 hours of paycheck.

Other DD-related triggers:
- Day before expected payday: "Your paycheck is on its way. Get notified when it arrives."
- DD setup confirmed but not yet received: "You're set up. Your first early paycheck should hit by [date]."
- DD bonus earned: "You did it. $100 is yours. It will hit your account in 1-2 business days."

## Re-engagement for dormant or stopped DD

Signal: 35+ days since last DD inflow on an account that previously had recurring DD.

Sequence:
- Day 1: "We noticed your direct deposit stopped. Did you change jobs?"
- Day 4: "Switching jobs? It takes 2 minutes to update your direct deposit." (links to switcher)
- Day 10: "Come back with a $25 bonus. Set up direct deposit by [date] and we'll add $25 when your first paycheck of $200+ arrives."
- Day 21: final-touch email with employer-change support contact

## Output format: DD acquisition campaign brief

Use this template when this skill is invoked:

```
DD ACQUISITION CAMPAIGN BRIEF

Neobank: [name]
Surface: [hero / paid ad / email / push / onboarding step]
Mechanic: [early pay / cash bonus / switcher / employer lookup / combo]

Offer:
- Headline:
- Subheadline:
- Primary CTA:
- Bonus amount + qualifying conditions:

Funnel placement:
- Where in onboarding:
- Skip behavior:
- Re-prompt cadence:

Switcher vendor + reason:

Disclosure block (verbatim):

Push trigger copy (post-conversion):

Success metrics:
- DD switcher start rate
- DD switcher completion rate
- First qualifying DD within 45 days
- 90-day DD retention

Review owner before launch:
```

## Disclaimer

This skill does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything.
