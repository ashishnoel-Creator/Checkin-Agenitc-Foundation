# CheckIn — Product Overview

> Last updated: February 16, 2026
> Status: **CANONICAL** — all other documents reference this file for product definitions
> Sources: product/overview.md (Git repo), Check-in Thesis V1, Checking V2-Working Doc

---

## One-Liner

**CheckIn is an AI-native customer engagement platform that helps F&B venues own their customer relationships through gamified experiences, a dual credit economy, and per-venue AI agents.**

## The Problem

India's F&B industry is bleeding margin in two directions — and losing its customer relationships in the process.

**The Delivery Tax**

Venues pay 15-28% commission to Zomato and Swiggy on every delivery order, plus payment gateway fees, GST, platform fees (₹10-12/order), and packaging costs. Total effective cost can exceed 35% of order value. In exchange, the aggregator provides genuine logistics value — riders, routing, customer support. But the customer's loyalty stays with the app, not the venue. If a venue leaves Zomato, its delivery customers don't follow.

**The Dine-In Trap**

Zomato Pay and Swiggy Dineout require participating venues to offer 15-40% mandatory discounts to customers, plus pay 4-12% commission per transaction. The critical issue: these discounts apply to any customer who pays through the app — including walk-ins who discovered the venue on their own, not through the aggregator. A customer sits down at your café because their friend recommended it, opens Zomato Pay, and the venue pays a 20% discount plus commission to an aggregator that contributed nothing to that visit. As the NRAI put it: "Why should a restaurant pay a commission to a middleman to offer a discount to its own customer?"

**The Dependency Spiral**

These two forces create a vicious cycle. Venues can't build direct customer relationships → they depend on aggregators for visibility → aggregators charge commissions AND insert themselves into dine-in transactions → venues lose margin on both delivery AND in-venue sales → venues can't afford to invest in their own engagement systems → dependency deepens.

**The Data Asymmetry**

Aggregators give venues dashboard access to aggregate metrics — order volumes, revenue trends, average order values, popular items, and operational scores. What they don't share is individual customer identity. A venue can see '200 orders this week' but can't identify who ordered, whether they're repeat customers, what else they eat, or when they'll come back. The platform masks customer phone numbers behind relay systems, so the venue can't contact its own customers directly. The aggregator builds a rich customer graph across the entire ecosystem; the venue gets a dashboard of its own aggregate numbers. That's not customer knowledge — that's a report card.

**The Retention Gap**

Most independent venues have zero systematic way to bring customers back. No loyalty program, no re-engagement tools, no way to reward regulars or incentivize return visits. The ones that try are stuck with punch cards or basic points systems that customers forget about. Research shows over 50% of loyalty memberships become inactive. Chains run loyalty programs, but they're expensive, generic, and disconnected from the in-venue experience.

**The Result**

Venues are caught between delivery commissions (15-28%) they can't avoid and dine-in discount programs (15-40% + commission) that cannibalise their own walk-in customers. The solution isn't to fight delivery — it provides real value. The solution is to make the in-venue experience so compelling that customers come directly, stay loyal, and keep coming back without needing aggregator-mediated discounts. That's what CheckIn builds.

## The Solution

CheckIn flips this dynamic. Instead of sending customers to an aggregator, CheckIn brings the platform to the venue — giving each venue its own intelligent engagement system.

### For the Venue

CheckIn is a platform where each venue gets a deep, customizable presence — their own page, their own quests, their own brand identity — powered by CheckIn. When a diner scans a venue's QR code, they enter that venue's world: active quests, the ordering system, VCs, leaderboard position, collectibles, personalized recommendations. It feels like the venue's system, but it runs on CheckIn's platform ("Powered by CheckIn").

When the diner leaves that venue's page, they return to the broader CheckIn platform — where they can browse other venues, see what's happening around them, discover new places through GCs — but they're not 'checked in' anywhere. The check-in is the moment of commitment; the platform is the ecosystem around it.

The venue gets:
- A community of every diner who has ever checked in — auto-followed, reachable via notifications and feed, with full behavioral profiles
- A customer intelligence system that learns diner preferences, visit patterns, and spending behavior
- A gamification engine (quests, streaks, challenges) that drives repeat visits without discounting
- A dual credit economy that creates a genuine reason for customers to return
- An AI agent that can autonomously run campaigns, optimize quests, manage inventory-linked promotions, and personalize the dining experience
- Full ownership of customer data and relationships within the platform

