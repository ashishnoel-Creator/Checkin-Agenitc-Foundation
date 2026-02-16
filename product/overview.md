# CheckIn — Product Overview

*Last updated: February 16, 2026 | By: Ashish*
*Status: CANONICAL — all other docs reference this file for product definitions*

---

## One-Liner

CheckIn is an AI-native customer engagement platform that helps F&B venues own their customer relationships through gamified experiences, a dual credit economy, and per-venue AI agents.

## The Problem

India's F&B industry is bleeding margin in two directions — and losing its customer relationships in the process.

**The Delivery Tax:** Venues pay 15-28% commission to Zomato and Swiggy on every delivery order, plus payment gateway fees, GST, platform fees (₹10-12/order), and packaging costs. Total effective cost can exceed 35% of order value. In exchange, the aggregator provides genuine logistics value — riders, routing, customer support. But the customer's loyalty stays with the app, not the venue. If a venue leaves Zomato, its delivery customers don't follow.

**The Dine-In Trap (the less visible but more painful problem):** Here's where it gets insidious. Zomato Pay and Swiggy Dineout require participating venues to offer 15-40% mandatory discounts to customers, plus pay 4-12% commission per transaction to the platform. The critical issue: these discounts apply to *any* customer who pays through the app — including walk-ins who discovered the venue on their own, not through the aggregator. A customer sits down at your café because their friend recommended it, opens Zomato Pay, and the venue pays a 20% discount plus commission to an aggregator that contributed nothing to that visit. As the NRAI put it: "Why should a restaurant pay a commission to a middleman to offer a discount to its own customer?"

**The Dependency Spiral:** These two forces create a vicious cycle. Venues can't build direct customer relationships → so they depend on aggregators for visibility → aggregators charge commissions AND insert themselves into dine-in transactions → venues lose margin on both delivery AND in-venue sales → venues can't afford to invest in their own engagement systems → dependency deepens.

**The Data Asymmetry:** Aggregators give venues dashboard access to aggregate metrics — order volumes, revenue trends, average order values, popular items, and operational scores. What they don't share is individual customer identity. A venue can see "200 orders this week" but can't identify who ordered, whether they're repeat customers, what else they eat, or when they'll come back. The platform masks customer phone numbers behind relay systems, so the venue can't contact its own customers directly. Even Zomato's late-2025 data-sharing initiative (under NRAI pressure) only offers to share phone numbers — with customer opt-in consent — and nothing else. No order history, no taste preferences, no behavioral profile. The aggregator builds a rich customer graph across the entire ecosystem; the venue gets a dashboard of its own aggregate numbers. That's not customer knowledge — that's a report card.

**The Retention Gap:** Most independent venues have zero systematic way to bring customers back. No loyalty program, no re-engagement tools, no way to reward regulars or incentivize return visits. The ones that try are stuck with punch cards or basic points systems that customers forget about. Chains run loyalty programs, but they're expensive, generic, and disconnected from the in-venue experience.

**The Result:** Venues are caught between delivery commissions (15-28%) they can't avoid and dine-in discount programs (15-40% + commission) that cannibalise their own walk-in customers. The solution isn't to fight delivery — it provides real value. The solution is to make the in-venue experience so compelling that customers come directly, stay loyal, and keep coming back without needing aggregator-mediated discounts. That's what CheckIn builds.

## The Solution

CheckIn flips this dynamic. Instead of sending customers to an aggregator, CheckIn brings the platform to the venue — giving each venue its own intelligent engagement system.

### What CheckIn Does

**For the Venue:**
CheckIn is a platform where each venue gets a deep, customizable presence — their own page, their own quests, their own brand identity — powered by CheckIn. When a diner scans a venue's QR code, they enter that venue's world: active quests, the ordering system, VCs, leaderboard position, collectibles, personalized recommendations. It feels like the venue's system, but it runs on CheckIn's platform ("Powered by CheckIn").

When the diner leaves that venue's page, they return to the broader CheckIn platform — where they can browse other venues, see what's happening around them, discover new places through GCs — but they're not "checked in" anywhere. The check-in is the moment of commitment; the platform is the ecosystem around it.

