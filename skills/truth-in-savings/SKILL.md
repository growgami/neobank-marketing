---
name: truth-in-savings
description: Reg DD compliance review for any rate, APY, yield, or savings copy. Auto-triggers when copy mentions APY, interest rate, savings rate, yield, or designs/reviews savings product copy.
argument-hint: "[rate copy, surface, product details]"
user-invocable: true
disable-model-invocation: false
---

# Truth in Savings (Reg DD) Compliance

## Why this exists (first principles)

The Truth in Savings Act and Regulation DD (12 CFR Part 1030) are unambiguous about how savings rates can be advertised. The rule is short. Violations are common because writers default to "high yield" or "earn up to" without the legally-required co-disclosures.

The audit pattern is mechanical: 6 elements must accompany any rate, "APY" is the only allowed term, banned phrases are listed. Run the checks. Done.

## The 6 required elements when advertising a rate

Whenever a rate is shown, the following must be present in the same context:

1. **"Annual Percentage Yield" or "APY"**. No other term. Not "interest rate" used loosely. Not "yield" alone. Not "return."
2. **Effective date of the rate**. "X% APY as of [Month Day, Year]."
3. **Minimum balance to obtain the APY**. If tiered, show the tier structure or link to it.
4. **Minimum balance to open the account**. Often $0, still must be stated.
5. **Whether fees could reduce earnings**. "Fees may reduce earnings."
6. **Whether the rate is variable**. "Variable rate. Subject to change without notice."

Missing any one of these = Reg DD violation.

## Banned patterns

- **"High yield"** without showing the actual APY in close proximity.
- **"Earn up to X%"** without showing the conditions to reach the top tier.
- **"Highest APY"** without a dated source comparing against named competitors.
- **Comparing your APY to a competitor's** without the effective date of both APYs and the source.
- **"X% interest"** when you mean APY. Reg DD requires APY specifically because it accounts for compounding.
- **"Bonus rate"** without disclosing how the bonus is calculated, how long it lasts, and what triggers reversion.
- **Annualized claims on short-window promotions** without clearly stating the promo window and post-promo rate.

## Display patterns by surface

### Hero copy on landing page

Headline: rate as APY with effective date. Below the fold or in a footnote near the rate: minimum to open, minimum to earn the rate, fee disclosure, variable language.

Example skeleton:

> Earn [X]% APY on your savings.
> [X]% Annual Percentage Yield as of [date]. Variable rate. No minimum to open. Earn the stated APY on balances up to [Y]. Fees may reduce earnings.

### Ad creative (limited footer space)

Static or video footer line:

> [X]% APY as of [date]. Variable rate. Conditions apply. See [URL] for full details.

The link must resolve to a page that satisfies all 6 elements.

### Email subject line

Either show the rate with a footnote in the email body, or do not show a number in the subject.

OK: "Your savings now earn [X]% APY" → with full Reg DD block in the email body.

Not OK: "High-yield savings, rates that beat banks" with no rate body content.

### Push notification

Do not show a rate in push. Drive to a screen with full disclosure.

### App store screenshot caption

Caption with rate must carry full disclosure in the screenshot text, not just in the app store description block.

> Earn [X]% APY. Variable rate, as of [date]. Fees may reduce earnings.

## Tiered rate handling

If the rate varies by balance, every advertisement must either show the full tier table or clearly link to it.

Example:

> Earn up to [X]% APY. Tiered: balances $0 to $9,999 earn [A]% APY. Balances $10,000 and above earn [X]% APY. Tiers and APYs as of [date]. Variable. Fees may reduce earnings.

Do not advertise the top tier as "the rate" if most customers will not reach it.

## Promotional and intro rate handling

Required:

- The promotional APY
- The duration of the promotional period
- The APY that applies after the promo ends
- Effective date
- Any conditions to qualify (new money, direct deposit, balance threshold)

Example:

> Earn [Y]% APY for the first 90 days. After the promotional period, the APY reverts to [Z]% (variable, as of [date]). Promotional rate available to new customers on funds deposited within 30 days of account opening. Fees may reduce earnings.

## Output format

```
REG DD REVIEW: [asset] | [surface] | [date]

ELEMENT CHECK:
  1. APY term used: yes / no
  2. Effective date: yes / no
  3. Min balance for APY: yes / no
  4. Min balance to open: yes / no
  5. Fee disclosure: yes / no
  6. Variable language: yes / no

BANNED PATTERNS DETECTED:
  - "..." (line X)

REWRITE:
  [compliant version]

VERDICT: SHIP / FIX / KILL
```

## Compliance and human review

This skill produces drafts, not legal artifacts. Every output must be reviewed by qualified compliance counsel and your partner bank's marketing review team before publishing. Specifically check: Truth in Savings Act 12 USC 4301 et seq., Regulation DD 12 CFR Part 1030. This pack does not constitute legal advice and Growgami is not liable for outputs.
