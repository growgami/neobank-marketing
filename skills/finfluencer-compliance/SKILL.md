---
name: finfluencer-compliance
description: Creator and influencer content compliance review. Auto-triggers when copy mentions influencer, creator, finfluencer, sponsored content, brand deal, or paid partnership. Covers FTC, FINRA, and platform-specific rules.
argument-hint: "[creator brief or content, platform, product context]"
user-invocable: true
disable-model-invocation: false
---

# Finfluencer Compliance

## Why this exists (first principles)

The FTC's 2023 endorsement guide update, FINRA Rule 2210, and the FTC's fake review rule (effective October 21 2024) made paid creator content the highest-risk channel in fintech marketing. AI-generated personas making financial claims fall under the fake review ban explicitly.

Recent enforcement:

- **TradeZero America, June 2024**: $250,000 FINRA fine in part for failures in supervising and recordkeeping social media posts by paid promoters.
- **2024 SEC and FINRA finfluencer sweeps**: multiple firms hit for paid creator programs without principal review, archived recordkeeping, or proper disclosure. Civil penalties ranged into the high six figures across the sweep.
- **FTC Endorsement Guide update, 2023**: clarified "clear and conspicuous" disclosure requirements, expanded liability to platforms and brands, applied to all paid creator content including likes-for-pay.

If a neobank touches investing or brokerage features, every creator post is a "communication with the public" under FINRA Rule 2210 and triggers a separate compliance regime.

## Required disclosure pattern: clear and conspicuous

The FTC's "clear and conspicuous" standard is specific. Disclosure cannot be:

- Buried in hashtag stacks
- After "more" truncation
- In a different language than the post
- Smaller than the surrounding text
- Off-screen, behind another element, or auto-dismissed

Acceptable formats:

- "#ad" at the start of the caption (acceptable, not "#partner" alone, not "#sp," not "#collab," not "#thanksbrand")
- "Paid partnership with [Brand]" using platform tagging
- On-screen text "#ad" or "Paid partnership" present for at least 3 seconds in video

### Platform-specific patterns

- **TikTok**: Branded Content toggle ON + "#ad" in caption start + on-screen "Paid partnership" overlay during the disclosure window.
- **Instagram and Reels**: Paid Partnership label via tagging tool + "#ad" in caption start + on-screen text during video.
- **X (Twitter)**: "Ad" label via X paid partnership tools + "#ad" at the start of the post.
- **YouTube**: Includes Paid Promotion checkbox ON in YouTube studio + verbal "this video is sponsored by [Brand]" within the first 30 seconds + on-screen text during the sponsored segment.
- **Long-form podcasts**: verbal disclosure at the start of the sponsored segment, not buried in the show notes.

## Required brief / contract elements

Every creator brief and contract must include:

1. **Pre-approval of content**. No live posts without brand and compliance review of the final cut and caption.
2. **No specific yield, return, or earnings claims**. Creators cannot say "I earned X%" or "you'll make $Y." They can describe features and their experience.
3. **No testimonials about features that do not exist or are not generally available**. No claims about beta features, no implying speed/coverage that does not match disclosed reality.
4. **Disclosure mandatory and platform-specific**. Spell out the exact format per platform.
5. **FTC and FINRA review acknowledgment**. Creator signs that they understand obligations.
6. **Takedown clause: 24 hours**. Creator agrees to take down or amend any post within 24 hours of a regulator complaint or brand request, regardless of cause.
7. **Recordkeeping**. Brand retains all final cuts, captions, and approval logs for the FINRA-required period (3 years for 2210, longer for some categories).
8. **No claim about FDIC insurance, guaranteed returns, or risk-free language**.

## AI persona and synthetic creators

Prohibited for fintech use.

Why:

- The FTC fake review rule (effective October 21 2024) prohibits AI-generated reviews and testimonials presented as real.
- UDAAP: a synthetic persona endorsing a deposit product is deceptive.
- An AI-generated character cannot meaningfully comply with disclosure rules because they have no "endorser" to be accountable.

Even AI b-roll or AI voice in an otherwise human creator's post should be flagged and disclosed if the AI element would mislead the viewer about who is endorsing the product.

## FINRA Rule 2210 specifics

If the neobank offers any investing, brokerage, or securities feature, every paid creator post is a "retail communication" under FINRA Rule 2210.

Required:

- **Principal review** by a registered principal at the broker-dealer before posting
- **Recordkeeping**: 3 years minimum, including final asset, caption, approval log, and creator agreement
- **No promissory or unwarranted claims**: no "guaranteed," no projected returns, no implied risk-free
- **Balance**: risk disclosure must accompany any benefit claim
- **Compliance with content standards** for performance, comparisons, ranking claims

A paid TikTok by a finfluencer about a brokerage product without principal review is a textbook FINRA case.

## Output format

```
FINFLUENCER REVIEW: [creator] | [platform] | [date]

DISCLOSURE CHECK:
  - Format used: [#ad / Paid Partnership / etc.]
  - Position: [caption start / on-screen / verbal] pass / fail
  - Duration on-screen: [X seconds] pass / fail (need 3+)

CLAIM REVIEW:
  - Yield/return claims: [list, action]
  - Feature claims: [list, action]
  - Testimonial accuracy: [pass / fix]

CONTRACT CHECK:
  - Pre-approval clause: [present / missing]
  - Takedown 24h clause: [present / missing]
  - Recordkeeping: [present / missing]

FINRA APPLICABLE: yes / no
  If yes, Principal review status: [done / pending]

VERDICT: SHIP / FIX / KILL
```

## Compliance and human review

These skills have not been reviewed by banking compliance counsel. Treat all output as a starting point only.

This skill produces drafts, not legal artifacts. Every output must be reviewed by qualified compliance counsel and your partner bank's marketing review team before publishing. Specifically check: FTC Endorsement Guides 16 CFR Part 255, FTC Fake Reviews Rule (effective October 21 2024), FINRA Rule 2210, SEC Marketing Rule 206(4)-1 if RIA-adjacent. This pack does not constitute legal advice and Growgami is not liable for outputs.
