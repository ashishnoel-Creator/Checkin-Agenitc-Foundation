# Investor Q&A Preparation

> Last updated: Feb 16, 2026

## Anticipated Questions

### Market & Competition

- **Q: How do you compete with Zomato/Swiggy?**
  A: We don't compete on delivery — we compete on dine-in experience where they're weakest. Their model is transactional; ours is emotional and gamified. We give venues data sovereignty they'll never get from aggregators.

- **Q: What stops Zomato from copying this?**
  A: Their DNA is delivery and discovery, not in-venue engagement. Gamified loyalty with group dynamics, community features, and venue-specific currencies is architecturally different from discount subscriptions. Also, venues are actively looking for alternatives to aggregator dependency — they won't trust the fox guarding the henhouse.

- **Q: How is this different from Reelo or other Indian loyalty SaaS?**
  A: Reelo is B2B-only with basic points/cashback. We offer a unified consumer platform with social gamification, group quests, credit pooling, and community features. No Indian SaaS combines venue empowerment with consumer engagement.

- **Q: Aren't you just another aggregator?**
  A: CheckIn does aggregate venues — the GC economy and cross-venue discovery require a network. But the model is fundamentally different from Zomato/Swiggy. The venue owns every customer relationship (check-in = auto-follow, venue gets full diner profiles). Revenue comes from SaaS tiers and agentic AI usage, not per-order commissions. If we provide payment gateway services, there's a per-transaction processing fee — but that's infrastructure cost recovery, not a food commission. Zomato sits between diner and venue on every transaction; CheckIn empowers the venue to build its own community.

- **Q: Don't aggregators already share data with venues?**
  A: They give venues aggregate dashboards — order volumes, AOV, ratings, operational metrics. But no individual customer identity: phone numbers are masked, no per-diner behavioral profiles. Even Zomato's late-2025 data-sharing initiative only shares phone numbers with customer opt-in — and a phone number without context is just spam fuel, not a customer relationship. CheckIn gives venues full profiles of every diner who's checked in: visit patterns, taste preferences, spending behavior, social connections.

### Business Model

- **Q: Why will venues pay for another tool?**
  A: Venues already spend ₹30K–1L/month on marketing with zero attribution. We offer measurable ROI at ₹2K/month — a fraction of what they waste on untracked Instagram and aggregator spend.

- **Q: What's your path to profitability?**
  A: Our unit economics are designed for efficiency. At ₹2K/month premium tier with RM-led onboarding, venue CAC payback is under 6 months. As agentic usage grows (₹3K → ₹5K → ₹8.5K/month), ARPU increases while acquisition costs stay flat. At ~100 premium venues (achievable within 12 months in Bengaluru), SaaS revenue covers team burn. Phase 2 ecosystem revenue (brand partnerships, breakage, transaction fees) adds margin. Full P&L in `fundraise/financials.md`. [FOUNDER INPUT NEEDED — update with specific numbers once financials are locked]

- **Q: What if venues churn after the free trial?**
  A: Three retention mechanisms: (1) Data lock-in — venues accumulate customer profiles and community data they can't get elsewhere. (2) Credit lock-in — active VC circulation creates switching costs for both venue and diners. (3) Agentic value — AI agent autonomously drives measurable repeat visits, making the ROI visible. Our target churn is <5%/month. If we see higher churn, it signals product-market fit issues we need to address before scaling.

### Product & Technology

- **Q: How do you solve the cold-start problem?**
  A: Venue Credits function as standalone B2B loyalty tools even before the network forms. Venues get value from day one. Hyperlocal cluster strategy in 3 neighborhoods creates local density fast.

- **Q: What about the credit system regulatory risk?**
  A: Both VCs and GCs are structured as non-VDA loyalty points under CBDT Notification No. 74/2022. The key architectural decision: GCs sit on a centralized database ledger (not blockchain), are earned only through non-monetary activity, have no fiat off-ramp, and no P2P trading — structurally identical to airline miles, CRED coins, or Paytm cashback. Zero tax burden on users. GC bill payments are capped at X% of bill value as an additional safeguard. The original design treated GCs as VDA tokens with 30% tax — we restructured to eliminate that entirely. See `operations/compliance.md` and `product/credit-system.md`.

- **Q: How do you build AI agents for every venue economically?**
  A: Multi-model routing. Simple tasks (notifications, basic responses) use Haiku at ~₹300/month per venue. Personalized recommendations use Sonnet. Complex strategy uses Opus. Blended inference cost is ₹300–1,100/month per venue vs. ₹3K–15K/month pricing = 3–5x margin. The MCP (Model Context Protocol) architecture means each venue agent connects to venue-specific data without retraining.

- **Q: What if diners don't adopt — why would they scan a QR code?**
  A: The QR scan is the lowest-friction entry point possible — no app download required (browser-first). The immediate value is seeing active quests and earning credits on their current visit. Gated features (leaderboards, collections, personal AI) drive app download for engaged users. In-venue is the highest-intent moment — they're already there, already spending. Group quests add social pressure ("your table hasn't completed the quest yet").

