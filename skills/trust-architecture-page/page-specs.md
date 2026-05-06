# Trust Architecture Page Specs

Content spec for each of the 7 pages. Build all 7 before scaling acquisition.

## 1. Security page

URL convention: /security

Required content:
- AES-256 encryption disclosure (data at rest)
- TLS 1.2+ in transit
- Biometric login (Face ID, Touch ID, Android equivalent)
- Real-time fraud alerts and how to enable
- Visa or Mastercard zero-liability protection statement (with the network's official language)
- FDIC partner bank named with certificate number
- Bug bounty program details (link to HackerOne or equivalent)
- SOC 2 Type II if applicable, with most recent audit date
- 24/7 fraud hotline number (not chatbot-only)
- How to report a lost or stolen card
- 2FA / MFA options available

Tone: confidence + specificity. "We use bank-grade security" is dead. "256-bit encryption, biometric login, real-time fraud alerts, $250K FDIC pass-through via [Bank]" is alive.

## 2. How we make money

URL convention: /how-we-make-money or /how-it-works

Required content:
- Interchange revenue: plain English explanation that merchants pay a small fee on each card swipe and the bank shares it with us.
- Net interest margin: if applicable, plain explanation that customer deposits are held at the partner bank and earn yield, a portion of which we keep.
- Premium subscription revenue: if applicable, the price and what the user gets.
- Lending revenue: if applicable.
- What we do not do: sell user data, charge hidden fees, profit from overdrafts (if true).

Reference: Monzo's version. Cite the structural categories, not just the totals. Customers want to know the model, not just the number.

## 3. Partner bank disclosure page

URL convention: /banking-services or /partner-bank

Required content:
- Partner bank legal name (or names if multiple)
- FDIC certificate number for each
- Pass-through insurance explanation: the brand is a fintech, not a bank. Funds are held at the partner bank, which is FDIC insured up to $250K per depositor.
- Multi-bank sweep handling if applicable: explain how higher coverage limits work, list each bank in the program with its FDIC certificate number.
- What happens if the brand fails (it is the partner bank that holds your money).
- What happens if the partner bank fails (FDIC standard process).

Post-Synapse the bar is explicit naming. "Banking services provided by our partner bank" without a name fails the test. The named pattern: "Banking services provided by Lead Bank, Member FDIC, Certificate #58233."

## 4. Fraud center

URL convention: /fraud or /security/fraud

Required content:
- Report fraud: phone, in-app, web form. All three.
- Common scam education: Zelle scams, romance scams, IRS impersonation, fake tech support, "your account is locked" texts. One paragraph each, plain English.
- Liability policy: what we cover, what we do not, under what timelines.
- Dispute timeline: the standard pattern most US neobanks publish is 10 business days for provisional credit on most disputes, extended to 45 days for new accounts and POS or foreign transactions. Match what your partner bank requires you to publish.
- Examples of what the brand will never do (will never call asking for your password, will never send a text with a link to log in).

This page is also a fraud-prevention surface. Customers who read it before falling for a scam are less likely to fall for it.

## 5. Status page

URL convention: status.[brand].com (subdomain, public, not gated)

Required content:
- Real-time service status: card transactions, transfers, deposits, app login, web login.
- Incident history: list of past incidents with timestamps, root cause summary, resolution.
- Planned maintenance windows.
- Subscribe to updates (email, SMS, RSS).

Reference: Monzo runs a public status page with full incident history. This is the standard. A status page that only shows "all systems operational" with no historical data signals you are hiding outages. Show them.

## 6. Dispute and complaints process

URL convention: /disputes or /complaints

Required content:
- Timeline by dispute type. Match what your partner bank publishes.
- Channels: in-app, web, phone, mail.
- Escalation path: first-line support, manager escalation, formal complaint.
- External complaint channel: most US neobanks point users to consumerfinance.gov/complaint.
- For state-licensed money transmitters: state regulator complaint paths.

Build it once, link it from the footer.

## 7. Audit and trust signals page

URL convention: /trust or /audits

Required content:
- SOC 2 Type II report status and most recent audit date (executive summary public, full report under NDA).
- PCI DSS scope and most recent attestation.
- Recent third-party security audits.
- State money transmitter licenses if applicable: list each state with license number.
- Federal registrations: FinCEN MSB if applicable.
- Privacy framework: privacy policy link, data retention policy.

Customers do not read this page often. Reporters, partner bank reviewers, and enterprise security reviewers do. Build it for them.
