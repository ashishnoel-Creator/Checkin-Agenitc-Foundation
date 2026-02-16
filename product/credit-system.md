# CheckIn Dual Credit System — VC/GC Architecture

> Last synthesized: Feb 16, 2026

## Overview

CheckIn operates a **dual-currency economy** designed to resolve a fundamental tension: users want **liquidity** (freedom to spend anywhere) while venues want **lock-in** (ensuring customers return). The system draws from Free-to-Play gaming economics (Soft Currency vs. Hard Currency).

The dual credit economy is also what makes CheckIn a platform that aggregates venues — GCs and cross-venue discovery require a network of venues. But unlike Zomato/Swiggy aggregation, CheckIn's model ensures venues own their customer data and relationships, and revenue comes from SaaS + agentic value, not per-order commissions.

The architecture also navigates India's VDA (Virtual Digital Asset) tax framework through deliberate regulatory structuring.

## The Two Currencies

### Venue Credits (VC) / Partner Coins (PC) — The "Local Loyalty" Ledger

**Nature:** Closed-loop, venue-specific digital currency
**Value:** Dynamic/floating (set by each venue)

**How Users Earn:**
- Completing venue-specific quests ("Visit 3 Fridays in a row," "Try 5 dishes")
- Non-monetary actions: streaks, check-ins, challenges
- Swapping Global Credits for venue-specific credits (with possible bonuses)

**How Users Spend:**
- PCs/VCs **cannot directly pay bills** (prevents margin erosion)
- Used exclusively for **gamified utility**: bid for best tables, control music/jukebox, unlock secret menu items, access exclusive experiences
- Think "casino chips" — once converted, psychologically committed to that venue

**Economic Design:**
- **Floating value** allows dynamic inventory management (Friday table auction: 5,000 PC; Tuesday: 500 PC)
- **Lock-in effect:** Converting GC → PC is generally one-way (or incurs steep ~50% haircut to convert back)
- **Minting bonuses:** Venues can offer "Swap GCs for our coins today, get 50% bonus" on slow days
- **Dynamic decay:** No venue visit for 60 days → PC balance degrades 10% (prevents liability ballooning, incentivizes frequency)

### Global Credits (GC) — The "Liquidity Layer"

**Nature:** Semi-closed-loop, fiat-pegged, cross-venue currency
**Peg:** 1 GC = ₹1 INR (fixed exchange rate for user trust)

**How Users Earn:**
- **Global Quests:** Brand-funded campaigns ("Watch the trailer for new Marvel movie → earn 50 GC")
- **Transaction Mining:** "Earn 1% back in GC on all dining transactions at any partner"
- **Referrals:** Viral growth engine

**How Users Spend:**
- **Universal bill payment** at any participating venue (capped at ~20% of bill to prevent "surrogate currency" concerns)
- **Global CheckIn Store:** Merchandise, event tickets, exclusive items
- **Portability:** GCs earned at Starbucks can be spent at a local mom-and-pop cafe — removes "stranded points" friction

**Economic Design:**
- Fixed 1:1 fiat peg is critical for trust (users know exactly what effort is worth)
- Strict 1:1 backing policy: marketing funds must hit bank before GCs are minted
- Float between brand payment and user redemption creates working capital

## Three-Tier Hierarchy

| Level | Scope | Example | Revenue Angle |
|-------|-------|---------|---------------|
| Venue VCs | Single independent venue | A standalone café's loyalty points | CheckIn takes a cut per circulation cycle |
| Chain VCs | All outlets in a franchise/chain | "Social VCs" redeemable at any Social outlet | Platform/settlement fee to franchisor |
| Global Credits (GCs) | Every venue on CheckIn | Platform-wide discovery currency | Brand-sponsored campaigns, platform circulation |

This creates a natural upsell path: independent venues start with Venue VCs, chains upgrade to Chain VCs, and everyone participates in the GC ecosystem.

## The Swap Mechanism — "Casino Chip" Psychology

The conversion between GC and PC is the key retention mechanism:

1. User holds GCs (universal "dollars")
2. To access venue VIP experiences, user swaps GCs for that venue's PCs ("casino chips")
3. PCs generally cannot convert back to GCs (or incur 50% penalty)
4. User is now psychologically committed to spending at that venue
5. Venues can dynamically incentivize swaps on slow days with minting bonuses

**Example Flow:**
- Slow Tuesday at Cafe Y
- Cafe Y offers: "Swap GCs for Cafe Y Coins today → 50% bonus"
- User swaps ₹1,000 in GCs → receives 1,500 PCs
- User gains massive utility value (more songs, secret menu) but loses liquidity
- User now locked into Cafe Y for future visits

## Revenue Model from Credit System

| Stream | Contribution | Margin | Mechanism |
|--------|-------------|--------|-----------|
| Commission Arbitrage | ~40% | 30–40% | Spread between brand ad spend and GC minting cost |
| SaaS Fees | ~30% | ~90% | Venues pay for analytics, CRM, premium features |
| Transaction Fees | ~10% | 1–2% | Standard payment gateway fees |
| Breakage | ~20% | 100% | Expired/unredeemed GCs = pure profit |

**User LTV:** Projected 3x higher than standard aggregator users due to PC lock-in and GC sunk cost fallacy.

## B2B Credit Circulation

An important feature: accumulated Venue Credits circulate in the B2B layer.

**Example:**
- User completes "Frequency Quest" → earns 500 VC
- User uses 500 VC to cover ₹500 bill (Bill on Account)
- 500 VCs transfer to venue's Merchant Wallet (not destroyed)
- Venue uses accumulated VCs to pay CheckIn's ₹8,000/month SaaS fee (e.g., ₹5,000 cash + ₹3,000 in VC value)

This creates a closed-loop B2B economy and raises the economic cost of venue churn (leaving = losing accumulated credit balance).

## Transaction Flow — Brand-Funded Quest Example

1. **Brand Investment:** Coffee chain allocates ₹100,000 for customer acquisition campaign
2. **Platform Fee:** CheckIn retains 20% (₹20,000) as service fee — immediate high-margin revenue
3. **GC Minting:** Remaining ₹80,000 backed 1:1 by fiat, minted as 80,000 GCs
4. **Distribution:** GCs distributed to users completing Global Quests ("Visit any partner cafe this week")
5. **Redemption:** Users spend GCs at venues; CheckIn reimburses venue at conversion rate (e.g., ₹0.85 per GC)
6. **Breakage:** ~20% of GCs expire unredeemed → pure profit for CheckIn (no GST per CBIC Circular 243/37/2024)

## Inflation Control — Sinks and Faucets

Managing a dual-currency economy requires strict governance:

- **Faucets:** GC earning from quests, referrals, transaction mining; PC minting bonuses
- **Sinks:** Redemption at venues, credit expiry, PC dynamic decay
- **PC Half-Life:** 60 days of inactivity → 10% balance degradation (prevents hoarding, incentivizes frequency)
- **GC Backing:** Strict 1:1 fiat reserve requirement — no unbacked minting

## Key Terminology

| Term | Definition |
|------|-----------|
| **VC (Venue Credits)** | Closed-loop loyalty points for venue-specific circulation (India regulatory term) |
| **PC (Partner Coins)** | Alternative name for venue-specific credits, emphasizing the gamified utility layer |
| **GC (Global Credits)** | Cross-venue, fiat-pegged credits for universal bill payment and platform-wide use |
| **CKIN** | Future offshore governance token (Singapore/Dubai) for global expansion |
| **Table Pot** | Temporary shared credit pool during a dining session for group experiences |
| **Breakage** | Revenue from expired/unredeemed credits |
| **BOA (Bill on Account)** | When user pays bill using accumulated credits |

[NEEDS REVIEW] The naming convention between VC and PC needs final alignment — "Venue Credits" is used in regulatory/compliance docs, while "Partner Coins" is used in product/strategy docs. Recommend standardizing.

---

Sources: Dual-Coin Economy for CheckIn: Regulatory Arbitrage, Corporate Structuring, and Economic Viability; GC/VC Specific - Utility and Compliance; Check-in - Thesis; Checking V2-Working Doc; Checkin Whitepaper v1.1
