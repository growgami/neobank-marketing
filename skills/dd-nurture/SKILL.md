---
name: dd-nurture
description: Lifecycle email and push for B2C neobank users who have routed direct deposit. Triggers when designing post-DD activation flows, writing payday push copy, building dormant-DD win-back, or planning the first-30-days nurture.
argument-hint: "[neobank name + lifecycle stage]"
user-invocable: true
disable-model-invocation: false
---

# DD Nurture

## Why this exists (first principles)

Once a user routes direct deposit to the neobank, the product job changes. Acquisition is over. The next goal is card-as-primary behavior. Every interchange swipe is revenue. Every external transfer to a competitor neobank is revenue lost.

Engagement signal hierarchy after DD:
1. Payday → app open
2. First-week swipes (count and merchant variety)
3. Round-up adoption
4. Savings goal creation
5. Secondary feature engagement (SpotMe / overdraft, credit-builder, investing)

Multi-neobank reality: roughly 39 percent of US neobank users hold 2+ neobank accounts. Only the primary-DD bank gets the card swipes. The other accounts become single-feature utilities (savings, credit-builder, P2P). The nurture sequence is competing for "primary card in the wallet" status, not just "active app on the phone."

If the lifecycle program does not move card swipes per DD-routed user upward in the first 30 days, it is not nurturing. It is filler.

## Trigger map

Detailed copy templates for each trigger live in `sequence-templates.md` in this folder. Summary below.

1. **DD detected (first time)**: welcome message, "your paycheck just arrived [2 days early]," explain features now available. Push + email within 1 hour of credit.
2. **Payday recurring (every DD)**: "Paycheck day. $X just hit your account." Push only. Drives same-day card use.
3. **End-of-week summary**: spending breakdown, savings nudge, top merchants. Email Sunday morning.
4. **Round-up activation prompt**: 7 days post first DD. In-app + push.
5. **Savings goal creation**: 14 days post first DD. Email + in-app.
6. **Feature discovery sequence**: SpotMe / overdraft (week 2), credit-builder (week 3), investing or yield product (week 4) if available. One feature per week, not bundled.
7. **Dormant DD signal**: 30 days no card use post-DD triggers re-engagement push + email.
8. **DD stopped**: 35 days no DD inflow triggers win-back $25 bonus offer + employer-change support.

## Channel split

- **Push**: time-sensitive, high-trust, transactional-feeling
  - Payday credits
  - Card declines
  - Fraud alerts
  - Same-day balance milestones
  - Round-up celebration

- **Email**: narrative, longer-form, weekly cadence
  - Weekly spending summary
  - Milestone celebrations (first $1,000 saved)
  - Win-back sequences
  - Feature deep-dives

- **In-app**: feature discovery, contextual
  - Round-up prompt after first paycheck deposit
  - Savings goal creation when balance crosses threshold
  - Credit-builder activation when DD stable for 60+ days
  - SpotMe / overdraft offer when balance dips low

## TCPA compliance for SMS and push

Push notifications generally fall outside TCPA but enter scope when carrying marketing content to phone numbers obtained for transactional reasons. SMS is in scope. Both require:

- **Explicit opt-in** at signup, separate checkbox for marketing vs transactional
- **Easy opt-out**: STOP keyword for SMS, in-app toggle for push, every marketing message must reference how to opt out
- **Transactional vs marketing classification**: payday credit notification = transactional. Round-up activation prompt = marketing. Separate consent for each. Do not send marketing under transactional consent. The CFPB and FTC both look at this.

Consent record: keep timestamped record of opt-in source, channel, and version of consent language for 4+ years.

## Frequency caps

- Push: max 1 marketing push per day. Transactional pushes (DD credit, fraud alert, card declined) do not count against the cap.
- Email: max 3 marketing emails per week. Transactional emails (statement, password reset, security alert) do not count.
- SMS: max 1 marketing SMS per week. Transactional SMS (2FA, fraud confirmation) do not count.
- In-app: 1 prompt per session, max 3 prompts per week per surface.

Never stack a push + email + in-app on the same prompt the same day. Sequence them: push first, email if no action in 24h, in-app on next session.

## Output format: 30-day DD nurture sequence

Full template lives at `sequence-templates.md` in this folder. Brief structure:

```
30-DAY DD NURTURE SEQUENCE

Neobank: [name]
Audience: First-time DD-routed users
Goal: Card-as-primary behavior by day 30

Day 0 (DD detected):
- Push: [copy]
- Email: [subject + body]

Day 1:
- ...

Day 7 (Round-up prompt):
- ...

Day 14 (Savings goal):
- ...

Day 21 (Feature discovery 2):
- ...

Day 28 (Feature discovery 3):
- ...

Day 30 dormancy check:
- Trigger: [no card use 7+ days]
- Re-engagement: ...

Send rules:
- Frequency caps:
- Channel split:
- Suppression rules:
- Time-of-day:

Compliance review owner:
```

See `sequence-templates.md` for the full 30-day sequence with copy.

## Compliance and human review

This skill produces lifecycle marketing copy and trigger logic. It does not produce legally sufficient disclosures. Every output of this skill must be reviewed by qualified counsel and the compliance team before going live.

Regulations that apply:
- TCPA (47 USC 227 + 47 CFR 64.1200): SMS and push that carry marketing content require prior express consent. Transactional vs marketing classification matters. Opt-out must be honored within 10 business days.
- CAN-SPAM (15 USC 7701): every marketing email needs accurate from/subject lines, physical mailing address, and a working unsubscribe link honored within 10 business days.
- Reg E (12 CFR 1005): any transactional content (DD credits, transfer notifications, dispute language) must comply with electronic fund transfer rules, including error resolution and unauthorized transfer notices.
- CFPB UDAAP: any retention, "save more," "earn more," or speed-of-funds claim. Win-back bonuses must follow the same disclosure rules as acquisition bonuses.
- State PII / privacy laws: CCPA/CPRA, Virginia CDPA, Colorado CPA all apply to lifecycle data use. Honor opt-out of sale/share where relevant.

Do not ship copy or triggers without sign-off from counsel, compliance, and the bank partner if applicable.
