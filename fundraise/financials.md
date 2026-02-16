# Financial Projections

> Last updated: Feb 16, 2026

## Status: Structure Ready — Awaiting Founder Inputs

This document contains the full financial model framework. Sections marked `[FOUNDER INPUT NEEDED]` require the founding team to provide raw numbers. Once inputs are filled, the projections, unit economics, and sensitivity analysis will be computed.

---

## Section 1: Founder Inputs Required

**Instructions:** Each founder fills in their section below. Once all inputs are provided, the financial model sections (P&L, unit economics, use of funds) will be finalized.

### 1A. Current Monthly Burn (Pre-Raise)

| Item | Monthly Cost (₹) | Notes |
|------|------------------|-------|
| Founder 1 (Ashish) — personal expenses | [FOUNDER INPUT NEEDED] | Living costs covered during build phase |
| Founder 2 (Aravind) — personal expenses | [FOUNDER INPUT NEEDED] | |
| Founder 3 (Shash) — personal expenses | [FOUNDER INPUT NEEDED] | |
| Infrastructure (Supabase, Vercel, domains) | [FOUNDER INPUT NEEDED] | Current hosting/tools spend |
| Software tools (Figma, GitHub, etc.) | [FOUNDER INPUT NEEDED] | |
| Legal/compliance (if any) | [FOUNDER INPUT NEEDED] | CA, lawyer retainer, registration fees |
| Travel/meetings | [FOUNDER INPUT NEEDED] | Venue visits, investor meetings in Bengaluru |
| Miscellaneous | [FOUNDER INPUT NEEDED] | |
| **Total Pre-Raise Monthly Burn** | **[Auto-calculated]** | |

### 1B. Fundraise Parameters

| Parameter | Value | Notes |
|-----------|-------|-------|
| Target raise amount (₹) | [FOUNDER INPUT NEEDED] | Typical Indian pre-seed: ₹1–3 Crore |
| Dilution range | [FOUNDER INPUT NEEDED] | Typical pre-seed: 10–20% |
| Target runway post-raise (months) | [FOUNDER INPUT NEEDED] | Recommended: 15–18 months |
| Target close date | April 2026 | |

### 1C. Post-Raise Monthly Burn

| Item | Monthly Cost (₹) | Start Month | Notes |
|------|------------------|-------------|-------|
| Founder 1 (Ashish) — salary | [FOUNDER INPUT NEEDED] | Month 0 | |
| Founder 2 (Aravind) — salary | [FOUNDER INPUT NEEDED] | Month 0 | |
| Founder 3 (Shash) — salary | [FOUNDER INPUT NEEDED] | Month 0 | |
| Engineer hire #1 | [FOUNDER INPUT NEEDED] | Month 1–2 | Full-stack, Bengaluru market rate |
| RM/Sales hire #1 | [FOUNDER INPUT NEEDED] | Month 2–3 | Relationship manager for venue onboarding |
| Infrastructure (scaled) | [FOUNDER INPUT NEEDED] | Month 0 | Supabase pro, Vercel pro, monitoring |
| Marketing budget | [FOUNDER INPUT NEEDED] | Month 1 | QR materials, social ads, events |
| Legal/compliance | [FOUNDER INPUT NEEDED] | Month 0 | Incorporation, CA, compliance advisor |
| Office/co-working | [FOUNDER INPUT NEEDED] | Month 0 | Or WFH — state if ₹0 |
| Miscellaneous/buffer | [FOUNDER INPUT NEEDED] | Month 0 | Recommend 10–15% of total |
| **Total Post-Raise Monthly Burn** | **[Auto-calculated]** | | |

### 1D. Revenue Assumptions

| Assumption | Value | Basis |
|-----------|-------|-------|
| Venues onboarded per month (M1–6) | [FOUNDER INPUT NEEDED] | RM capacity: ~10–15 venues/month/RM |
| Venues onboarded per month (M7–12) | [FOUNDER INPUT NEEDED] | With second RM or self-service |
| Free → Premium conversion rate | [FOUNDER INPUT NEEDED] | Industry benchmark: 5–15% |
| Monthly churn rate (venues) | [FOUNDER INPUT NEEDED] | Target: <5% |
| Premium ARPU | ~₹2,000/month | From revenue-model.md |
| Enterprise ARPU | [FOUNDER INPUT NEEDED] | Multi-location pricing |
| Average users per venue (monthly) | [FOUNDER INPUT NEEDED] | Diners who check in per venue |
| User acquisition via organic/QR (%) | [FOUNDER INPUT NEEDED] | vs. paid channels |

---

## Section 2: 18-Month P&L Projection

*To be computed from Section 1 inputs. Structure below.*

### Revenue Build-Up

| Month | Venues (Cum.) | Free | Premium | Enterprise | Monthly SaaS Revenue (₹) | Agentic Usage Revenue (₹) | Total Revenue (₹) |
|-------|--------------|------|---------|------------|--------------------------|---------------------------|-------------------|
| M1 | — | — | — | — | — | — | — |
| M2 | — | — | — | — | — | — | — |
| M3 | — | — | — | — | — | — | — |
| M4 | — | — | — | — | — | — | — |
| M5 | — | — | — | — | — | — | — |
| M6 | — | — | — | — | — | — | — |
| M7 | — | — | — | — | — | — | — |
| M8 | — | — | — | — | — | — | — |
| M9 | — | — | — | — | — | — | — |
| M10 | — | — | — | — | — | — | — |
| M11 | — | — | — | — | — | — | — |
| M12 | — | — | — | — | — | — | — |
| M13 | — | — | — | — | — | — | — |
| M14 | — | — | — | — | — | — | — |
| M15 | — | — | — | — | — | — | — |
| M16 | — | — | — | — | — | — | — |
| M17 | — | — | — | — | — | — | — |
| M18 | — | — | — | — | — | — | — |

