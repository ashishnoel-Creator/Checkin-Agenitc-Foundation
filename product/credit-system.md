# CheckIn Dual Credit System — Canonical Architecture

> Last updated: February 16, 2026 | By: Ashish + Aravind
> Status: CANONICAL — definitive reference for credit system design, economics, and regulatory positioning

## Overview

CheckIn operates a dual-currency economy designed to resolve a fundamental tension in loyalty: users want liquidity (freedom to spend anywhere) while venues want lock-in (ensuring customers return). The system draws from Free-to-Play gaming economics — specifically the Soft Currency vs. Hard Currency model that drives retention in mobile games.

The dual credit economy is also what makes CheckIn a platform. Global Credits and cross-venue discovery require a network of venues, which is why CheckIn aggregates venues — but unlike Zomato/Swiggy aggregation, venues own their customer data and relationships, and revenue comes from SaaS + agentic value, not per-order commissions.

Both currencies — Venue Credits and Global Credits — are structured as non-VDA loyalty points under Indian law. This was a deliberate architectural decision. The original design treated GCs as VDA tokens (ERC-20, 30% tax, crypto infrastructure). The revised architecture eliminates the entire VDA tax burden, removes RBI scrutiny, avoids FEMA complications, and creates a simpler narrative for investors and users. Blockchain may be used as backend infrastructure in the future, but the user-facing product is a clean loyalty engine.

## Naming Convention

Standardized terminology (effective Feb 2026):

| Term | Use | Notes |
|------|-----|-------|
| Venue Credits (VCs) | All contexts — product, regulatory, investor materials | Replaces "Partner Coins (PC)" from earlier docs |
| Chain VCs | Chain/franchise variant of VCs | Same legal structure, wider redemption scope |
| Global Credits (GCs) | Platform-wide loyalty currency | NOT a VDA. NOT crypto. Loyalty points on a centralized ledger |

"Partner Coins" and "PC" are deprecated. Any older document using those terms should be read as "Venue Credits."

## The Two Currencies

### Venue Credits (VCs) — The "Lock-In" Currency

**Nature:** Closed-loop, venue-specific loyalty points
**Scope:** Earned and redeemable ONLY at a single venue (or across a chain, for Chain VCs)
**Legal classification:** Loyalty points, exempt from VDA definition (CBDT Notification 74/2022), no PPI license required

**How Diners Earn VCs:**
- Completing venue-specific quests ("Visit 3 Fridays in a row," "Try 5 new dishes," "Bring 2 friends")
- Non-monetary actions only: streaks, check-ins, social challenges, menu exploration
- Swapping Global Credits for VCs at a venue (with possible minting bonuses — see Swap Mechanism below)
- VCs are never purchased for cash. This is critical for maintaining the loyalty point exemption.

**How Diners Spend VCs:**
- Redeeming for goods, services, or experiences at that venue
- Gamified utility: bid for best tables, control music/jukebox, unlock secret menu items, access exclusive experiences, priority reservations
- VCs do NOT directly pay bills in cash terms — they unlock value through the venue's reward structure. The venue decides what VCs are worth in terms of menu items, experiences, and perks.
- Think "casino chips" — once you've converted your GCs into a venue's VCs, you're psychologically committed to that venue

**Economic Design:**
- Floating value: venues set their own VC redemption rates, allowing dynamic inventory management (Friday table auction: 5,000 VC; Tuesday: 500 VC)
- Lock-in effect: Converting GC → VC is generally one-way (or incurs a steep ~50% haircut to convert back)
- Minting bonuses: Venues can offer "Swap GCs for our VCs today, get 50% bonus" on slow days — a powerful demand-shaping tool
- Dynamic decay: No venue visit for 60 days → VC balance degrades 10% (prevents liability ballooning, incentivizes visit frequency)
- Venue controls VC supply within CheckIn's governance framework

### Global Credits (GCs) — The "Liquidity" Currency

**Nature:** Platform-wide loyalty points on a centralized ledger
**Scope:** Earned through platform-wide activity, redeemable at ANY CheckIn venue
**Peg:** 1 GC = ₹1 INR (fixed, not floating — critical for user trust)
**Legal classification:** Non-VDA loyalty points (same exemption as VCs — see Regulatory section)

