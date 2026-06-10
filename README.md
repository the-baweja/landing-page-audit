# Landing Page Audit — Find the Real Leak in Your Post-Click Experience

**Audit Meta/Facebook ad landing pages for conversion. Most landing page failures are congruency failures, not structural ones. This skill applies the Congruency Doctrine (the "red shoe" rule), runs the Conversion Razor on every element, and uses real Microsoft Clarity session data to find where users actually drop off.**

## Install

**Claude Desktop (Cowork):** download [`landing-page-audit.skill`](https://github.com/the-baweja/landing-page-audit/releases/latest) → Settings → Skills → drop it in.

**Claude Code:**

```
git clone https://github.com/the-baweja/landing-page-audit.git ~/.claude/skills/landing-page-audit
```

**Manual:** clone this repo into any skills directory your Claude setup reads from.

## Why this skill exists

Facebook can only provide exposure. What happens after they leave Facebook is much more important. The landing page does the converting, not the ad. So before re-running ad-side experiments, you audit the post-click flow.

And the doctrine this skill operates on: **most LP failures are congruency failures, not structural ones.** Fixing other elements with broken congruency is wasted production budget.

## The Congruency Doctrine — the red shoe rule

If the ad shows a red shoe, the landing page must show a red shoe above the fold. Missing congruency or wrong audience kills conversion despite good CTR. The moment congruency breaks, the winner becomes a loser.

Every audit starts here. If congruency is broken (score < 5), the report stops the deep audit and routes immediately to ad rewrite or LP rewrite.

## What it does

1. **Preflight Check + Setup Runbook** — detects what's connected (Microsoft Clarity MCP, browser MCP, ad creative source), gives install paths for anything missing
2. **3-tier Data Import** — Microsoft Clarity MCP (session recordings + heatmap + analytics) → screenshot + browser fallback → manual paste
3. **Page-Type Classification** — Lead-magnet / Application / Sales page. Each gets a different audit depth. Per the Three LP Categories rule, a lead-magnet page that's too long underperforms (a control-vs-test lifted CVR from 2.32% to 3.51% just by simplifying)
4. **The 6-Step Audit:**
   - Step 1: The Congruency Check (the red shoe rule)
   - Step 2: The Conversion Razor — "if this element doesn't directly increase opt-in %, cut it"
   - Step 3: The Visual Hierarchy Predictive Heatmap — Headline → Sub-headline → Hero → CTA → Form Stack
   - Step 4: The Trust + Objection Handling Audit — Burden of Proof on Business (AG1 gold standard)
   - Step 5: The CTA + Friction Audit (with the Friction-as-Lead-Quality counter-intuitive rule)
   - Step 6: The Mobile + CPLPV Ratio Audit (one-number diagnostic: <70% broken, <80% needs work, 90%+ awesome)
5. **Series handoffs** — every leak routes back to the upstream skill that fixes it (Ad Copy Writer, Ad Hook Generator, Creative Performance Audit, etc.)

## The Burden of Proof Hierarchy

It is the marketer's job to prove the claim, not the prospect's job to believe it. The AG1 gold standard — clinical study, 50k+ reviews, ICP-relatable testimonials, "feel the difference or it's on us" guarantee — is the benchmark.

Proof strength hierarchy: **clinical / scientific** (strongest) → **volume reviews + star rating** → **ICP-relatable testimonials** → **founder authority + transparency** → **celebrity endorsements** (weakest — prospects know it's paid) → **generic "as seen in" logos** (weak unless logos match ICP).

## Output

A branded DOCX report with:

- Preflight Check Summary with confidence-flagging per finding
- The Congruency Spotlight — side-by-side ad ↔ LP comparison
- Executive Summary with overall page score + headline finding + top 3 actions
- Page-Type Classification with applied audit depth + benchmark cell
- CPLPV Ratio Health Check (one-number page-health diagnostic)
- Per-section diagnostic cards: signal, score, what's broken, clickable prescription steps, expected outcome, downstream skill handoff, what NOT to do
- Action Plan with step-by-step instructions + "what failure looks like" warning boxes
- Pattern Analysis — Winner DNA across account high-CR pages + Loser DNA across low-CR pages
- Quick Wins vs Rebuilds — fixes separated by effort
- Series Handoffs page — every leak routed back to the upstream skill that fixes it
- Contrarian Insight — one finding that contradicts conventional CRO wisdom

## Customize Your Branding

Edit `references/branding.md` with your own brand colors, typography, and document structure. The skill reads this file to generate reports that match your brand identity.

## Example

Prompt:

```
Audit the landing page at <URL>.
The ad driving traffic is <ad URL or screenshot>.
This is a direct-sales page.
```

Output: Preflight Check confirmed Microsoft Clarity MCP + browser MCP available. Pulled last 30 days of session data — 1,247 sessions, 22 longest sessions reviewed for drop-off patterns, 18 highest-click sessions reviewed for rage-click signals. Page-type: direct sales. Congruency score: 4/10 — the ad promises "Clear skin in 30 days with our 5-step routine" but the landing page hero says "Welcome to Pure Botanicals" with a brand-story video. Stopping deep audit; routing to Ad Copy Writer for hero rewrite. CPLPV ratio: 78% (needs work — page-load speed is 4.2s on mobile, fix this in parallel). Once congruency is fixed, the deep audit re-runs on Step 3+.

## Who this is for

Media buyers, founders, and creative strategists who suspect their landing page is leaking conversions but don't know where. The Congruency Doctrine + Conversion Razor + Clarity session data combination finds the leak in under 10 minutes — and routes it to the right downstream skill for the fix.

This is skill 10 of 10 in the **AI Skills for Media Buyers** series by [Baweja Media](https://bawejamedia.com). The series is complete with this skill.

---

## Want Baweja Media to audit your landing page and run the full media-buying stack on your account?

[→ Book a strategy call](https://webinar.sannidhyabaweja.com/vsl-lp-ind)

---

Built by [Baweja Media](https://bawejamedia.com) · MIT License
