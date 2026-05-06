---
name: neobank-referral-program
description: Design, copy, and anti-abuse mechanics for B2C neobank referral programs. Triggers when planning a refer-a-friend program, writing share copy, setting incentive amounts, or building fraud detection for referrals.
argument-hint: "[neobank name + program goal or surface]"
user-invocable: true
disable-model-invocation: false
---

# Neobank Referral Program

## Why this exists (first principles)

Referrals are the highest-ROI acquisition channel a B2C neobank has. Chime's S&M as a percent of revenue dropped from 42 percent in 2022 to 26 percent in Q1 2025, and referrals did most of that work. CAC at modern neobanks now sits around $100. Traditional banks pay $600+ per acquired checking customer.

The mechanic only works if the qualifying action is direct deposit or first qualifying transaction. Not signup. Signup-only referrals burn CAC with no retention, fill the funnel with bonus farmers, and produce a 90-day churn cliff that makes the channel look broken.

Build the program around "got a paycheck routed in" not "downloaded an app." Everything else (incentive size, copy, share surfaces) flows from that.

## Mechanic design

### Incentive structure (referrer + referee)

Two-sided beats one-sided in conversion and in long-term retention. Roughly equal sides outperform skewed splits.

- $50 / $50: broad mass-market, lower-friction qualifying action
- $100 / $100: premium positioning, stricter DD threshold
- $25 / $25: cultural / habitual sharing (Cash App pattern, runs on volume not amount)

### Qualifying action

The bonus must trigger on a qualifying direct deposit OR a qualifying first transaction (e.g. $200+ in card spend or DD within 45 days). Never on signup alone.

Standard pattern:
> "You'll earn $100 when your friend opens an account and receives a qualifying direct deposit of $200 or more within 45 days."

### Payout timing

Pay within 1-2 business days of qualification. Faster payout drives more shares. Hold-and-clawback windows beyond 7 days correlate with referrer drop-off.

### Referral cap

Cap per referrer per calendar year. Standard: $1,000-$2,500. Soft-throttle at $500 (require additional KYC review on referrer past that point). Caps prevent professional bonus farmers without hurting genuine evangelists.

### Fraud detection

Flag and review when any of these fire:
- Same device fingerprint across referrer and referee
- Same IP at signup
- Same physical address
- Phone or email differs by less than 2 characters from referrer
- Synthetic ID signals: SSN issued < 5 years ago vs claimed age, no credit history, address listed as a CMRA
- DD source matches referrer's DD source
- Funded via debit card belonging to referrer

Hold bonus payout pending manual review on any flag. Do not auto-deny. Borderline cases include married couples and roommates, both legitimate.

## Reference programs

- **Chime**: $100 / $100, conditional on $200+ qualifying DD within 45 days. Drove the bulk of Chime's S&M efficiency gain. Limit and qualifying language clearly disclosed at every share surface.
- **Cash App**: $5-15 per side, small dollar amount but extremely high cultural circulation. Trades incentive size for share frequency. Works because Cash App is already a peer-to-peer surface.
- **Revolut**: time-bound bonus structures with gamified elements ("invite 3 friends in 7 days, get $X"). Higher activation in the window, sharper churn after.
- **SoFi Money**: bonus tied to direct deposit + first ACH transfer, often $25-$75. Stacks with cross-product (loans, invest) referral.

## Copy templates (referrer message)

Templated only. The referrer cannot freestyle claims about yield, features, or speed of funds. That creates FTC endorsement liability and CFPB UDAAP risk for the neobank. Provide pre-filled share text with the disclosure baked in.

### SMS
> "Hey, I use [Neobank] for my paycheck and they're giving us each $[X] if you sign up and get your direct deposit set up. Here's my link: [URL]. (I get $[X] when you complete the qualifying steps.)"

### Email share
> Subject: I think you'd like [Neobank]
> Body: I've been using [Neobank] for [my paycheck / day-to-day spending]. They have a refer-a-friend thing. We'd both get $[X] if you sign up and route your direct deposit. Here's the link: [URL].
> Disclosure: I receive $[X] when you sign up and complete a qualifying direct deposit of $[Y]+ within 45 days.

### In-app share card
> "Get $[X] from [Neobank]. [Referrer name] sent you a sign-up bonus."
> Fine print: "Both you and [referrer] receive $[X] when you complete a qualifying direct deposit of $[Y]+ within 45 days of opening your account."

### Social caption (pre-filled, copy-to-clipboard)
> "Been using [Neobank] for the last [time]. They're running a sign-up bonus right now, link in bio. (I get a referral bonus when you complete the qualifying steps.)"

### Post-share confirmation
> "Your link is on its way. You'll see your $[X] within 1-2 business days after your friend completes their qualifying direct deposit."

## Required disclosure on every referral surface

Non-negotiable. The FTC's 2023 update to the Endorsement Guides makes "material connection" disclosure required on any share where the sharer receives compensation, including referral bonuses. CFPB UDAAP layers on top of that.

Required language pattern (must appear on every share surface, every social post, every email):

> "I receive [$X] when you sign up and complete [qualifying action]."

Why non-negotuable:
- 16 CFR Part 255 covers all endorsements, not just paid creator deals
- Bonus = material connection
- Hiding it = deceptive endorsement
- Liability sits with the brand, not the referrer

Build this into the share text and lock it. Do not allow editing of the disclosure line.

## Anti-abuse

Detection signals (already listed in mechanic design above): same device, same IP, same address, similar email/phone, synthetic ID flags, shared debit card funding source.

Throttle limits:
- 5 invites per day soft cap (UI prevents more)
- 25 invites per week
- $500 in payouts before manual review
- $2,500 annual cap

KYC link: every referral payout is contingent on the referee passing KYC. If referee fails KYC, referrer is not paid. If referee closes account within 30 days of bonus payout and never funded the account further, claw back the referrer bonus.

## Output format: referral program design doc

Use this template when this skill is invoked:

```
REFERRAL PROGRAM DESIGN

Neobank: [name]
Goal: [acquisition / activation / retention via DD]
Launch surface: [in-app / email / web]

Incentive structure:
- Referrer: $[X]
- Referee: $[Y]
- Rationale:

Qualifying action:
- Type: [DD / first transaction / combo]
- Threshold: [$X within Y days]

Payout timing:
- Trigger event:
- Payout SLA:

Caps:
- Per-referrer annual:
- Soft review threshold:

Share surfaces (with copy):
- SMS:
- Email:
- In-app:
- Social caption:

Disclosure (verbatim, locked):

Anti-abuse rules:

Success metrics:
- K-factor
- Cost per qualified referral
- 90-day retention of referred users vs paid-channel users
- DD activation rate of referred users

Compliance review owner:
```

## Disclaimer

This skill does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything.