**How Diners Earn GCs:**
- Cross-venue activity: visiting new venues, completing discovery quests ("Try 3 new cafés this month")
- Referrals: bringing new diners or venues to the platform
- Brand-funded Global Quests: brand-sponsored campaigns ("Watch the trailer for new movie → earn 50 GC")
- Community contributions: reviews, social sharing, content creation
- GCs are never purchased for cash.

**How Diners Spend GCs:**
- Redeem at any participating venue for goods/services (venue treats as a discount — CheckIn reimburses venue)
- Swap for VCs at a specific venue (often with minting bonuses)
- Access platform-level rewards: merchandise, event tickets, exclusive experiences via CheckIn Store
- Discovery incentive: GCs earned at Café A can be spent at Café B — removing "stranded points" friction and powering cross-venue discovery

**Economic Design:**
- Fixed 1:1 fiat peg: users always know exactly what their effort is worth. No floating exchange rates, no speculation.
- Strict backing policy: brand/marketing funds must be deposited before GCs are minted. No unbacked minting.
- Float between brand payment and user redemption creates working capital for CheckIn
- Bill coverage cap: GC redemptions may be capped at a percentage of bill value (e.g., 20%) to prevent "surrogate currency" concerns and protect venue margins

## Three-Tier Hierarchy

| Level | Scope | Example | Revenue Angle |
|-------|-------|---------|---------------|
| Venue VCs | Single independent venue | A standalone café's loyalty points | CheckIn takes a % cut per VC circulation cycle |
| Chain VCs | All outlets in a franchise/chain | "Social VCs" redeemable at any Social outlet | Platform/settlement fee to franchisor |
| Global Credits (GCs) | Every venue on CheckIn | Platform-wide discovery currency | Brand-sponsored campaigns, platform circulation fee |

This creates a natural upsell path: independent venues start with Venue VCs, chains upgrade to Chain VCs, and everyone participates in the GC ecosystem. Each tier is progressively more valuable to the diner (wider redemption) and gives CheckIn a different revenue surface.

### Chain VCs — The Franchise Model

When a chain like Social or Third Wave Coffee joins CheckIn, their VCs become Chain VCs — redeemable across all outlets in that chain.

**Settlement Model:** The franchisor manages a unified VC pool. When Outlet B redeems VCs that were earned at Outlet A, the franchisor's internal accounting handles the transfer. CheckIn's platform facilitates this, and the service fee is charged to the franchisor centrally.

This mirrors how Starbucks Rewards and McDonald's loyalty programs already work. Clean, well-understood, no regulatory issues. The legal status is identical to single-venue VCs — loyalty points within a single brand entity.

## The Swap Mechanism — "Casino Chip" Psychology

The conversion between GC and VC is the key retention mechanism. It's deliberately designed to create psychological commitment:

**The Flow:**
1. Diner holds GCs (universal "dollars" — liquid, spendable anywhere)
2. Venue offers a minting bonus: "Swap GCs for our VCs today → 50% bonus"
3. Diner swaps 1,000 GCs → receives 1,500 VCs at that venue
4. VCs generally cannot convert back to GCs (or incur ~50% penalty)
5. Diner now has massive utility value at that venue but has lost liquidity
6. Diner is psychologically committed to returning to that venue to spend their VCs

**Why This Works:**
- The minting bonus creates a "too good to pass up" offer
- One-way conversion (or steep haircut) prevents arbitrage
- Venues can dynamically incentivize swaps on slow days — powerful demand shaping tool
- The diner doesn't feel "trapped" because they chose to swap — it's an active decision that feels rewarding
- Venues fund their own VCs (COGS cost, not cash), so the economics work

**Example:**
- Slow Tuesday at Café Y
- Café Y offers: "Swap GCs for Café Y VCs today → 50% bonus"
- Diner swaps ₹1,000 worth of GCs → receives 1,500 VCs
- Diner gets: more songs on the jukebox, secret menu access, table priority — but only at Café Y
- Café Y gets: a committed customer who will return to use their VC balance
- CheckIn gets: a % cut on the GC→VC swap transaction

## Revenue Model from Credit System

CheckIn's revenue from the credit economy is outcome-based — it grows as the economy circulates, not as a flat subscription tax.