- **Q: Why not white-label for each venue?**
  A: White-label kills network effects. The GC economy, cross-venue discovery, and community graph all require a unified platform. White-label also means each venue bears the acquisition cost of their own app — with 96% of apps uninstalled within the first month, that's a losing proposition. CheckIn as a platform means diners discover new venues organically.

### Moat & Defensibility

- **Q: What's your moat?**
  A: Five compounding moats: (1) Network effects — dense venue clusters create local lock-in. (2) Data sovereignty — venues retain customer data, creating switching costs. (3) Credit lock-in — venue-specific VCs can't leave the ecosystem. (4) Community graph — real-world social connections are proprietary. (5) Intelligence layer — rich diner interactions generate insights no competitor has. These compound over time — the moat deepens with every check-in.

- **Q: What happens if a large competitor enters this space?**
  A: Our advantage is focus and speed. Large companies (Zomato, Swiggy, Google) optimize for delivery/discovery, not in-venue engagement. Building gamified loyalty with AI agents is a fundamentally different product requiring different DNA. Even if they enter, our data moat (per-diner profiles, community graph) and credit lock-in (VC/GC economy) create real switching costs. First-mover in hyperlocal cluster density is hard to replicate.

### Team

- **Q: Why this team?**
  A: [FOUNDER INPUT NEEDED — Each founder writes their narrative. Template: "Ashish brings [X years] of [domain] experience from [companies]. He [specific accomplishment]. Aravind designed [specific thing] and has [expertise]. Shash has driven [specific results] in [domain]." The narrative should show why these three people — specifically — are the right team for this problem.]

- **Q: You're a 3-person team with no revenue — why should we bet on you?**
  A: Three reasons: (1) We've done the homework — this repo demonstrates deeper market understanding than most seed-stage companies. We understand the regulatory landscape, competitive dynamics, and unit economics before writing a line of product code. (2) We're building, not just planning — Phase 1A prototype is in development, customer discovery is underway. (3) Complementary skills with zero overlap — product/engineering, compliance/economy, and growth/marketing are the three pillars this business needs. No redundancy.

### Traction & Validation

- **Q: What traction do you have?**
  A: [FOUNDER INPUT NEEDED — update after interviews begin. Template: "We've completed [X] customer discovery interviews with venue owners in Bengaluru. Key findings: [Y]% validated our hypothesis that [Z]. Average willingness to pay: ₹[W]/month. [N] venues have expressed interest in piloting. Our Phase 1A prototype demonstrates [specific features]. We have [any LOIs, commitments, or verbal agreements]." Update this answer weekly as data comes in.]

- **Q: Do you have any LOIs or commitments from venues?**
  A: [FOUNDER INPUT NEEDED — update as venue conversations progress. Even soft verbal commitments like "I'd try this" from interviews count at pre-seed stage.]

### Risk & Downside

- **Q: What are your biggest risks?**
  A: (1) **Venue adoption velocity** — if we can't onboard 10+ venues/month in Bengaluru, the cluster density thesis breaks. Mitigation: RM-led high-touch onboarding, freemium tier lowers barrier. (2) **Diner engagement** — if quest completion stays below 20%, the value prop weakens. Mitigation: gamification design informed by gaming industry (Ashish's background), iterate rapidly based on real data. (3) **Regulatory** — GC reclassification as VDA would trigger 30% tax + 1% TDS. Mitigation: GCs are structured as non-VDA loyalty points (centralized ledger, no cash purchase, no fiat off-ramp, no P2P trading) with belt-and-suspenders safeguards including bill payment caps (see `operations/compliance.md` and `product/credit-system.md`).

- **Q: What's the downside scenario?**
  A: Bear case: venue onboarding is slower than expected (5/month vs. 10/month target). In this scenario, we still reach 50 venues by M10–12 and have enough data to demonstrate product-market fit, but seed raise timing pushes by 3–6 months. The ₹[raise amount] with 15–18 months runway gives us room for this scenario. If the fundamental thesis is wrong (venues don't want to own customer relationships), we'll know within 6 months from interview and pilot data — early enough to pivot the approach, not the mission.

- **Q: What if the Indian F&B market contracts?**
  A: India's organized F&B sector is growing at 13.2% CAGR — contraction is unlikely in our time horizon. But even in a downturn, our value proposition strengthens: venues under margin pressure need to reduce aggregator dependency (15–30% commissions) and improve retention (cheaper than acquisition). CheckIn at ₹2K/month is the cheapest tool in their stack — it's the last thing they'd cut.

---

Sources: Checking V2-Working Doc, Porter's 5 Forces Analysis, product/overview.md, product/competitive-landscape.md, operations/compliance.md, product/architecture.md
