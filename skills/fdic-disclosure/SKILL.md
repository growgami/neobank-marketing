---
name: fdic-disclosure
description: Partner bank and FDIC disclosure review. Auto-triggers when copy mentions FDIC, deposit insurance, partner bank, or sponsor bank. Catches the misrepresentations that get fintechs banned.
argument-hint: "[copy or product context, partner bank name]"
user-invocable: true
disable-model-invocation: false
---

# FDIC and Partner Bank Disclosure

## Why this exists (first principles)

Most "neobanks" are not banks. They are fintechs that hold customer deposits at a partner or sponsor bank. The FDIC insures the bank, not the fintech. The difference between safe and dangerous copy is one sentence.

What happens when this is missed:

- **Synapse, April 2024**: Synapse Financial Technologies filed Chapter 11. Customer funds at non-bank fintechs that relied on Synapse for ledgering were frozen. Reporting from the bankruptcy trustee and CFPB indicated more than $200M in customer money was inaccessible across multiple programs (Yotta, Juno, others). Customers had read FDIC language on those apps and assumed they were covered. They were not, in the way they thought.
- **Beam Financial, March 2021**: FTC action banned founder for life. Beam claimed FDIC coverage while customer funds sat in a non-bank structure that did not deliver pass-through insurance.
- **FDIC enforcement Q1-Q2 2024**: cease-and-desist letters to fintechs whose marketing implied they were FDIC-insured banks.

The rule for copy: never let a customer believe the fintech itself is FDIC-insured.

## The required disclosure pattern

Canonical: **"Banking services provided by [Partner Bank Name], Member FDIC."**

Use the partner bank's exact legal name. Place close to any deposit, balance, or savings claim.

### Variations by surface

- **Web footer**: "Banking services provided by [Bank], Member FDIC. [Brand] is a financial technology company, not a bank."
- **Signup screen**: at the top of the deposit step: "Your funds will be held at [Bank], Member FDIC."
- **Ad creative**: in the disclosure footer of the asset, sized and contrasted to be readable: "Banking services by [Bank], Member FDIC."
- **App store description**: in the body of the listing: "[Brand] is a financial technology company, not a bank. Banking services provided by [Bank], Member FDIC."
- **Push notification**: skip the FDIC claim entirely. Push has no room for adequate disclosure. Drive to a screen that does.
- **Email transactional**: footer: "Banking services provided by [Bank], Member FDIC."

### Wrong patterns (banned on sight)

- "FDIC insured" with no partner bank name
- "Your money is FDIC protected" applied to the fintech
- "We are FDIC insured"
- "[Brand] is FDIC insured"
- Mixing FDIC and SIPC ("FDIC and SIPC insured up to $X") without clarifying which product is which
- Using the FDIC logo without authorization (FDIC Part 328 controls signage)

## Multi-bank sweep networks

Many neobanks use sweep programs that distribute deposits across multiple partner banks for higher coverage caps. Rules:

- Disclose pass-through insurance is conditional on customer records, agency relationship, and FDIC requirements being met.
- Name every bank in the network, or link to a maintained list.
- Show the per-customer per-bank FDIC limit ($250K). The "up to $X million in FDIC coverage" claim must specify it is achieved by spreading across N banks.
- Pattern: "Funds are swept across a network of banks. See the current list at [URL]. Coverage up to $[N]M is achieved via FDIC pass-through across these banks, $250K per bank per customer, subject to standard FDIC rules."

## Post-Synapse posture

After the Synapse collapse, transparency about partner banks is the new minimum bar.

Mercury's public posture in 2024: "We became acutely aware that having direct relationships with our partner banks was in the best interest of our customers." They consolidated and named partners publicly.

Recommendations:

1. Public page that names every partner bank, dated.
2. In-app screen showing where the customer's specific funds are held.
3. Clear separation in copy: "[Brand] is a fintech. [Bank] is the bank. The bank holds the money."

## Compliance and human review

These skills have not been reviewed by banking compliance counsel. Treat all output as a starting point only.

This skill produces drafts, not legal artifacts. Every output must be reviewed by qualified compliance counsel and your partner bank's marketing review team before publishing. Specifically check: 12 CFR Part 330 (FDIC pass-through insurance), FDIC Part 328 (deposit insurance representation and advertising), 12 USC 1828(a). This pack does not constitute legal advice and Growgami is not liable for outputs.