| Stream | Description | Margin Profile |
|--------|-------------|----------------|
| VC Circulation Fee | CheckIn takes a % cut each time VCs complete a circulation cycle (earned → redeemed → recirculated) | High margin (~30-40%) |
| GC Minting Fee | When brands fund GC campaigns, CheckIn retains 15-20% as a platform/service fee before minting GCs | Very high margin (~90%) |
| GC Redemption Spread | CheckIn reimburses venues at a rate below face value when GCs are redeemed (e.g., ₹0.85 per GC). The spread is margin. | Moderate margin |
| Breakage | Expired/unredeemed credits = pure revenue for CheckIn. No supply = no GST (per CBIC Circular 243/37/2024) | 100% margin |
| Swap Fees | % cut on GC→VC conversions | High margin |
| SaaS Base | Monthly subscription fees (payable in cash or partially in accumulated VCs) | ~90% margin |
| Payment Processing | If CheckIn provides payment gateway services, per-transaction processing fee applies | Low margin (1-2%) — infrastructure cost recovery |

The key insight: this is an "agentic revenue" model. As the AI agent drives more quest completions, more VC circulation, and more GC activity, CheckIn's revenue grows automatically. Revenue correlates with value delivered.

## B2B Credit Circulation

VCs don't just flow from CheckIn → diner → venue and stop. They circulate in a B2B layer that creates economic switching costs.

**How It Works:**
1. Diner completes quest → earns 500 VCs
2. Diner redeems 500 VCs for a meal at the venue
3. 500 VCs transfer to the venue's Merchant Wallet (they're not destroyed)
4. Venue accumulates VCs over time in their Merchant Wallet
5. Venue can use accumulated VCs to partially offset CheckIn's monthly SaaS fee (e.g., ₹5,000 cash + ₹3,000 in VC value for ₹8,000/month subscription)

**Why This Matters:**
- Creates a closed-loop B2B economy within CheckIn
- Raises economic switching costs: leaving CheckIn means forfeiting accumulated VC balance in the Merchant Wallet
- Gives venues a tangible "asset" within the platform — they can see their VC balance growing
- Aligns incentives: the more a venue engages its customers (driving VC circulation), the more VCs accumulate in their wallet, reducing their effective SaaS cost

## Brand-Funded GC Campaign — Full Transaction Flow

Here's how money flows through a Global Quest campaign:

1. **Brand Investment:** Coffee chain allocates ₹100,000 for customer acquisition campaign on CheckIn
2. **Platform Fee:** CheckIn retains 20% (₹20,000) as a service fee — immediate high-margin revenue
3. **GC Minting:** Remaining ₹80,000 backed 1:1 by fiat, minted as 80,000 GCs in the system
4. **Distribution:** GCs distributed to diners who complete the Global Quest ("Visit any partner café this week")
5. **Redemption:** Diners spend GCs at venues. CheckIn reimburses venue at a conversion rate (e.g., ₹0.85 per GC). The ₹0.15 spread per GC is CheckIn revenue.
6. **Breakage:** ~15-20% of GCs expire unredeemed → pure profit for CheckIn (no GST per CBIC Circular 243/37/2024)

**Unit economics per ₹100 brand spend:**
- ₹20.00 — CheckIn platform fee (captured immediately)
- ₹54.40 — Venue reimbursements (₹0.85 × 64 GCs redeemed, assuming 80% redemption)
- ₹9.60 — CheckIn spread on redeemed GCs (₹0.15 × 64)
- ₹16.00 — Breakage revenue (unredeemed GCs)
- **Total CheckIn revenue: ₹45.60 per ₹100 brand spend**

## Inflation Control — Sinks and Faucets

Managing a dual-currency economy requires strict governance to prevent hyperinflation (too many credits chasing too few rewards) or deflation (users hoarding, not spending).

**Faucets (how credits enter the system):**
- VC earning from venue quests, streaks, challenges
- GC earning from global quests, referrals, brand campaigns
- VC minting bonuses during GC→VC swaps

**Sinks (how credits leave the system):**
- VC redemption at venues (converted to goods/services)
- GC redemption at venues (removed from circulation after reimbursement)
- Credit expiry: GCs and VCs have expiration windows
- VC dynamic decay: 60 days of inactivity at a venue → 10% VC balance degradation
- GC→VC swap (GCs leave the liquid pool, enter venue-specific lock-in)