### For the Diner

CheckIn transforms a routine meal into an engaging experience. Diners earn Venue Credits (VCs) by completing quests (try 3 new dishes, visit 3 Fridays in a row, bring 2 friends). These credits are redeemable at that venue for real value. Over time, diners also earn Global Credits (GCs) that work across all CheckIn venues, creating a discovery engine that rewards exploring new places.

- A reason to go back (active quests, streaks, rewards they've earned)
- A feed of updates from followed venues — new quests, events, specials
- Personalized recommendations based on their actual taste profile
- Social features (group quests, leaderboards, challenges with friends)
- A cross-venue discovery system that rewards trying new places
- Control over the relationship: unfollow any venue anytime, manage notifications

### The Core Engagement Loop

Diner visits venue → Scans QR / opens CheckIn → Checks in (auto-follows the venue) → Sees active quests, personalized recommendations → Completes quest actions (orders, visits, social) → Earns Venue Credits (VCs) → Redeems VCs for rewards at that venue → Earns Global Credits (GCs) for platform-wide activity → GCs unlock discovery of new venues → Visits new venue → Checks in → New quests begin → Cycle repeats, data compounds, experiences improve.

**Check-in = auto-follow.** Once checked in, the diner becomes part of that venue's community. The venue can reach them — notifications, feed updates, new quests, special events. If they don't want to hear from a venue anymore, they unfollow. No consent popups, no phone number sharing debates. The check-in IS the relationship. The unfollow IS the exit.

## The Dual Credit Economy

CheckIn runs on a two-currency system, each serving a distinct purpose. The system draws from Free-to-Play gaming economics — the Soft Currency vs. Hard Currency model that drives retention in mobile games.

### Venue Credits (VCs) — The "Lock-In" Currency

- Earned by completing quests and challenges at a specific venue
- Redeemable ONLY at that venue for goods, services, or experiences
- Non-transferable, non-exchangeable between venues
- Floating value: venues set their own redemption rates, enabling dynamic demand shaping
- Dynamic decay: 60 days of inactivity → 10% balance degradation (prevents liability ballooning)
- Legal classification: loyalty points, exempt from VDA and PPI regulations (CBDT Notification 74/2022)

### Global Credits (GCs) — The "Liquidity" Currency

- Earned through platform-wide activity (cross-venue visits, referrals, brand campaigns)
- Redeemable at ANY CheckIn venue
- Fixed 1:1 INR peg (₹1 = 1 GC) — no floating exchange, no speculation
- Strict backing: brand/marketing funds deposited before GCs are minted
- Creates the network effect: more venues = more places to earn and redeem = more valuable for every diner

### The Swap Mechanism — "Casino Chip" Psychology

The GC→VC conversion is the key retention mechanism. A venue offers a minting bonus ("Swap GCs for our VCs today → 50% bonus"). The diner swaps 1,000 GCs → receives 1,500 VCs. VCs generally can't convert back to GCs (or incur a ~50% penalty). The diner is now psychologically committed to returning to that venue. This is deliberate demand-shaping — venues can incentivize swaps on slow days.

### Three-Tier Hierarchy

| Level | Scope | Example | Revenue Angle |
|-------|-------|---------|--------------|
| Venue VCs | Single independent venue | A standalone café's loyalty points | CheckIn takes a % cut per circulation cycle |
| Chain VCs | All outlets in a franchise/chain | "Social VCs" redeemable at any Social outlet | Platform/settlement fee to franchisor |
| Global Credits (GCs) | Every venue on CheckIn | Platform-wide discovery currency | Brand-sponsored campaigns, platform circulation |

This creates a natural upsell path: independent venues start with Venue VCs, chains upgrade to Chain VCs, and everyone participates in the GC ecosystem.

## The AI-Native Architecture

**CheckIn is not SaaS with AI bolted on. The AI is the product.**

### Per-Venue AI Agent

Every venue on CheckIn gets its own AI agent. This agent:
- **Learns** the venue's customer base — who visits, what they order, when they come, who they come with
- **Creates** quests and campaigns autonomously — tied to real business goals (move inventory, fill slow nights, reward regulars)
- **Personalizes** the diner experience — recommendations based on taste profile, not popularity
- **Optimizes** in real time — adjusts quest parameters based on completion rates, adjusts rewards based on margins
- **Grows** the venue's engagement — without the venue owner needing to do anything after initial setup

### Technical Stack

| Component | Technology | Why |
|-----------|-----------|-----|
| Framework | Vercel AI SDK 6 + Next.js | AI-native, built for streaming and agent orchestration |
| Database | Supabase | Postgres + real-time + auth + edge functions. Zero DevOps. |
| Agent Protocol | MCP (Model Context Protocol) | Each venue agent = a configuration, not a deployment |
| Models | Multi-model routing | Haiku (simple) → Sonnet (recommendations) → Opus (strategy) |
| Cost/venue | ₹300–1,100/month | vs. ₹3K–15K/month pricing = 3–5x margin |

### Agentic Revenue Model

Traditional SaaS charges a flat subscription. CheckIn's revenue grows as the AI does more.

| Timeline | What the AI Does | Revenue |
|----------|-----------------|---------|
| Month 1 | Base platform, basic quests | ₹3,000/month |
| Month 3 | AI runs campaigns, personalized recommendations | ₹3,000 base + ₹2,000 usage |
| Month 6 | Full autonomy, inventory-linked quests, 2 plugins | ₹3,000 base + ₹4,000 usage + ₹1,500 plugins |

Revenue correlates with value delivered. More engagement = more revenue = proof of value. This is the agentic revenue model — the AI itself generates revenue-producing actions.

## What CheckIn is NOT

- **Not an aggregator in the Zomato/Swiggy sense.** CheckIn does aggregate venues on its platform — it has to, because the Global Credits economy and cross-venue discovery only work with a network. But revenue comes from SaaS tiers and agentic value, not from taxing every order. If CheckIn provides payment gateway services, a per-transaction processing fee applies — but that's infrastructure cost recovery, not a commission on food sales.
- **Not a delivery platform.** CheckIn is about the in-venue experience and direct customer relationships. Delivery aggregators provide genuine logistics value — CheckIn doesn't compete with that.
- **Not a POS system.** CheckIn integrates with existing POS (Petpooja, Posist, etc.) but doesn't replace it.
- **Not a discount platform.** This is a critical distinction from Zomato Pay / Swiggy Dineout. Those programs drive visits through mandatory 15-40% discounts. CheckIn drives visits through quests, streaks, and earned rewards.
- **Not a generic loyalty tool.** Tools like Reelo do basic points-per-purchase. CheckIn's gamification engine drives behavior change, not just reward accumulation.

## Target Market

### Primary: Urban Independent F&B Venues in India

- Cafés, restaurants, bars, breweries, cloud kitchens with dine-in
- Located in urban clusters (starting: Indiranagar, Koramangala, HSR Layout, Bangalore)
- Revenue: ₹10L–2Cr/month
- Currently have zero or basic loyalty/engagement systems
- Paying 15-30% to aggregators and want alternatives
- 69% of Gen-Z consumers use aggregators for venue discovery (V1 market research)

### Secondary: F&B Chains and Franchises

- Multi-outlet operations wanting unified loyalty across locations
- Chain VCs enable cross-outlet redemption
- Higher ACV, longer sales cycle, but stronger retention

### Future: Any Venue with Repeat Customers

- Salons, gyms, co-working spaces, retail — the engagement model generalizes
- 74% of Gen-Z consumers value real-world experiences more than digital ones (V1 research)
- But F&B first, because visit frequency is highest and the aggregator pain is sharpest

## Product Phases

### Phase 1A: The Prototype — Vision Demo (Now)

A vibe-coded front-end prototype demonstrating the full system end-to-end. Not deployed to real venues — it's the vision made tangible for investors and venue partners.

Three surfaces:
- **Diner Browser:** QR check-in, quest system, ordering, VC earn/redeem, gated rewards
- **Diner App:** Discovery, feed, profile, GC economy, personal AI agent, collections
- **Venue Side:** AI agent (WhatsApp), analytics dashboard, campaign builder, plugin showcase

### Phase 1B: The MVP — First Deployment

The focused slice deployed to real venues in Indiranagar/Koramangala.

**What's in:** QR-based browser check-in and auto-follow, core quest system, VC earning and redemption, basic venue dashboard, campaign builder, gated app download flow.

**What's NOT in (yet):** Full app with discovery/feed/AI agent, GC cross-venue economy, plugin ecosystem, AI-driven autonomous quest creation, brand partnerships.

**Key MVP Metrics**

| Metric | What It Proves | Target |
|--------|---------------|--------|
| Quest Completion Rate | Are quests engaging enough? | >40% |
| Return Visit Rate | Are diners coming back because of CheckIn? | >35% within 30 days |
| VC Redemption Rate | Are credits valuable enough to use? | >60% |
| QR → Check-in Conversion | Does the entry flow work? | >50% of scans |
| App Download Rate | Does the gated reward model drive installs? | >20% of browser users |
| Venue Retention | Are venues staying on after trial? | >80% after 3 months |
| Venue Owner NPS | Do venues actually like this? | >50 |

### Phase 2: Intelligence & Expansion (Post-Seed, 0-12 months)

- Deploy app with discovery flow, feed, user profiles
- Per-venue AI agent learning from real customer data
- Automated quest creation tied to business goals
- Global Credits launch across venue network
- Expand to additional Bangalore neighborhoods

### Phase 3: Platform & Network Effects (12-24 months)

- Full agentic autonomy — venues set goals, AI handles execution
- Chain VC support, brand partnership marketplace, plugin marketplace
- Cross-city expansion
- Network effects compound — every new venue makes every existing venue more valuable

## Competitive Positioning

| Dimension | Aggregators (Zomato/Swiggy) | Dine-In Programs (Zomato Pay/Dineout) | Loyalty Tools (Reelo/Hashtag) | CheckIn |
|-----------|----------------------------|--------------------------------------|------------------------------|---------|
| Customer ownership | Aggregator owns; venue gets dashboards | Aggregator mediates even walk-in transactions | Venue has basic CRM data | Check-in = auto-follow. Venue has full profile |
| Cost to venue | 15-28% delivery commission + fees | 15-40% mandatory discount + 4-12% commission | Flat SaaS (₹2-5K/month) | Tiered SaaS + agentic usage; no food commission |
| Engagement model | Discounts and listing rank | Discount-driven footfall | Points-per-purchase | Gamified quests, streaks, earned rewards |
| Data depth | Aggregate metrics (volume, AOV, ratings) | Transaction data stays with platform | Transaction history, phone numbers | Full taste profile, behavioral patterns, social graph |
| Network effects | Discovery via aggregator | None | None | Cross-venue credit economy |
| Intelligence | Platform-level, not shared | None for venue | Basic analytics | Per-venue AI agent with diner-level intelligence |

CheckIn doesn't compete with Zomato's delivery logistics — that provides real value. CheckIn competes with the aggregator's grip on the customer relationship. By making in-venue experiences compelling enough to drive direct, repeated visits, CheckIn reduces a venue's dependency on both delivery commissions and dine-in discount programs.

## Go-To-Market: Services-Led Product Discovery

CheckIn's GTM is deliberately manual in Phase 1. This is not a weakness — it's the strategy.

The founding team does the work that AI agents will eventually automate at scale. Shash manually runs influencer campaigns. Ashish manually does venue onboarding and customer interviews while building the prototype. Aravind handles compliance and product specs.

Every manual workflow is documented in structured logs. These logs become the training data and playbook for AI agents as the platform scales.

**The pitch:** "We built the entire system before asking for money. We've done the work ourselves first. Now we need capital to put it in real venues and prove the economics."

---

## Historical Context (V1 Thesis)

The original thesis (September 2025) framed CheckIn as "Building the Operating System for the Experience Economy" — a broader framing that has been refined to focus specifically on F&B customer engagement. Key V1 concepts like the "Identity & Trust Fabric" (user-owned identity, bank-grade security) and the three-tiered architecture (Foundation Layer, Intelligence Layer, Application Layer) informed the current design but have evolved significantly.

V1 market research provided early validation: 74% of Gen-Z consumers value real-world experiences more than digital ones; 31% of F&B executives identify customer data as a top priority but lack unified systems; over 50% of traditional loyalty memberships become inactive. These data points reinforced the focus on gamified engagement over transactional loyalty.

---

*Sources: product/overview.md (canonical, Git repo); Check-in Thesis V1 (Sep 2025); Checking V2-Working Doc; Urban Indian F&B Analysis; Investor Pitch Deck.*

*This is the canonical product overview. All other documents should reference definitions and terminology from this document. If something here conflicts with another doc, this document wins.*
