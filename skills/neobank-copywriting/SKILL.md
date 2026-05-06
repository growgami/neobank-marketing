---
name: neobank-copywriting
description: Copy primitive for every consumer-facing word a B2C neobank ships. Auto-triggers when drafting or revising hero, subhead, benefit row, CTA, push notification, email, or app store copy. Enforces calibrated specificity within disclosure and the strict-editor screenshot test.
argument-hint: "[asset type, audience segment, claim list]"
user-invocable: true
disable-model-invocation: false
---

# Neobank Copywriting

## Why this exists (first principles)

Generic SaaS copywriting frameworks teach "claim more, qualify less." Make it punchy, sell the dream. That advice gets a B2C neobank stuck in marketing review and ignored by users.

Neobank copywriting reverses the rule: the differentiation is **calibrated specificity within disclosure**. The best B2C neobank copy is plain, specific, and survives a strict-editor screenshot. Hype kills you twice. It gets flagged by your partner bank's marketing team, and it sounds like every other fintech in the App Store.

The proof is in the brands that pulled away:

- Chime: "Get paid up to 2 days early. Why should you wait? It's your money." Specific (2 days), plain (no jargon), survives screenshot (the "up to" and the cause are clear).
- Cash App: "For the people." Five syllables, identity claim, no quantitative exposure.
- Mercury (B2B contrast): "Banking that gets out of your way." A negative claim, hard to attack.
- Revolut: "One app. All things money." Functional, no quantitative exposure.

Compare to the dead-on-arrival pattern: "Banking, reimagined. The future of finance, built for the modern consumer." Every fintech says this. Customers do not remember it. Marketing reviewers stop reading at the third cliche.

## The 6-pass copywriting workflow

Run in this order. Each pass is a gate.

### Pass 1: Audience pass

Who is reading this asset? Pick the segment from the neobank context:

- **Mass consumer** (Chime, Current, Varo): "I get paid Friday and money is tight." Plain language, dollar specifics.
- **Cultural / niche affinity** (Cash App, Greenwood, Daylight, First Boulevard): identity-first, brand voice, the product is the badge.
- **Premium / aspirational** (SoFi, Ally premium tiers): rate-led, clean visual, upmarket signal.
- **Niche functional** (Step for teens, Greenlight for kids, Aspiration for ESG): the audience and the use case are the same word.

Same product, four different copy registers. Decide first, write second.

### Pass 2: Tone pass

Pull from `reference/tone-matrix.md`. Match the archetype for the audience segment. If you are off-archetype, you are off-brand and the reader feels it within one line.

### Pass 3: Specificity pass

Replace every adjective with a sourceable fact. This is the pass that separates Chime from generic.

- "Fast direct deposits" -> "Direct deposits hit up to 2 days before settlement."
- "Easy to use" -> cut the word, show the screenshot.
- "Secure banking" -> "256-bit encryption, biometric login, zero-liability protection on your card."
- "No hidden fees" -> "No monthly fee. No overdraft fee. No minimum balance fee."
- "Save more" -> "Round up every purchase and move the change to savings."

If the line will not survive a "what specifically" challenge, it is filler. Cut or rewrite.

### Pass 4: Substantiation pass

Every quantitative claim has a sourced, dated footnote. Every comparative claim has a fairly-sourced competitor reference, pulled within the last 30 days.

- Quantitative: "Save $300 a year" needs the methodology document on file.
- Speed: "Up to 2 days early" needs the disclosure that explains it depends on when the payer files the ACH.
- Comparative: "More features than [competitor]" needs the competitor's published feature list as of [date].

No source on file = no claim. Rewrite to a claim you can back.

### Pass 5: Banned-word pass

Scan against `reference/banned-words.md`. The repeat offenders:

- "Free" without footnote
- "Guaranteed" anything in a financial context
- "FDIC insured" without the partner bank name
- "Instant" for transfers
- "Best APY" or any superlative without dated competitive sourcing
- "Risk-free"
- "No fees" as a global claim (almost always inaccurate at the product level)

Plus the AI slop additions every pass should kill: "seamlessly," "robust," "leverage" as a verb, "comprehensive," "unlock," "elevate," "supercharge," "best-in-class," "harness the power of."

### Pass 6: Disclosure-fit pass

