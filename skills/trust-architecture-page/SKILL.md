---
name: trust-architecture-page
description: Trust surface system for B2C neobanks. Auditing OR drafting. Auto-triggers when designing, auditing, or writing security, how-we-make-money, partner bank disclosure, fraud center, status, dispute, or trust pages. Treats the whole trust surface as one designed system, not a legal afterthought. Outputs shippable page copy with placeholders for bank-specific facts.
argument-hint: "[brand, partner bank(s), current trust pages or audit target]"
user-invocable: true
disable-model-invocation: false
---

# Trust Architecture Page System

## Why this exists (first principles)

B2C neobanks have a structural trust deficit vs. legacy banks. No branches, no century of brand, no relationship with the customer's parents and grandparents. After Synapse (April 2024) froze ~$200M of customer funds at multiple non-bank fintechs, the consumer side of the market is now sophisticated about partner-bank risk. The "is this thing real" question is asked before signup, not after.

The trust surface is a primary conversion tool. It is not a legal afterthought.

Two reference moves:

- **Mercury post-Synapse, mid-2024**: explicitly named Column Bank and Lead Bank as direct partners on a transparent disclosure page. Strategy, not afterthought. Customers shared screenshots of the page on Twitter as a reason to switch.
- **Monzo (UK)**: "How we make money" page has been the foundation of brand trust for years. Plain English, breaks down interchange, net interest margin, paid plans. Customers cite it when asked why they trust Monzo more than other challenger banks.

Vague reassurance theater ("we take security seriously") underperforms specific disclosure ("256-bit encryption, biometric login, $250K FDIC pass-through via [Partner Bank], FDIC certificate #[CERT NO]"). Specificity converts. Vagueness signals you have something to hide.

## The 7 pages every B2C neobank needs

Build all 7 before scaling acquisition. Full content spec per page in `page-specs.md`.

1. **Security page** (/security): encryption, biometrics, fraud alerts, partner bank, SOC 2, 24/7 fraud line.
2. **How we make money** (/how-we-make-money): interchange, NIM, subscription, lending. Plain English. Reference: Monzo.
3. **Partner bank disclosure** (/banking-services): bank legal name, FDIC certificate number, pass-through explanation, multi-bank sweep if applicable. Post-Synapse the bar is explicit naming.
4. **Fraud center** (/fraud): report flow, scam education, dispute timeline, never-do examples.
5. **Status page** (status.[brand].com): real-time status + 12+ months of incident history. Reference: Monzo's public page.
6. **Disputes and complaints** (/disputes): dispute timeline, channels, escalation, complaint channel for users.
7. **Audit and trust signals** (/trust or /audits): SOC 2, PCI DSS, third-party audits, state MTL list, FinCEN MSB if applicable.

Each page's required content list, tone notes, and references live in `page-specs.md`. Read that before drafting any page.

## IA and placement

### Footer mapping

Every page on the site should footer-link:
- Security
- How we make money
- Partner bank disclosure (with FDIC language inline in the footer too)
- Privacy policy
- Terms of service
- Status (link to subdomain)
- Trust signals / audits
- Disputes and complaints

### Homepage trust strip

Above-the-fold or directly below the hero:
- Partner bank + FDIC line (always inline, never just footer)
- Security signal: "256-bit encryption + biometric login"
- Audit signal if available: "SOC 2 Type II"
- Customer count or rating if substantiated

### Signup screen trust elements

At the top of the deposit step:
- "Your funds will be held at [Partner Bank], Member FDIC."

At the top of the personal info step:
- "Your information is encrypted and never sold."

These are not optional. Drop-off testing shows trust signals at the friction point reduce abandonment.

## Bad-pattern audit

Kill on sight:

- **Vague claims**: "We take security seriously." Replace with specific list.
- **Missing partner bank name**: "FDIC insured" with no bank named. Fix immediately.
- **No incident history**: status page that only shows current state. Add 12+ months of historical incidents.
- **Chatbot-only support**: Chime took a $2.5M California DFPI consent order in 2024 in part for support failures. A real human support phone number is the standard. List it on the security and fraud pages.
- **No dispute timeline**: a published dispute timeline is one of the first things partner bank reviewers look for.
- **Stale audit dates**: SOC 2 from 18 months ago without a refresh reads as lapsed.
- **Buried disclosures**: partner bank name only in the footer fine print. Move it inline.
- **Single-paragraph "trust" page**: signals nothing. Customers and reviewers want specifics.

## Two output modes

This skill has two output modes. Pick based on what the user asked for.

### Mode 1: Audit (when an existing site is in scope)

```
TRUST ARCHITECTURE AUDIT: [brand] | [date]

PAGE INVENTORY (existing)
  Security: [exists / missing / weak]
  How we make money: [...]
  Partner bank disclosure: [...]
  Fraud center: [...]
  Status: [...]
  Disputes: [...]
  Audit / trust signals: [...]

GAP MAP
  Critical (review-blocker): [...]
  High (conversion exposure): [...]
  Medium (brand exposure): [...]

PAGE-BY-PAGE FIX LIST
  [page]: [specific content to add or rewrite]

IA FIX LIST
  Footer: [missing links]
  Homepage trust strip: [present / missing]
  Signup screen trust elements: [present / missing]

BAD PATTERNS PRESENT
  [pattern]: [where] -> [fix]

PRIORITY ORDER
  1. ...
  2. ...
```

### Mode 2: Draft (when starting from scratch or rewriting from blank)

This is the mode that produces shippable copy. Use it when the user does not yet have one of the 7 pages, or asks for a rewrite. Pull from `page-specs.md` for what each page needs to cover. Apply the bank's tone archetype from `neobank-context` and `tone-matrix.md`.

Output every page in this format. Do not stop at the spec. Write the actual copy.

```
PAGE: [Security | How we make money | Partner bank disclosure | Fraud center | Status | Disputes | Audit / trust signals]
URL: /[path]

[H1 headline — under 8 words, no slop]

[Subhead — one sentence, specific, no fluff]

## [Section heading 1]

[Body copy — plain English, specific facts, real numbers. Use [PLACEHOLDER] for anything the bank profile does not specify.]

## [Section heading 2]

[Body copy with disclosure pattern inline where required. Example: "Banking services provided by [Partner Bank], Member FDIC, Certificate #[CERT NO]."]

## [As many sections as the page-specs file requires for this page]

[Body copy.]

[Footer disclosure block, verbatim from the bank's standard disclosure line.]
```

Then loop through every page the user asked for, or all 7 if they asked for the full set. Every page must:

- Lead with a specific, plain headline. No "Banking, reimagined."
- Use real numbers and specific certifications wherever the profile has them
- Use `[PLACEHOLDER]` markers for anything the profile does not specify (FDIC certificate number, exact dispute SLA, etc.) so the user knows what to fill in
- Include the partner bank disclosure block at minimum once per page
- End with a list of what the user still needs to confirm before publishing

## Disclaimer

This skill does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything.
