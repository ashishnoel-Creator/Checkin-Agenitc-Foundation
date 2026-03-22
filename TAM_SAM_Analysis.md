# CheckIn TAM/SAM Critical Analysis & Expansion Roadmap

> Prepared: February 25, 2026
> Context: VC feedback that current TAM is too small for investment. Analysis of conservative assumptions and defensible expansion paths.

## The VC's Concern — And Why They're Partly Right

Your current thesis presents the F&B India beachhead TAM at **$1.24B** (₹4,800 Cr in thesis text, $1,243M in Excel model — note these don't match, which itself is an issue to fix) and SAM at **$207M**. The VC's reaction is predictable: at pre-seed, institutional investors want to see a path to a **$1B+ SAM** because their fund math requires portfolio companies that can become $100M+ revenue businesses. A $207M SAM caps your theoretical revenue ceiling too low for most funds to get excited.

But here's the thing — **your model is genuinely too conservative**, and not in a hand-wavy "just make the numbers bigger" way. There are specific, defensible methodological choices you've made that systematically undercount the opportunity.

---

## Part 1: What You're Doing Right

Before critiquing, credit where it's due — several things in your TAM model are strong:

**Bottom-up ARPU construction is excellent.** The Standard Tier breakdown (SaaS $47 + MDR $40 + Agentic $18 + Bookings $24 + Plugins $6 = $135/month) is detailed, sourced, and internally consistent. VCs love seeing that you've thought through each revenue line item with real math behind it.

**Source documentation is thorough.** The Sources sheet with 16 references — NRAI, IBEF, Mordor Intelligence, MarketsandMarkets — shows rigorous research. Most pre-seed decks cite 2-3 sources; you have proper institutional data.

**The tiered ARPU blend is smart.** Acknowledging that 55% of venues would be on a Light tier ($29/mo) rather than assuming everyone pays premium pricing shows intellectual honesty.

**Global TAM benchmarking from 7 research firms** with median calculation is methodologically sound.

---

## Part 2: Where You're Being Too Conservative (The Specific Problems)

### Problem 1: The Thesis Text and Excel Model Don't Match

Your thesis says: "400,000 organized dine-in venues → ₹4,800 Cr (~$565M) TAM at blended ARPU ₹10K/month"

Your Excel model says: "1,200,000 venues → $1,243M TAM at blended ARPU $86/month"

These are different numbers telling different stories. The Excel is more defensible (bigger venue count, properly built ARPU), but the thesis quotes a *smaller* number. **Fix this immediately** — an investor who reads the thesis and then opens the Excel will see a contradiction. Use the Excel numbers as the source of truth and update the thesis.

### Problem 2: Your F&B Venue Count Is Actually Conservative — But Your SAM Is Artificially Small

Your TAM uses 1.2M venues (800K organized + 400K semi-organized). This is reasonable given NRAI data. The issue is your SAM: **200,000 venues across 20 cities at 10,000 venues per city**.

Here's the problem: Mumbai alone has 141,000+ restaurants (you cite this in your own Sources sheet). Bengaluru has 60,000+. Delhi NCR has 80,000+. Your "10,000 qualifying venues per city" assumption massively undercounts the top metros while overcounting smaller cities. A tiered city approach would be more accurate:

- Tier 1 (Mumbai, Delhi, Bengaluru, Hyderabad, Chennai, Pune): ~40,000-50,000 qualifying venues each = 240,000-300,000
- Tier 2 (Kolkata, Ahmedabad, Jaipur, Lucknow, etc., 14 more cities): ~5,000-10,000 each = 70,000-140,000

A more realistic SAM venue count is **310,000-440,000 venues**, not 200,000.

### Problem 3: You're Sizing TAM as "What Venues Would Pay for CheckIn" Instead of "What Venues Currently Spend"

This is the biggest methodological issue. Your TAM counts *your projected ARPU* × *venue count*. That gives you the revenue CheckIn could capture. But VCs think about TAM as the **total current spend** on the problem you're solving.

Venues currently spend on:
- Aggregator commissions (15-28% of delivery revenue + dine-in discounts)
- Marketing (3-6% of revenue, higher for new venues)
- Existing loyalty/CRM tools (Reelo, Hashtag, etc.)
- Table booking platforms
- POS systems (the engagement portion)

For a mid-range venue doing ₹15-20L/month revenue, the spend on customer acquisition and retention is ₹50,000-200,000/month (aggregator fees alone). Your ARPU of $86/month ($134 for Standard tier) captures a *tiny fraction* of this spend. The real TAM question is: what is the total addressable *wallet* for customer engagement and relationship management?

For 1.2M organized/semi-organized F&B venues with an average engagement-related spend of ₹20,000-50,000/month (aggregator commissions + marketing + tools), the F&B engagement TAM is **$3.4B-$8.5B**, not $1.2B.

### Problem 4: You Present Multi-Vertical as an Afterthought, Not as the TAM

Your Excel has a Multi-Vertical India sheet showing $2.2B across F&B + Retail + Wellness + Entertainment. But your thesis says "F&B represents the beachhead market" and only quotes the F&B number as the TAM. Your summary sheet mentions it but buries it.

This is exactly backward from how successful platform companies pitch. Zomato didn't pitch "food delivery in Gurugram." Stripe didn't pitch "payment processing for Y Combinator startups." **They pitched the platform opportunity, with the beachhead as the proving ground.**

Your TAM summary should lead with the platform opportunity: $2.2B India venue engagement (multi-vertical) → with $31B global loyalty market context → then narrow to "we start with F&B, here's why, here's the $1.2B beachhead."

### Problem 5: The Consumer Revenue Side Is Completely Missing from TAM

Your entire TAM model is venue-side (B2B) only. But CheckIn has a two-sided business model. The consumer-side revenue streams — brand-sponsored quests, GC campaigns, the 45.6% take rate on brand spend — are potentially *larger* than the venue SaaS revenue, and they're not counted in your TAM at all.

India's digital advertising market is $6-8B and growing 20%+ annually. Brand-funded loyalty campaigns are a subset of this. Even if CheckIn captures 0.5-1% of F&B-related brand marketing spend, that's a meaningful revenue stream that should be reflected in the TAM.

### Problem 6: Your Multi-Vertical ARPU Assumptions Are Very Conservative

- Retail ARPU: $59/month (vs. F&B $86). Why would retail be lower? Fashion retail with average bills of ₹2,000-5,000 has *higher* transaction values and *higher* willingness to pay for loyalty tools.
- Wellness ARPU: $47/month. Gym memberships are ₹2,000-10,000/month. A gym paying $47/month for a retention platform that reduces churn by even 5% would see massive ROI.
- Entertainment ARPU: $94/month. This one is actually reasonable.

---

## Part 3: How to Defensibly Increase the TAM/SAM

Here are three progressively ambitious reframes, all defensible:

### Option A: Fix the Methodology, Keep F&B Focus → ~$2.5-3B TAM, ~$500M SAM

Changes:
1. **Fix SAM venue count** to 350,000 (tiered city approach)
2. **Reframe ARPU as "wallet share"** — your Standard tier is $134/month, but the venue's total engagement spend is $300-500/month. Your TAM should reflect the addressable wallet, not just your initial pricing.
3. **Add consumer-side revenue** — brand-sponsored quests, GC campaigns at even modest penetration
4. This gets you to ~$2.5-3B TAM with a $500M+ SAM

### Option B: Lead with Multi-Vertical Platform → ~$5-7B TAM, ~$1B SAM

Changes:
1. Everything in Option A
2. **Lead with the multi-vertical TAM** ($2.2B from your Excel, but re-calculated with corrected ARPU assumptions → ~$4-5B)
3. **Add India loyalty/engagement market** context ($3.45B in 2025 → $7.18B by 2030 per Globe Newswire/ResearchAndMarkets)
4. **Frame F&B as the beachhead** with clear expansion triggers for retail, wellness, events
5. This gets you to a $5-7B TAM with credible $1B+ SAM — firmly in territory that excites seed and Series A investors

### Option C: "Engagement Infrastructure" Platform Play → $10B+ TAM

Changes:
1. Everything in Option B
2. **Reframe CheckIn as "engagement infrastructure for the physical economy"** — not a loyalty tool, not a CRM, but the *operating system* for how physical venues build customer relationships
3. Reference the $31B global loyalty market as the ultimate TAM
4. India's share (APAC is 31% of global, India is the fastest-growing market in APAC) = $3-5B loyalty software + $3-4B adjacent engagement spend
5. This is the Zomato-style pitch: big vision, clear beachhead, platform economics

**My recommendation: Option B.** It's ambitious enough to satisfy VC fund math, but every number is defensible with existing data. Option C risks looking like hand-waving at pre-seed. Option A, while honest, still might not clear the bar.

---

## Part 4: Specific Fixes for the Excel Model

### Fix 1: Reconcile Thesis and Excel Numbers
The thesis quotes ₹4,800 Cr (~$565M) TAM. The Excel shows $1,243M. Pick one. The Excel is more defensible. Update the thesis.

### Fix 2: Add a "Current Market Spend" TAM Layer
Add a row/sheet that shows: "Total venue spend on customer engagement (aggregator fees + marketing + tools)" — this is the *real* TAM. Your current approach (your ARPU × venues) understates the market because you're pricing below what venues currently spend.

### Fix 3: Restructure the SAM Calculation
Replace "20 cities × 10K venues" with a tiered breakdown:
- 6 Tier 1 metros × 40K qualifying venues = 240,000
- 14 Tier 2 metros × 8K qualifying venues = 112,000
- Total SAM: 352,000 venues → at $86 blended ARPU = **$365M/year**
- Or at $134 Standard ARPU (excluding Light tier from SAM, since SAM should represent venues you'd *target*) = **$566M/year**

### Fix 4: Add Consumer Revenue TAM
New sheet or rows showing:
- Brand-sponsored quest revenue (% of India F&B brand marketing spend)
- GC campaign revenue (unit economics: ₹45.60 per ₹100 brand spend)
- Even at modest penetration, this adds $50-200M to the TAM

### Fix 5: Lead with Multi-Vertical on the Summary Sheet
Restructure the TAM Summary sheet:
1. Global Loyalty Market: $31B (context)
2. India Venue Engagement Platform (Multi-Vertical): $4-5B (the real TAM)
3. India F&B Beachhead: $1.2-2.5B (where you start)
4. Year 1 Execution Focus (SAM): $500M-1B
5. Bengaluru SOM: $X (where the first dollar comes from)

---

## Part 5: The Narrative Fix (Just as Important as the Numbers)

VCs don't invest in TAM slides. They invest in *narratives about market size*. Your current narrative says: "We're building loyalty tools for Indian restaurants. The market is $1.2B."

The narrative should be: "The $31B global loyalty market is being reinvented by AI. India — with 2.5M physical venues, the world's fastest-growing organized retail sector, and 450M digital-native consumers — is where this plays out first. CheckIn is building the engagement infrastructure layer: starting with F&B ($1.2B beachhead), expanding across retail, wellness, and events ($5B India platform TAM). F&B is the proving ground because it has the highest visit frequency, the sharpest aggregator pain, and the most natural fit for gamification. But the architecture is vertical-agnostic from Day 1."

This narrative:
- Starts with a big number ($31B)
- Shows why India is the right market
- Positions F&B as a strategic *choice*, not a limitation
- Makes the $1.2B beachhead feel like the starting point of something much bigger
- Is 100% consistent with everything in your thesis and product docs

---

## Part 6: Red Flags to Address (Beyond TAM)

A few things a sharp VC will notice:

1. **Thesis and Excel number mismatch** — Fix urgently. This undermines credibility.

2. **No consumer revenue in the model** — For a two-sided platform, having a B2B-only TAM model looks incomplete.

3. **ARPU assumption gap** — Your thesis says ₹10K/month blended ARPU but your Excel blended ARPU is $86/month (≈₹7,310/month). Another mismatch.

4. **"Semi-organized" venues in TAM** — 400K venues that use "QR/WhatsApp, no POS" at $29/month ARPU. A VC will question whether these venues will actually pay for anything. Consider separating your TAM into "high-conviction TAM" (organized, 800K venues) and "expansion TAM" (semi-organized, 400K venues).

5. **No SOM in the Excel** — You discuss Bengaluru SOM in other docs (2,500 venues) but it's not in the TAM model. Add it. VCs want to see the full funnel: TAM → SAM → SOM → Year 1 revenue.

---

## Summary: Action Items (Priority Order)

1. **Fix thesis/Excel mismatch immediately** — Use Excel as source of truth, update thesis text
2. **Restructure TAM Summary to lead with multi-vertical** — $5-7B India platform → $1.2B F&B beachhead → $365-566M SAM → Bengaluru SOM
3. **Add consumer-side revenue to the model** — Brand-sponsored quests, GC campaigns
4. **Fix SAM venue count** — Tiered city approach, ~350K venues
5. **Add "current market spend" framing** — Show what venues already pay (aggregator fees, marketing), position CheckIn ARPU as a fraction of existing spend
6. **Add SOM sheet** — Bengaluru, first 12-18 months, with revenue projections
7. **Update narrative** — Start with $31B global → India platform opportunity → F&B beachhead strategy

---

*This analysis is based on: Investment Thesis V2.md, CheckIn_TAM_Model.xlsx (all 4 sheets), product/revenue-model.md, product/competitive-landscape.md, fundraise/deck-outline.md, fundraise/qa-prep.md, fundraise/financials.md, product/overview.md, product/credit-system.md, product/roadmap.md, and web research on Indian VC expectations, comparable startups, and market sizing methodologies.*
