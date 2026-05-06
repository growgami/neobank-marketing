# DD Nurture Sequence Templates

Copy templates referenced by `SKILL.md`. Pair with the trigger map and channel split rules in the parent skill file.

All copy is templated. Every claim, dollar amount, speed reference, and feature mention needs to be substantiated against your own data and routed through your standard review pipeline before sending. This file does not take compliance reviews into account.

---

## Trigger 1: DD detected (first time)

Fires within minutes of the first qualifying ACH credit hitting the account.

### Push (sent within 5 min of credit)
> Your paycheck just arrived. $X is in your account, up to 2 days early.

### Email (sent within 1 hour)
> Subject: Your paycheck just hit. Here's what changed.
>
> Body:
> $X just landed in your account, up to 2 days earlier than your scheduled payday.
>
> Now that your direct deposit is set up, you have access to:
> - Early paycheck access on every direct deposit
> - SpotMe overdraft up to $X (after eligibility)
> - Higher savings interest on your Savings Account
> - Bonus eligibility on referrals
>
> Tap to see your balance.
>
> [CTA: View account]

---

## Trigger 2: Payday recurring (every DD)

Fires on every subsequent DD credit. Push only.

### Push variations (rotate to avoid fatigue)
> Paycheck day. $X just hit your account.

> $X is in. Your paycheck arrived [up to 2 days] early.

> It's payday. $X just landed.

---

## Trigger 3: End-of-week summary

Sundays, 9 AM local.

### Email
> Subject: Your week: $X spent, $Y saved
>
> Body:
> Here's how last week broke down.
>
> Spending: $X
> Top 3 merchants: [list]
> Saved automatically: $Y
> Savings goal progress: $Y of $Z
>
> Want to save a little more next week? Round up every purchase to the nearest dollar. Small change, big habit.
>
> [CTA: Turn on round-ups]

---

## Trigger 4: Round-up activation prompt

7 days post first DD. In-app card on next session + push if no action in 48h.

### In-app card
> Headline: Save without thinking about it
> Body: Round up every purchase to the nearest dollar. The change goes straight to your savings.
> CTA: Turn on round-ups

### Push (24-48h follow-up)
> One tap to save more. Round-ups can grow your savings without changing what you buy.

---

## Trigger 5: Savings goal creation

14 days post first DD. Email + in-app.

### Email
> Subject: Pick a number. Hit it.
>
> Body:
> People who set a savings goal save 2x more than people who don't. Pick a goal (emergency fund, trip, holiday) and we'll track your progress.
>
> Common goals our members set:
> - Emergency fund: $1,000
> - Vacation: $2,500
> - Holiday spending: $500
>
> [CTA: Set your goal]

### In-app card (next session after email)
> Headline: Set your first savings goal
> Body: Pick a target. We'll track it for you and celebrate when you hit it.
> CTA: Get started

---

## Trigger 6: Feature discovery sequence

One feature per week. Do not bundle.

### Week 2: SpotMe / overdraft

Push:
> You're eligible for SpotMe up to $X. Cover small overdrafts with no fees.

Email subject: You qualify for SpotMe
Email body:
> Good news. Based on your direct deposit history, you're eligible for SpotMe up to $X.
>
> SpotMe lets you overdraw your account by a small amount with no fees. Useful for small purchases that would otherwise decline.
>
> [CTA: Activate SpotMe]
>
> Eligibility based on direct deposit history and account activity. Limits may change.

### Week 3: Credit-builder

Push:
> Build credit with the spending you already do. No credit check, no interest.

Email subject: A different way to build credit
Email body:
> The Credit Builder Card uses the money you already have. No credit check. No interest. No annual fee.
>
> Spend on the card, we report your on-time payments to the major credit bureaus, and your credit score grows.
>
> [CTA: Open Credit Builder]
>
> Disclosure block: [issuer / partner bank / credit bureau reporting language]

### Week 4: Investing or high-yield (if available)

Push:
> Your savings can earn more. See what an [X]% yield account looks like.

Email subject: Make your money work
Email body:
> Your idle balance could be earning [X]% APY in a high-yield savings account.
>
> No minimums. No lock-in. Move money in and out anytime.
>
> [CTA: Open high-yield savings]
>
> APY accurate as of [date]. Terms apply. [Insert your standard APY disclosure block]

---

## Trigger 7: Dormant DD signal

30 days post first DD with no card use in past 7 days. The user has DD but isn't swiping. Treat as primary-card competition risk.

### Push
> Your paycheck is here, but your card has been quiet. What's getting in the way?

### Email subject: Your card hasn't moved in a while
Email body:
> We've noticed your direct deposit is still arriving, but your card hasn't been used in [X] days.
>
> If something's not working (fees, declines, app issues) let us know. We're listening.
>
> [CTA: Reply to this email] [Secondary CTA: Use your card]

### In-app survey (next session)
> Quick question: what would make you use your card more often? [3 options + Other]

---

## Trigger 8: DD stopped

35 days no DD inflow on an account that previously had recurring DD.

### Day 1 push
> We noticed your direct deposit stopped. Did you change jobs?

### Day 4 email
Subject: Switching jobs? Updating direct deposit takes 2 minutes
Body:
> If your job changed, you can re-route your direct deposit to your account in about 2 minutes.
>
> [CTA: Update direct deposit]
>
> Need help finding the new employer? Reply to this email and we'll walk you through it.

### Day 10 win-back email
Subject: $25 to come back
Body:
> Re-route your direct deposit to your account by [date] and we'll add a $25 bonus when your first qualifying paycheck of $200+ arrives.
>
> [CTA: Set up direct deposit]
>
> Disclosure block: $25 bonus paid within 1-2 business days of qualifying direct deposit. Limit one per customer. Existing direct deposit re-route eligible. Bonus is taxable.

### Day 21 final-touch email
Subject: One more thing before we go quiet
Body:
> If we're not the right fit anymore, that's okay. If there's anything we can do (fees, features, support) we'd like to know.
>
> [CTA: Tell us what happened] [Secondary CTA: Set up direct deposit]

---

## Send rules summary

- Time-of-day: payday pushes within 5 min of credit. Marketing emails 9-11 AM local. Sunday summary 9 AM local. Never push between 9 PM and 8 AM local.
- Suppression: do not send marketing to users in active dispute, KYC review, or fraud lockout.
- Suppression: opt-out honored within 24 hours, opt-out signal propagates across all channels (suppress email if user opts out of push for the same campaign).
- A/B test scope: subject lines, push first sentence, in-app card headlines. Do not A/B test disclosure blocks or required language.