### Monthly P&L

| Month | Revenue (₹) | Burn (₹) | Net (₹) | Cash Remaining (₹) |
|-------|-------------|----------|---------|-------------------|
| M0 | — | — | — | [Raise amount] |
| M1 | — | — | — | — |
| M2 | — | — | — | — |
| ... | ... | ... | ... | ... |
| M18 | — | — | — | — |

### Break-Even Analysis

- **Break-even monthly burn:** [Auto-calculated from inputs]
- **Venues needed at break-even:** [Auto-calculated] (premium venues at ₹2K/month + agentic usage)
- **Estimated break-even month:** [Auto-calculated]
- **Note:** Pre-seed companies are not expected to break even within 18 months. This analysis shows the path and demonstrates financial discipline.

---

## Section 3: Unit Economics

### Venue Economics

| Metric | Value | Methodology |
|--------|-------|-------------|
| **CAC per venue** | [Calculated from inputs] | (RM monthly cost + marketing allocation) / venues onboarded per month |
| **LTV per venue** | [Calculated from inputs] | Monthly ARPU × (1 / monthly churn rate) |
| **LTV:CAC ratio** | [Calculated from inputs] | Target: >3x |
| **Payback period** | [Calculated from inputs] | CAC / Monthly ARPU (months) |
| **Gross margin per venue** | [Calculated from inputs] | (Revenue - inference costs - infra allocation) / Revenue |

**Inference cost per venue:** ₹300–1,100/month (multi-model routing: Haiku for simple tasks, Sonnet for recommendations, Opus for strategy). See `product/architecture.md` for cost breakdown.

### User Economics

| Metric | Value | Methodology |
|--------|-------|-------------|
| **CAC per user** | [Calculated from inputs] | Primarily organic (QR in-venue). Paid CAC applies only to non-venue-driven acquisition |
| **LTV per user** | [Calculated from inputs] | GC transaction value × frequency × platform commission + indirect venue retention value |
| **Organic acquisition %** | [FOUNDER INPUT NEEDED] | QR check-in at venue = zero CAC. This is CheckIn's acquisition moat |

### Benchmarks (Indian Pre-Seed SaaS)

| Metric | CheckIn Target | Industry Median | Notes |
|--------|---------------|-----------------|-------|
| LTV:CAC | >3x | 3–5x | Pre-seed: demonstrate the unit economics work, even if based on assumptions |
| Monthly churn | <5% | 3–7% | F&B has higher churn risk than enterprise SaaS |
| Gross margin | >70% | 70–85% | AI inference costs are the primary COGS |
| Payback period | <6 months | 6–12 months | Low ARPU means fast payback is critical |

---

## Section 4: Use of Funds

*Breakdown based on raise amount from Section 1B.*

| Category | % Allocation | Amount (₹) | What It Covers |
|----------|-------------|------------|----------------|
| **Engineering** | [FOUNDER INPUT NEEDED] | — | Engineer hire, infrastructure scaling, AI inference costs |
| **Sales & Onboarding** | [FOUNDER INPUT NEEDED] | — | RM hire, venue onboarding materials, QR stands |
| **Marketing** | [FOUNDER INPUT NEEDED] | — | Social campaigns, events, content, influencer pilots |
| **Operations** | [FOUNDER INPUT NEEDED] | — | Founder salaries, co-working, travel |
| **Legal & Compliance** | [FOUNDER INPUT NEEDED] | — | Incorporation, CA, compliance advisory, PPI license exploration |
| **Buffer** | 10–15% | — | Contingency for unexpected costs |

**Recommended allocation for pre-seed F&B SaaS (for reference):**
- Engineering: 35–40%
- Sales/Onboarding: 20–25%
- Marketing: 10–15%
- Operations: 15–20%
- Legal: 5%
- Buffer: 10%

---

## Section 5: Sensitivity Analysis

*Three scenarios based on venue acquisition velocity.*

| Scenario | Venues at M12 | Revenue at M12 (₹/month) | Runway Consumed | Implication |
|----------|--------------|--------------------------|-----------------|-------------|
| **Bull** (15 venues/month) | ~150 | — | — | Seed-ready by M12 |
| **Base** (10 venues/month) | ~100 | — | — | Seed-ready by M15 |
| **Bear** (5 venues/month) | ~50 | — | — | Need to extend runway or pivot GTM |

**Key sensitivity drivers:**
1. Venue onboarding velocity (most impactful — directly drives revenue and user acquisition)
2. Free → Premium conversion rate (determines when SaaS revenue materializes)
3. Monthly churn rate (determines LTV and long-term revenue retention)
4. Agentic usage adoption (upside driver — higher ARPU than base SaaS)

---

## Revenue Model Summary

See `product/revenue-model.md` for detailed breakdown. Key numbers:

- Bengaluru SOM: ~2,500 premium venues
- Premium tier: ~₹2,000/month
- 10% penetration = ₹0.6 Crore/year SaaS revenue
- 30% penetration = ₹1.8 Crore/year SaaS revenue
- Phase 2 adds Commission Arbitrage + Breakage + Transaction Fee revenue

---

Sources: product/revenue-model.md, product/architecture.md (inference costs), Checkin: Investor Pitch Deck
