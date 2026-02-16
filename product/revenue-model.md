# Revenue Model

> Last synthesized: Feb 16, 2026

## Phase 1: Smart SaaS (Months 0–18)

**Freemium Model** drives rapid venue adoption and network density.

| Tier | Pricing | Features |
|------|---------|----------|
| **Free** | ₹0/month | Basic check-in, limited quests, core leaderboard, basic analytics |
| **Premium** | ~₹2,000/month | Advanced quest customization, deep analytics, customer segmentation, targeted communication, community management |
| **Enterprise** | ₹8,000–15,000/month per location | Multi-location dashboard, Chain VCs, advanced CRM, API access, dedicated support, custom integrations |

**Plugin Marketplace:** Specialized add-on modules (karaoke, table booking, advanced feedback, event management) drive additional ARPU.

**Value-Added Services (one-time):** Setup assistance, custom QR stands, branded promotional materials.

## Phase 2: Ecosystem Monetization — Credit Economy Revenue (Months 18+)

CheckIn's revenue from the credit economy is outcome-based — it grows as the economy circulates, not as a flat subscription tax.

### Revenue Stream Mix

| Stream | Description | Margin Profile |
|--------|-------------|----------------|
| **VC Circulation Fee** | CheckIn takes a % cut each time VCs complete a circulation cycle (earned → redeemed → recirculated) | High margin (~30-40%) |
| **GC Minting Fee** | When brands fund GC campaigns, CheckIn retains 15-20% as a platform/service fee before minting GCs | Very high margin (~90%) |
| **GC Redemption Spread** | CheckIn reimburses venues at a rate below face value when GCs are redeemed (e.g., ₹0.85 per GC). The spread is margin. | Moderate margin |
| **Breakage** | Expired/unredeemed credits = pure revenue for CheckIn. No supply = no GST (per CBIC Circular 243/37/2024) | 100% margin |
| **Swap Fees** | % cut on GC→VC conversions | High margin |
| **SaaS Base** | Monthly subscription fees (payable in cash or partially in accumulated VCs) | ~90% margin |
| **Payment Processing** | If CheckIn provides payment gateway services, per-transaction processing fee applies | Low margin (1-2%) — infrastructure cost recovery |

### Brand-Funded GC Campaign — Unit Economics

Per ₹100 brand spend:
- ₹20.00 — CheckIn platform fee (captured immediately)
- ₹54.40 — Venue reimbursements (₹0.85 × 64 GCs redeemed, assuming 80% redemption)
- ₹9.60 — CheckIn spread on redeemed GCs (₹0.15 × 64)
- ₹16.00 — Breakage revenue (unredeemed GCs)
- **Total CheckIn revenue: ₹45.60 per ₹100 brand spend**

### Future Revenue Streams
- **Transaction Marketplace:** Commission on event tickets, table bookings, exclusive memberships sold through platform
- **Intelligence Layer:** Premium analytics and AI-driven predictive insights (the "ultimate prize")
- **Delivery-as-a-Service:** Subscription-based delivery logistics (Phase 3+)

## Agentic Revenue Model

Traditional SaaS charges a flat subscription. CheckIn's revenue grows as the AI does more:

- **Month 1:** Base platform, basic quests → ₹3,000/month
- **Month 3:** AI runs campaigns, personalized recommendations → ₹3,000 base + ₹2,000 usage
- **Month 6:** Full autonomy, inventory-linked quests, 2 plugins active → ₹3,000 base + ₹4,000 usage + ₹1,500 plugin revenue

Revenue correlates with value delivered. More engagement = more revenue = proof of value.

## Pricing Philosophy

**Core revenue from SaaS tiers + agentic usage, NOT from taxing food transactions.** This is a critical strategic decision:
- Venues associate variable commissions with Zomato/Swiggy exploitation
- Per Porter's analysis: if CheckIn charges >10% success fees, venues view it as "Zomato 2.0"
- SaaS + agentic usage positions CheckIn as a partner/tool, not another aggregator extracting value
- **Payment gateway exception:** If CheckIn provides payment gateway services (for VC redemption, in-app ordering, etc.), a per-transaction processing fee applies — this covers infrastructure costs, not a commission on food sales

## Unit Economics

**User LTV:** Projected 3x higher than standard aggregator users due to:
- Venue Credit lock-in (venue-specific credits can't leave)
- GC sunk cost fallacy (accumulated credits discourage churn)
- Social graph stickiness (friends on platform create switching costs)

**Venue Willingness to Pay:**
- Venues already allocate 3–6% of revenue to marketing (10–15% for new establishments)
- Currently paying 15–30% to aggregators — massive reallocation opportunity
- Customer discovery hypothesis: ₹3–5K/month (most venues), ₹5–10K (higher revenue)

## SOM Revenue Projections (Bengaluru)

Bengaluru target: ~2,500 premium Gen-Z-focused venues

| Penetration | Venues | Annual SaaS Revenue |
|-------------|--------|-------------------|
| 10% | 250 | ₹0.6 Crore (~USD 72K) |
| 30% | 750 | ₹1.8 Crore (~USD 216K) |
| 50% | 1,250 | ₹3.0 Crore (~USD 360K) |

*Note: These are SaaS-only projections. Ad platform and transaction revenue would be additive.*

**National Scale:** 10,000–15,000 premium venues across Top 7 Tier-1 cities at 10–20% penetration = ₹2.4–7.2 Crore in premium SaaS alone.

## Financial Projections

Full P&L model, unit economics, and burn rate projections are in `fundraise/financials.md`. Key unit economics summary:

| Metric | Estimate | Methodology |
|--------|----------|-------------|
| **CAC per venue** | See `fundraise/financials.md` | (RM cost + marketing allocation) / venues onboarded per month |
| **LTV per venue (Premium)** | ₹2,000 × (1 / churn rate) | Monthly ARPU × expected lifetime |
| **LTV per venue (with agentic)** | ₹5,000–8,500 × (1 / churn rate) | ARPU grows as AI usage increases |
| **Gross margin** | >70% target | Revenue minus inference costs (₹300–1,100/venue) and infra |
| **Payback period** | <6 months target | CAC / Monthly ARPU |

**Agentic ARPU progression** is the key financial story: base SaaS (₹3K) → AI campaigns (₹5K) → full autonomy + plugins (₹8.5K). Revenue grows as AI delivers more value, without proportional cost increase (inference costs scale sub-linearly with usage).

---

Sources: Checkin: Investor Pitch Deck (Full Script & Content), Checking V2-Working Doc, GC/VC Specific - Utility and Compliance, Customer Discovery v2 Final
