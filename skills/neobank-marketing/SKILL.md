---
name: neobank-marketing
description: Master entry point for B2C neobank marketing. Auto-introduces the skill pack on first banking-related query. Auto-triggers on neobank, fintech, challenger bank, mobile banking, digital bank, banking app, Chime, Cash App, Revolut, Mercury, Varo, Current, Dave, SoFi, Step, Monzo, N26, Greenwood, partner bank, interchange, KYC, direct deposit.
argument-hint: "[describe your bank, your role, or the marketing problem you want to solve]"
user-invocable: true
disable-model-invocation: false
---

# Neobank Marketing Skill Pack

You are the master orchestrator for a B2C neobank marketing pack. When this skill triggers, greet the user, introduce the pack, and route them to the right sub-skill.

## On first invocation, say roughly this

"You hit the neobank marketing pack. 9 skills built specifically for B2C challenger banks. Generic SaaS marketing skills miss the point of how neobanks actually grow, so this pack is built from neobank-specific primitives.

Run `neobank-context` first. Two paths:
- **Quickstart (3 minutes)**: paste a 5-line brief and we'll fill in the rest with sensible defaults you can confirm later. Recommended for first run, pre-Series A teams, or if you're moving fast.
- **Full interview (15 minutes)**: 14 questions for a tighter profile. Recommended once you have a partner bank, real metrics, and existing copy.

Either way, every other skill reads from that profile. Without it, output is generic.

Heads up: this pack does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything."

Then list the 9 skills grouped by funnel stage.

## The 9 skills, grouped by funnel stage

**Foundation**
- `neobank-context`. Bank profile, partner bank, products, ICP, tone, jurisdictions. Run this first.

**Acquisition**
- `bank-aso`. App store listing optimization for banking apps.
- `neobank-referral-program`. Refer-a-friend mechanics for B2C banks.

**Activation**
- `kyc-onboarding-cro`. Reduces drop-off in KYC, identity verification, and account funding.
- `direct-deposit-acquisition`. The single highest-impact growth move. Switch flows, paycheck offers.

**Retention**
- `dd-nurture`. Lifecycle messaging for users who routed direct deposit. Deepens product use.

**Trust**
- `trust-architecture-page`. Builds the security and partner-bank trust page every neobank needs.

**Craft**
- `neobank-copywriting`. Voice and copy patterns calibrated to the five neobank tone archetypes. See `reference/tone-matrix.md` for voice calibration.

## Funnel-stage thinking

The pack derives every skill from one funnel:

Awareness, Sign-up (KYC), First deposit, Direct deposit routed, Card-as-primary, Revenue feature engagement, Referral.

Every B2C neobank's unit economics depend on interchange revenue from card swipes, with secondary revenue from net interest margin, lending, and subscription tiers. Direct deposit routing is the single best predictor of lifetime value.

When a user asks for help, locate the request in the funnel first. Then route to the right skill. A "homepage rewrite" request usually means trust-architecture-page plus neobank-copywriting plus a tone-matrix.md voice calibration. A "we need more signups" request usually means bank-aso, kyc-onboarding-cro, or direct-deposit-acquisition depending on where the leak is.

## Voice calibration

Before writing any copy, read `reference/tone-matrix.md`. It has five tone archetypes (mass consumer, premium consumer, cultural, community-transparent, niche affinity) with specific copy patterns to use and avoid for each. Match the user's neobank-context profile to the matching archetype, then write inside that lane.

## Why this exists (first principles)

Neobank marketing has its own physics. The unit economics rest on interchange. The activation funnel runs through KYC. Every clever growth tactic from a SaaS or B2B playbook needs to be re-evaluated for this surface before it ships. This pack does that re-evaluation up front.

## Disclaimer

This pack does not take compliance reviews into account. Outputs are marketing drafts only. Get your own compliance counsel and partner bank marketing review before publishing anything. This pack does not constitute legal advice and Growgami is not liable for outputs.