**Governance Rules:**
- GC strict 1:1 fiat backing: no unbacked minting, ever. Marketing funds must hit CheckIn's bank account before GCs are created.
- VC supply governed per venue: each venue has a VC budget cap set in consultation with CheckIn's AI agent, based on the venue's revenue, COGS margins, and engagement targets
- Dynamic decay prevents "zombie balances" that create accounting liabilities without generating engagement
- AI agent monitors faucet/sink ratios per venue and alerts when inflation risk emerges

## Regulatory Architecture

### The Core Principle

Both VCs and GCs are structured as non-VDA loyalty points under Indian law. This is the single most important design decision in CheckIn's credit system.

### Venue Credits — Legal Status

**VDA exemption:** ✅ Confirmed exempt under CBDT Notification 74/2022, which excludes "mileage points, reward points or loyalty card, being a record given without direct monetary consideration under an award, reward, benefit, loyalty, incentive, rebate or promotional program that may be used or redeemed only to obtain goods or services or a discount on goods or services."

**Three criteria that MUST be maintained:**
1. **No direct monetary consideration:** VCs earned via non-monetary actions only (quests, streaks, check-ins — never purchased for cash)
2. **Service redemption only:** Usable only for goods/services within the venue (never convertible to fiat, no cash-out)
3. **Non-transferable (with limits):** Social gifting within platform may be permitted, but no off-ramp to INR or third-party exchange

**RBI classification:** No PPI license needed. Closed System PPIs are exempt from RBI authorization. VCs are even simpler than closed-loop PPIs — they're loyalty points, not stored value.

**Tax on users:** Zero. Loyalty point earnings function as a rebate on engagement, not as income. Same treatment as credit card rewards, airline miles, CRED coins, Zomato credits.

### Global Credits — Legal Status

The key insight: GCs are structurally identical to multi-brand loyalty programs like airline miles, CRED coins, or Paytm cashback. They are earned through non-monetary activity, redeemable only for goods/services, and not convertible to cash. The same Notification 74/2022 exemption applies.

**What makes this work:**
- GCs are earned through quests/referrals/activity — never purchased for cash
- GCs are redeemable only for goods/services at CheckIn venues — no fiat off-ramp
- GCs sit on a centralized database ledger — NOT blockchain, NOT ERC-20 tokens
- GCs cannot be traded on any exchange — public or private
- No P2P transfers that could create a shadow market

**What would break this:**
- Allowing users to buy GCs for cash → makes them a PPI, requires RBI license
- Allowing fiat off-ramp → makes them a payment instrument
- Putting them on a public blockchain → risks VDA classification
- Allowing P2P trading → creates exchangeability that breaks the exemption
- Pegging to a floating exchange rate → implies speculative value

**Tax on users:** Zero — same loyalty point treatment as VCs.

### GST Treatment

| Event | GST Treatment | Basis |
|-------|---------------|-------|
| VC redemption at venue | Venue applies trade discount. If 100% VC bill, taxable value adjusted accordingly. Venue should still charge GST on the discounted value. | Trade discount at time of supply |
| GC redemption at venue | Third-party consideration: venue receives reimbursement from CheckIn. GST applies on full bill value. | Section 2(31) — third-party consideration |
| GC breakage (expired) | No supply occurred → ₹0 taxable → 0% GST | CBIC Circular 243/37/2024 |
| CheckIn platform fee | 18% GST on service fee retained from brand campaigns | Supply of marketing services |

**Important note:** The GST treatment of loyalty point redemptions is an evolving area. The precise treatment should be validated with a GST advisor, especially for 100% VC bill scenarios. The conservative approach: venue charges GST on the original bill value and treats VC redemption as a payment method, not a discount. This needs a formal legal opinion before launch.

## What Changed From the Original Architecture

