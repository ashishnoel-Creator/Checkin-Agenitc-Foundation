# Decisions Log

> Last synthesized: Feb 15, 2026

Track key strategic and product decisions with rationale.

## Template

Each entry should follow:
- **Date:**
- **Decision:**
- **Context:**
- **Options Considered:**
- **Rationale:**
- **Owner:**

## Key Decisions

### F&B as Beachhead Vertical
- **Date:** Mid-2025
- **Decision:** Launch with F&B (restaurants, cafes, pubs) as primary vertical
- **Rationale:** High frequency of visits (vs. retail/wellness), strong social dynamics (group dining), acute aggregator pain (15–30% commissions), Gen-Z engagement opportunity
- **Owner:** Ashish

### Bengaluru as Launch City
- **Date:** Mid-2025
- **Decision:** Launch in Bengaluru, specifically Koramangala/Indiranagar/HSR Layout clusters
- **Rationale:** High concentration of Gen-Z, tech-savvy demographic, dense premium venue clusters, team is based here
- **Owner:** Ashish

### Dual Credit Economy (VC + GC)
- **Date:** Late 2025 / Early 2026
- **Decision:** Two-currency system instead of single reward currency
- **Rationale:** Resolves user-liquidity vs. venue-lock-in tension; provides regulatory pathway in India (VC as loyalty points, GC as platform currency)
- **Owner:** Aravind

### Freemium SaaS Before Ad Platform
- **Date:** Mid-2025
- **Decision:** Revenue Phase 1 is freemium SaaS; Ad platform is Phase 2
- **Rationale:** Need venue network density before ad platform has value; freemium drives rapid adoption
- **Owner:** Ashish

### Fixed SaaS Fee, Not Commission
- **Date:** Late 2025
- **Decision:** Charge venues fixed monthly fee, not variable commission on transactions
- **Rationale:** Venues associate variable commission with Zomato/Swiggy exploitation. Fixed fee positions CheckIn as partner, not another aggregator. Per Porter's analysis: >10% success fee = "Zomato 2.0" perception.
- **Owner:** Aravind

### Technical Stack: Next.js + Supabase + Vercel AI SDK
- **Date:** Early 2026
- **Decision:** Use Vercel AI SDK 6 + Next.js for frontend/API, Supabase for database/auth/real-time, MCP for agent protocol
- **Options Considered:** (1) Custom backend (Node/Express + Postgres), (2) Firebase + custom AI layer, (3) Vercel + Supabase + AI SDK
- **Rationale:** Zero DevOps overhead for a 3-person team. Supabase provides Postgres + real-time + auth in one. AI SDK 6 provides native agent orchestration (tool calling, streaming, multi-model routing). MCP means venue agents are configurations, not deployments. Both Vercel and Supabase auto-scale.
- **Owner:** Ashish

### GTM: Hyperlocal Cluster Strategy
- **Date:** Early 2026
- **Decision:** Focus on 3 Bengaluru neighborhoods (Koramangala, Indiranagar, HSR) before expanding city-wide
- **Options Considered:** (1) City-wide launch, (2) Single neighborhood, (3) 3 adjacent clusters
- **Rationale:** Network effects require venue density. 3 clusters gives enough density for cross-venue discovery while keeping RM workload manageable. Gen-Z diner overlap between these neighborhoods means diner network effects too.
- **Owner:** Shash

### Naming Standardization: Venue Credits (VC)
- **Date:** Feb 16, 2026
- **Decision:** Standardize on "Venue Credits (VC)" across all documents. Deprecate "Partner Coins (PC)"
- **Rationale:** Compliance docs (which interface with regulators) already use VC. "Venue Credits" is clearer for venues and investors. "Partner Coins" created confusion between product and regulatory terminology.
- **Owner:** Aravind

### Brand Spelling: CheckIn (capital C, capital I)
- **Date:** Feb 16, 2026
- **Decision:** Canonical spelling is "CheckIn". Not "Checkin", "Check-In", or "CHECKIN"
- **Rationale:** Consistency across all investor-facing and customer-facing materials. CamelCase is distinctive and memorable.
- **Owner:** Shash

### Company Incorporation: Pvt Ltd
- **Date:** [FOUNDER INPUT NEEDED]
- **Decision:** [FOUNDER INPUT NEEDED — Pvt Ltd vs. LLP]
- **Options Considered:** (1) Private Limited Company, (2) LLP
- **Rationale:** [FOUNDER INPUT NEEDED — Most Indian pre-seed investors require Pvt Ltd for equity investment. LLP doesn't allow equity shares in the traditional sense.]
- **Owner:** Aravind

---

Sources: Check-in - Thesis, Checking V2-Working Doc, Porter's 5 Forces Analysis