Required footnotes present? Sized at minimum 8pt or the platform equivalent? WCAG AA contrast against background? Disclosure within reasonable proximity to the claim it qualifies?

If the disclosure is doing more work than the claim, the claim is wrong. Rewrite the claim.

## Format-specific patterns

- **Hero**: under 8 words. Verb or identity claim. No subordinate clause.
- **Subhead**: under 20 words. Specific benefit, plain language.
- **Benefit row**: 3-5 max. Parallel grammatical structure. One concrete fact each.
- **CTA**: verb-led, second person. "Open an account," "Get started," "Send money." Not "Learn more about our services."
- **Footnote**: one per claim. Date stamped. Linked source where applicable.
- **Push notification**: under 50 characters subject, under 100 body. No FDIC claim (no room for the disclosure that has to ride with it). Drive to a screen.
- **Email subject**: under 40 characters. No "guaranteed," no "free" without context.

## Reference good copy with attribution

Real published lines, cited:

- **Chime**: "Get paid up to 2 days early. Why should you wait? It's your money." (chime.com homepage, multi-year run)
- **Cash App**: "For the people." (cash.app, longstanding tagline)
- **Mercury** (B2B contrast): "Banking that gets out of your way." (mercury.com, used in homepage and ad creative)
- **Revolut**: "One app. All things money." (revolut.com)
- **Varo**: "Banking for all of us." (varomoney.com)
- **SoFi**: "Bank smarter. Borrow smarter. Invest smarter." (sofi.com)
- **Monzo (UK)**: "Banking made easy." (monzo.com)

What these share: short, specific or identity-led, no quantitative exposure in the headline, no AI slop adjectives.

## Anti-patterns (do not write)

- "Banking, reimagined." Every fintech says this. Zero signal.
- "The future of finance." Forward-looking, vague, every fintech says it.
- "Built for the modern [audience]." No specific signal. Could mean anything.
- "Unlock your financial potential." Forward-looking outcome promise. Vague, AI slop, and the kind of line a strict editor circles in red.
- "Effortlessly manage your money." AI slop. Replace with a screenshot.
- "Empowering [audience] to [verb]." Empty.
- "Seamless banking experience." Both AI slop words in one line.
- "Take control of your finances." Cliche, no specific signal.

## The strict-editor screenshot test

Before any line ships: imagine a strict editor screenshots this line out of context and drops it on your CMO's desk with a red circle. Does the line stand on its own?

- "Get paid 2 days early": stands up if "up to" is preserved and the ACH-timing footnote is close by.
- "Instant transfers": fails. Replace with "transfers in seconds when both users are on [Brand]" or similar.
- "FDIC insured": fails without the partner bank name. Always rewrite to "Banking services provided by [Partner Bank], Member FDIC."
- "Better than your old bank": fails. Comparative without a specific competitor and source. Replace.

If the line cannot survive the test, rewrite or kill.

## Output format

Always end with shippable copy in DRAFT v1, not just the audit. The audit blocks are the work-in-public; the draft is the artifact.

```
COPY BRIEF: [asset name] | [channel] | [date]

AUDIENCE
  Segment: [mass / cultural / premium / niche / community-transparent]
  Tone target: [archetype from tone-matrix.md]

CLAIMS (one row each)
  Claim: "..." | Source: [doc / URL / date] | Substantiated: yes / no
  Claim: "..." | Source: [...] | Substantiated: yes / no

BANNED-WORD CHECK
  Scanned: yes
  Hits: [list with line refs]
  Resolved: [list]

DISCLOSURE LIST
  Required: [list of footnotes]
  Present: [list]
  Missing: [list]

DRAFT v1 (shippable copy)
  Hero: "..."
  Subhead: "..."
  Benefit 1: "..."
  Benefit 2: "..."
  Benefit 3: "..."
  CTA: "..."
  Footnotes: [...]

STRICT-EDITOR SCREENSHOT TEST
  Lines that pass: [...]
  Lines to rewrite: [rewrite each one inline below the list, do not just flag it]
```

If the user asked for ad creative, push, email, or any specific format, deliver shippable copy in that format. Do not stop at the audit blocks above and ask the user to write it themselves.

## Disclaimer

This skill does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything.
