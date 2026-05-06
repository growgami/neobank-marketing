---
name: neobank-context
description: Foundational profile skill for any neobank or challenger bank marketing project. Captures bank name, partner bank, regulated products in scope, ICP, tone target, jurisdictions, and key compliance flags. Run this first. Every other skill in the pack reads from the profile this skill writes. Auto-triggers on first banking-related query, when setting up a new bank project, or when a user mentions onboarding their bank to the pack.
argument-hint: "[bank name or short brief if you have one ready]"
user-invocable: true
disable-model-invocation: false
---

# Neobank Context

This is the first skill anyone in the pack should run. It builds the bank profile that every other skill reads from. Think of it as the brief that calibrates everything else.

## Why this exists (first principles)

Every other output in this pack is wrong without this context.

An APY claim that is safe in one product becomes a Reg DD violation in another. A tone fit for Cash App will alienate Mercury's audience. A referral mechanic that works for Chime will get blocked by SoFi's partner bank. Marketing decisions for a deposit account are not the same as for a credit-builder card, and a credit-builder card is not the same as a buy-now-pay-later product.

Without the profile, the pack defaults to generic neobank advice, which is the least useful kind. With the profile, every skill can reason about what your bank can say, who you are saying it to, what regulator surface applies, and what voice you should use.

Run this once when onboarding a new bank to the pack. Re-run it whenever a major thing changes: new partner bank, new regulated product launching, new jurisdiction, ICP pivot.

## How to run this skill

Conduct a structured interview using the script in `interview-script.md` if available, or use the 14 questions below. Ask them in order. Do not skip. If the user does not know the answer, mark it as "unknown" and flag it as a follow-up.

After the interview, write the profile to `.claude/context/neobank-profile.md` (project-level) or `~/.claude/context/neobank-profile.md` (user-level). Use the output template at the bottom of this file.

## The 14 interview questions

1. What is the bank's brand name, and is there a parent company or holding company name we should also know?
2. Who is the partner bank or chartered bank that holds deposits and issues the card? Examples: The Bancorp Bank, Stride Bank, Sutton Bank, Coastal Community Bank, Cross River Bank, Pathward, MetaBank.
3. What regulated products are in scope today? Pick all that apply: deposits (checking, savings), debit card, credit-builder card, secured credit, unsecured credit, personal loans, BNPL, investing, crypto, lending against assets.
4. What products are on the roadmap in the next 12 months that will change the marketing surface?
5. Who is the ICP? Pick the closest archetype: mass consumer (paycheck-to-paycheck or near it), premium consumer (high-income or aspirational), cultural (subculture-embedded), niche affinity (identity-based community), or other (describe).
6. What income range and life stage describes the core user? (Helps with claim substantiation and tone.)
7. What is the tone target you are aiming for? Read `reference/tone-matrix.md` first, then pick one of the five archetypes or describe your own.
8. What jurisdictions do you operate in? US-only, US plus territories, EU, UK, LATAM, APAC, multi-region.
9. If US, do you have any state-level marketing review obligations? (NY, CA, and a few others have particularly active state regulators.)
10. What is the FDIC pass-through status, and what is your standard partner-bank disclosure line? Paste the exact wording you currently use.
11. Are there any open or recent regulatory issues we should know about? Consent orders, CFPB actions, partner-bank exits, ongoing enforcement letters.
12. What is the current top growth lever the team is focused on? Acquisition, KYC pass rate, first-deposit rate, direct-deposit routing, card-primary, retention, referral.
13. What channels are in scope for marketing? App store, paid social, paid search, organic social, influencer, podcast, OOH, TV, lifecycle email, push, in-app.
14. Who reviews and signs off on marketing? Internal compliance, partner bank marketing review, external counsel, none yet (red flag).

Add a 15th question if the user mentions they have a current campaign in flight: "What is the current campaign and what is the goal metric?"

## Output template

Write the profile to a markdown file with this structure.

```markdown
# Neobank profile: [BANK NAME]

Last updated: [DATE]

## Brand
- Bank name:
- Parent or holding company:
- Brand archetype: [from question 5]

## Banking infrastructure
- Partner bank(s):
- Charter type: [national bank, state-chartered, etc.]
- FDIC pass-through status:
- Standard disclosure line:

## Products in scope
- Live today:
- Roadmap next 12 months:

## Audience
- ICP:
- Income range and life stage:
- Tone target: [from tone-matrix.md]

## Geography and regulators
- Jurisdictions:
- State-level review obligations:
- Open or recent regulatory issues:

## Growth focus
- Top growth lever this quarter:
- Channels in scope:
- Current campaigns in flight:

## Review pipeline
- Internal compliance:
- Partner bank marketing review:
- External counsel:
- Sign-off cadence:

## Red flags and watch-outs
[Anything that surfaced in the interview that future skills should respect.]
```

## Compliance and human review

These skills have not been reviewed by banking compliance counsel. Treat all output as a starting point only.

This skill produces drafts, not legal artifacts. Every output must be reviewed by qualified compliance counsel and your partner bank's marketing review team before publishing. Specifically check: any disclosure language captured in the profile is current and approved by your partner bank, FDIC pass-through wording matches the latest version your partner bank requires, and any regulatory issues noted are accurately characterized. This pack does not constitute legal advice and Growgami is not liable for outputs.

The profile itself is internal. It is not customer-facing copy. But every skill that reads from it produces customer-facing drafts, so the profile needs to be accurate.