| Component | Original Design | Current Design |
|-----------|----------------|----------------|
| Venue Credits | Non-VDA loyalty points (venue-specific) | Same — no change |
| Global Credits (India) | VDA, ERC-20, 30% tax, 1% TDS | Non-VDA platform-wide loyalty points on centralized ledger |
| Global Credits (International) | Same token as India | Separate offshore token (CKIN) issued by foundation — deferred to post-PMF |
| VC circulation | Venue pays CheckIn in VCs (B2B swap) | Venue recirculates VCs to customers; CheckIn takes % cut per cycle |
| Revenue model | SaaS subscription only | SaaS + agentic revenue from VC/GC circulation |
| Tax burden on users | 30% on GC gains + 1% TDS | Zero — loyalty point exemption applies to both VCs and GCs |
| Regulatory risk | High (VDA compliance, RBI scrutiny) | Low — standard loyalty program rules |
| Blockchain | Core infrastructure | Backend option only, deferred. User-facing product is centralized ledger |

## Cross-Border Design (Future — Post-India PMF)

### The Principle

When CheckIn expands internationally, GCs are a universal engagement currency. Users see "100 GCs" everywhere. What changes is the local redemption value at the venue level, which is an internal business decision by CheckIn, not a user-facing forex transaction.

### What This Means

- No GC↔GC exchange between countries. Indian GCs and Bangladeshi GCs are the same currency — "GCs" — with different local redemption values.
- Users never see an exchange rate. The user experience is: "I have 500 GCs. I can spend them at this venue in Dhaka for a meal worth X, or at this venue in Bangalore for a meal worth Y."
- The value difference is absorbed by CheckIn's internal economics, not exposed to users.
- This preserves the loyalty point exemption by avoiding any implication of forex or exchangeability.

### Offshore Token (CKIN) — Deferred

A governance/utility token (CKIN) issued by an offshore foundation (Singapore under MAS or Dubai under VARA) remains a future option for global incentive alignment. This is relevant only for non-India markets and only after India PMF is proven. No development or legal work on CKIN is needed pre-fundraise.

### FEMA Considerations

Cross-border GC redemptions (Indian diner uses GCs at a foreign venue) are structured as B2B Marketing Service Agreements between CheckIn India and the CheckIn Global entity. The user is redeeming loyalty points for a discount — no outward remittance under LRS applies. The settlement between entities is an inter-company adjustment for marketing services, not a per-user remittance.

## Key Risks and Mitigations

| Risk | Severity | Mitigation |
|------|----------|------------|
| GCs reclassified as VDA | Medium | Maintain strict non-VDA criteria: no cash purchase, no fiat off-ramp, no public blockchain, no P2P trading, no floating exchange rate |
| RBI "surrogate currency" concern for GCs | Low-Medium | Cap GC bill payments at X% of bill value, maintain that GCs are not a payment instrument but a loyalty currency |
| VC loses loyalty point exemption | Low | Maintain three criteria: no cash purchase, service-only redemption, limited P2P. Document all compliance measures. |
| GST treatment challenged | Medium | Get formal GST opinion before launch. Conservative approach: charge GST on full bill value regardless of VC/GC payment method |
| Credit inflation/devaluation | Medium | AI agent monitors faucet/sink ratios. Dynamic decay on VCs. Strict 1:1 GC backing. Per-venue VC budget caps. |
| Venue gaming the system | Low | VC budgets capped per venue. AI agent flags unusual patterns. B2B circulation creates transparency. |

## Open Questions

1. **GC bill payment cap:** What percentage of a bill can be paid in GCs? Needs market testing and regulatory comfort.
2. **VC decay rate:** 10% per 60 days of inactivity — is this the right cadence? Needs user research.
3. **GC→VC swap haircut:** ~50% penalty to convert back. Is this too harsh? Too lenient? Needs game economy modeling.
4. **GST formal opinion:** The GST treatment of loyalty point redemptions needs a formal legal opinion from a qualified GST advisor before launch.
5. **B2B VC offset limit:** How much of a venue's SaaS fee can be offset with accumulated VCs? 100%? Capped at 50%?

---

This is the canonical credit system document. It supersedes all earlier versions, including the Dual-Coin Economy compliance doc and GC/VC Utility and Compliance doc from Aravind's original regulatory analysis. The regulatory framework in `operations/compliance.md` should be updated to align with this document.

Sources: Dual-Coin Economy for CheckIn (original, extensively revised); GC/VC Utility and Compliance analysis; Feb 13 2026 architectural restructuring session; product/overview.md (canonical); CBDT Notification 74/2022; CBIC Circular 243/37/2024.