The venue gets:
- A community of every diner who has ever checked in — auto-followed, reachable via notifications and feed, with full behavioral profiles
- A customer intelligence system that learns diner preferences, visit patterns, and spending behavior
- A gamification engine (quests, streaks, challenges) that drives repeat visits without discounting
- A dual credit economy that creates a genuine reason for customers to return
- An AI agent that can autonomously run campaigns, optimize quests, manage inventory-linked promotions, and personalize the dining experience
- Full ownership of customer data and relationships within the platform

**For the Diner:**
CheckIn transforms a routine meal into an engaging experience. Diners earn Venue Credits (VCs) by completing quests (try 3 new dishes, visit 3 Fridays in a row, bring 2 friends). These credits are redeemable at that venue for real value — free items, upgrades, exclusive experiences. Over time, diners also earn Global Credits (GCs) that work across all CheckIn venues, creating a discovery engine that rewards exploring new places.

The diner gets:
- A reason to go back (active quests, streaks, rewards they've earned)
- A feed of updates from followed venues — new quests, events, specials
- Personalized recommendations based on their actual taste profile
- Social features (group quests, leaderboards, challenges with friends)
- A cross-venue discovery system that rewards trying new places
- Control over the relationship: unfollow any venue anytime, manage notifications

**For CheckIn (the business):**
CheckIn earns through a multi-tier model that grows as venues grow. Core revenue comes from SaaS subscriptions and agentic usage fees — not from taxing food transactions. If CheckIn provides payment gateway services (for VC redemption, in-app ordering, etc.), a per-transaction processing fee applies — but this covers infrastructure costs, not a commission on food sales. Revenue scales with the value the platform creates, not the volume of orders it processes. (See: product/revenue-model.md)

### How It Works — The Core Loop

```
Diner visits venue
    → Scans QR / opens CheckIn
    → Checks in → auto-follows the venue (can unfollow anytime)
    → Sees active quests, personalized recommendations
    → Completes quest actions (orders, visits, social)
    → Earns Venue Credits (VCs)
    → Redeems VCs for rewards at that venue
    → Earns Global Credits (GCs) for platform-wide activity
    → GCs unlock discovery of new venues
    → Visits new venue → checks in → auto-follows → new quests begin
    → Cycle repeats, data compounds, experiences improve
```

**What "following" means:** Once checked in, the diner becomes part of that venue's community. The venue can reach them — notifications, feed updates, new quests, special events. The diner sees that venue's activity in their feed alongside other followed venues. If they don't want to hear from a venue anymore, they unfollow. No Zomato-style consent popups, no phone number sharing debates. The check-in IS the relationship. The unfollow IS the exit.

Each cycle generates data. The AI agent learns. Recommendations get sharper. Quests get more relevant. The venue gets smarter without doing anything.

## The Dual Credit Economy

CheckIn runs on a two-currency system, each serving a distinct purpose. (Full details: product/credit-system.md)

### Venue Credits (VCs)

- Earned by completing quests and challenges at a specific venue
- Redeemable ONLY at that venue for goods, services, or experiences
- Non-transferable, non-exchangeable between venues
- Think: "loyalty points that actually work because they're tied to engagement, not just spending"
- Legal classification: loyalty points, exempt from VDA and PPI regulations (validated per CBDT Notification 74/2022)

### Global Credits (GCs)

- Earned through platform-wide activity (cross-venue visits, referrals, community contributions)
- Redeemable at ANY CheckIn venue
- Platform-wide currency that powers the discovery network
- Funded by brand partnerships and CheckIn's own engagement budget
- Creates the network effect: more venues = more places to earn and redeem = more valuable for every diner

### Three-Tier Hierarchy

| Level | Scope | Example | Revenue Angle |
|-------|-------|---------|---------------|
| Venue VCs | Single independent venue | A standalone café's loyalty points | CheckIn takes a cut per circulation cycle |
| Chain VCs | All outlets in a franchise/chain | "Social VCs" redeemable at any Social outlet | Platform/settlement fee to franchisor |
| Global Credits (GCs) | Every venue on CheckIn | Platform-wide discovery currency | Brand-sponsored campaigns, platform circulation |

This creates a natural upsell path: independent venues start with Venue VCs, chains upgrade to Chain VCs, and everyone participates in the GC ecosystem.

## The AI-Native Architecture

CheckIn is not SaaS with AI bolted on. The AI is the product.

### Per-Venue AI Agent

Every venue on CheckIn gets its own AI agent. This agent:

- **Learns** the venue's customer base — who visits, what they order, when they come, who they come with
- **Creates** quests and campaigns autonomously — tied to real business goals (move inventory, fill slow nights, reward regulars)
- **Personalizes** the diner experience — recommendations based on taste profile, not popularity
- **Optimizes** in real time — adjusts quest parameters based on completion rates, adjusts rewards based on margins
- **Grows** the venue's engagement — without the venue owner needing to do anything after initial setup

The agent operates within boundaries set by the venue (budget caps, approved reward types, brand guidelines) but is autonomous within those boundaries.

### Technical Stack

- **Framework:** Vercel AI SDK 6 + Next.js (AI-native, built for streaming and agent orchestration)
- **Database:** Supabase (Postgres + real-time + auth + edge functions)
- **Agent Protocol:** MCP (Model Context Protocol) — each venue agent connects to venue-specific data via MCP servers
- **Models:** Multi-model routing — Haiku for simple tasks, Sonnet for recommendations, Opus for complex campaign strategy
- **Cost per venue agent:** $4-14/month in inference costs vs ₹3K-15K/month pricing

(Full architecture details: product/architecture.md)

### Agentic Revenue

Traditional SaaS charges a flat subscription. CheckIn's revenue grows as the AI does more.

Month 1: Base platform, basic quests → ₹3,000/month
Month 3: AI runs campaigns, personalized recommendations → ₹3,000 base + ₹2,000 usage
Month 6: Full autonomy, inventory-linked quests, 2 plugins active → ₹3,000 base + ₹4,000 usage + ₹1,500 plugin revenue

Revenue correlates with value delivered. More engagement = more revenue = proof of value. This is the agentic revenue model — the AI itself generates revenue-producing actions.

(Full revenue model: product/revenue-model.md)

## What CheckIn is NOT

- **Not an aggregator in the Zomato/Swiggy sense.** CheckIn does aggregate venues on its platform — it has to, because the Global Credits economy and cross-venue discovery only work with a network of venues. But the aggregation model is fundamentally different. Zomato/Swiggy sit between the diner and the venue on every transaction, taking 15-28% commission and owning the customer relationship. CheckIn aggregates venues into a shared ecosystem where each venue owns its own customer data and relationships. Revenue comes from SaaS tiers and agentic value, not from taxing every order. If CheckIn provides payment gateway services, there will be a per-transaction processing fee — but that's infrastructure cost recovery, not a commission on food sales.
- **Not a delivery platform.** CheckIn is about the in-venue experience and direct customer relationships. Delivery aggregators provide genuine logistics value — CheckIn doesn't compete with that. Instead, CheckIn reduces a venue's *dependency* on aggregators by building direct customer relationships that drive organic footfall. A venue with loyal, returning customers needs Zomato less.
- **Not a POS system.** CheckIn integrates with existing POS (Petpooja, Posist, etc.) but doesn't replace it.
- **Not a discount platform.** This is a critical distinction from Zomato Pay / Swiggy Dineout. Those programs drive visits through mandatory 15-40% discounts that erode margins. CheckIn drives visits through quests, streaks, and earned rewards — the diner feels achievement, not entitlement. Credits are earned through engagement, not given away as coupons.
- **Not a generic loyalty tool.** Tools like Reelo do basic points-per-purchase. CheckIn's gamification engine (quests, streaks, social challenges) drives behavior change, not just reward accumulation.

## Who It's For (Target Market)

### Primary: Urban Independent F&B Venues in India

- Cafés, restaurants, bars, breweries, cloud kitchens with dine-in
- Located in urban clusters (starting: Indiranagar, Koramangala, Bangalore)
- Revenue: ₹10L-2Cr/month
- Currently have zero or basic loyalty/engagement systems
- Paying 15-30% to aggregators and want alternatives
- Tech-aware owners/managers (use Instagram, maybe a POS system)

### Secondary: F&B Chains and Franchises

- Multi-outlet operations wanting unified loyalty across locations
- Chain VCs enable cross-outlet redemption
- Higher ACV, longer sales cycle, but stronger retention

### Future: Any Venue with Repeat Customers

- Salons, gyms, co-working spaces, retail — the engagement model generalizes
- But F&B first, because visit frequency is highest and the aggregator pain is sharpest

## Go-To-Market: Services-Led Product Discovery

CheckIn's GTM is deliberately manual in Phase 1. This is not a weakness — it's the strategy.

**Months 1-6 (Now → Fundraise):**
The founding team does the work that AI agents will eventually automate at scale. Shash manually runs influencer campaigns — learning what works, what venues respond to, which messages convert. Ashish manually does venue onboarding and customer interviews while building the functional prototype. Aravind manually handles compliance and product specs.

Every manual workflow is documented in structured logs (learnings/). These logs become the training data and playbook for AI agents as the platform scales.

**Why this works:**
1. Manual work generates real customer data before the product is fully built
2. Founder-led sales creates deep understanding of venue pain points
3. The manual playbook becomes the AI agent's instruction set
4. Investors see a team that understands the business at ground level, not just the tech

**The pitch:** "We built the entire system before asking for money. We've done the work ourselves first. Now we need capital to put it in real venues and prove the economics."

(See: learnings/ai-to-product-map.md for the manual→AI mapping)

## Product Phases

### Phase 1: Prototype + MVP (Now — Pre-Seed)

**Phase 1A: The Prototype (Vision Demo)**

A vibe-coded front-end prototype demonstrating the full system, end to end. This is not the deployed product — it's the vision made tangible. It shows investors and venues what CheckIn becomes.

*Diner Side — Browser (No App Required):*
- Check-in flow via QR — identifies the diner, auto-follows the venue
- Quest system — active quests, progress tracking, completion
- Validation systems — proof of quest completion (order-linked, visit-linked, social-linked)
- Ordering — table-side ordering with recommendations
- Reward system — VC earning and redemption
- Gated rewards — leaderboards, collectibles, premium rewards visible but locked behind app download. Browser is the hook; app is the commitment

*Diner Side — App:*
- Discovery flow — browse venues, see what's happening, find new places via GCs
- User profile — taste profile, visit history, collections, achievements
- Feed — updates from followed venues (new quests, events, specials)
- Reward discovery — where to earn, where to redeem, what's expiring
- Coin tracker — VC and GC balances, transaction history, earning projections
- Leaderboards — venue-level and platform-level rankings
- Collections — badges, achievements, collectibles from venues
- Premium memberships — buy premium tiers at specific venues
- Streaks and gamified mechanisms — visit streaks, quest chains, social challenges
- Personal AI agent — suggests places, morning updates on followed venues, quest recommendations based on taste profile

*Venue Side:*
- Agentic backend — venue interacts with an AI agent (via WhatsApp) for business updates, quest suggestions, live quest performance, customer base questions
- Analytics dashboard — unified view of customer engagement, visit patterns, quest performance, revenue impact, VC circulation
- Campaign builder — create and manage quests, promotions, events, seasonal campaigns
- Feedback and complaints — customer feedback loop
- Plugin ecosystem showcase — karaoke, DJ integrations, event ticketing, table reservations, menu voting. Demonstrates extensibility

*Ecosystem:*
- Money flow diagrams — how venues pay (SaaS tiers, agentic usage, payment processing), how VCs circulate, how GCs are funded, how brand partnerships work
- Payment integration — subscription management, usage tracking

**What the prototype proves:** The full product vision is tangible. The team can build. The engagement loop makes sense. The agentic model is real. The monetization is logical. The platform has depth.

---

**Phase 1B: The MVP (First Deployment)**

The slice of the prototype that goes live in real venues. This is what we deploy to the first cohort in Indiranagar/Koramangala to prove the model works.

*What's in the MVP:*
- QR-based browser check-in and auto-follow
- Core quest system (visit streaks, menu exploration, social referrals)
- VC earning and redemption at venue
- Basic venue dashboard with customer analytics
- Venue campaign builder (manual quest creation)
- Gated app download flow

*What's NOT in the MVP (yet):*
- Full app with discovery, feed, personal AI agent
- GC cross-venue economy (needs venue density)
- Plugin ecosystem (needs venue feedback on what they want first)
- AI-driven autonomous quest creation (needs real data to train on)
- Brand partnerships and premium memberships

*Key Metrics We Track to Prove It's Working:*

| Metric | What It Proves | Target |
|--------|---------------|--------|
| Quest Completion Rate | Are quests engaging enough? | >40% |
| Return Visit Rate | Are diners coming back because of CheckIn? | >35% within 30 days |
| VC Redemption Rate | Are credits valuable enough to use? | >60% |
| QR → Check-in Conversion | Does the entry flow work? | >50% of scans |
| App Download Rate | Does the gated reward model drive installs? | >20% of browser users |
| Venue Retention | Are venues staying on after trial? | >80% after 3 months |
| Venue Owner NPS | Do venues actually like this? | >50 |

*The investor pitch:* "Here's the full vision [shows prototype]. Here's what we're deploying first [shows MVP]. Here's how we know it's working [shows metrics]. Here's how we scale to the full vision [shows Phase 2]."

### Phase 2: Intelligence & Expansion (Post-Seed, 0-12 months)
- Deploy app with discovery flow, feed, user profiles
- Per-venue AI agent learning from real customer data
- Automated quest creation tied to actual business goals (move inventory, fill slow nights)
- Personalized diner recommendations based on real taste profiles
- Global Credits launch across venue network (once venue density supports it)
- Diner-side personal AI agent goes live
- Iterate on plugin ecosystem based on venue demand
- Expand to additional Bangalore neighborhoods, validate unit economics

### Phase 3: Platform & Network Effects (12-24 months)
- Full agentic autonomy — venues set goals, AI handles execution
- Chain VC support for franchise operations
- Brand partnership marketplace (brands sponsor quests and GC campaigns)
- Third-party plugin marketplace
- Cross-city expansion
- Network effects compound — every new venue makes every existing venue more valuable

## Key Metrics (Scaling)

As CheckIn moves from MVP to scale, additional metrics come into play:

| Metric | What It Measures | Target |
|--------|-----------------|--------|
| Venue Monthly Active Users | Is the platform sticky for venues? | Growing MoM |
| Net Revenue Retention (NRR) | Are venues spending more over time? | >120% |
| Venue Churn | Are venues leaving? | <5% monthly |
| Cost Per Venue Agent | Is the AI economically viable? | <₹1,200/month ($14) |
| GC Cross-Venue Usage | Is the network effect working? | >15% of GC redemptions at non-home venues |

## Competitive Positioning

CheckIn operates in a different category than existing solutions:

| Dimension | Aggregators (Zomato/Swiggy) | Dine-In Programs (Zomato Pay/Swiggy Dineout) | Loyalty Tools (Reelo/Hashtag) | CheckIn |
|-----------|---------------------------|----------------------------------------------|-------------------------------|---------|
| Customer ownership | Aggregator owns; venue gets aggregate dashboards, masked contacts | Aggregator mediates even walk-in transactions | Venue has basic CRM data | Check-in = auto-follow. Venue has full profile of every diner who's checked in; diner can unfollow anytime |
| Cost to venue | 15-28% delivery commission + fees | 15-40% mandatory discount + 4-12% commission | Flat SaaS (₹2-5K/month) | Tiered SaaS + agentic usage; payment processing fee if using CheckIn payments |
| Engagement model | Discounts and listing rank | Discount-driven footfall | Points-per-purchase | Gamified quests, streaks, earned rewards |
| Data depth | Aggregate metrics (order volume, AOV, ratings) | Transaction data stays with platform | Transaction history, phone numbers | Full taste profile, behavioral patterns, social graph |
| Network effects | Discovery via aggregator | None (single-venue discounts) | None | Cross-venue credit economy |
| Intelligence | Platform-level analytics, not shared at individual level | None for venue | Basic analytics | Per-venue AI agent with diner-level intelligence |

CheckIn doesn't compete with Zomato's delivery logistics — that provides real value. CheckIn competes with the aggregator's grip on the customer relationship. By making in-venue experiences compelling enough to drive direct, repeated visits, CheckIn reduces a venue's dependency on both delivery commissions and dine-in discount programs.

(Full competitive analysis: product/competitive-landscape.md)

---

*Sources: Synthesized from Check-in Thesis V1, Investor Pitch Deck, Dual-Coin Economy compliance doc, Future Features concept doc, and iterative strategy sessions (Jan-Feb 2026).*

*This is the canonical product overview. All other documents should reference definitions and terminology from this file. If something here conflicts with another doc, this file wins.*
