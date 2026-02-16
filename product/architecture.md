# Technical Architecture

> Last updated: Feb 16, 2026

## Three-Tiered Architecture

### Tier 1: The CheckIn Stack (Foundation)

| Component | Description |
|-----------|-------------|
| **Core OS (The Nexus Core)** | Open, API-first foundation for integrations and extensibility. Designed to be vertical-agnostic. |
| **Value Engine** | Flexible system for creating and exchanging value — spendable credits, status-based stars, collectible badges. Supports both Venue Credits (closed-loop) and Global Credits (cross-venue). |
| **Quest Engine** | Advanced rules-engine injecting dynamic, game-like challenges. Supports individual and group quests, streaks, time-based, bill-value, menu-item, and frequency-based mechanics. |
| **Community Graph** | Network mapping real-world social connections between users and venues. Tracks visit patterns, friend connections, leaderboard positions, group dynamics. |

### Tier 2: The Application Layer

| Product | Description |
|---------|-------------|
| **Unified Consumer App** | Single mobile app for all venues. QR check-in → web app initially, then native (iOS/Android). |
| **Venue Dashboard** | Web portal for quest creation, analytics, community management, direct communication, credit rules. |
| **Plugin Marketplace** | Extensible module system — karaoke, DJ requests, table booking, advanced feedback, gamification plugins. |

### Tier 3: The Intelligence Layer

| Component | Description |
|-----------|-------------|
| **Synapse Engine** | AI-powered analysis layer. Predictive insights for venues (churn detection, upsell opportunities, optimal quest timing). Hyper-personalized experiences for users (menu recommendations, venue suggestions). |

### Cross-Cutting: Identity & Trust Fabric

User-owned identity with bank-grade security and transparent privacy controls. Foundation for future Web3/decentralized identity integration.

## Verification System (Anti-Bot)

- **QR Code:** Venue-specific, session-specific
- **OTP:** Unique per table/session, device-locked
- **GPS:** Validates physical presence at venue
- **Group Mode:** Encourages real social presence (multiple devices at same location)

## Technical Stack

Per canonical product overview (Feb 16, 2026):

- **Framework:** Vercel AI SDK 6 + Next.js (AI-native, built for streaming and agent orchestration)
- **Database:** Supabase (Postgres + real-time subscriptions + auth + edge functions + storage)
- **Agent Protocol:** MCP (Model Context Protocol) — each venue agent connects to venue-specific data via MCP servers
- **Models:** Multi-model routing — Haiku for simple tasks (~₹300/venue/month), Sonnet for recommendations (~₹800/venue/month), Opus for complex campaign strategy (on-demand)
- **Cost per venue agent:** ₹300–1,100/month blended inference cost vs. ₹3K–15K/month pricing = 3–5x margin

## Hosting & Deployment

- **Hosting:** Vercel (frontend + API routes + edge functions) + Supabase Cloud (database + auth + real-time)
- **CI/CD:** GitHub Actions for automated testing and deployment on push to main
- **Monitoring:** Vercel Analytics (frontend performance) + Supabase Dashboard (database metrics) + custom logging for agent inference costs
- **Environments:** Development → Staging → Production, with branch previews on Vercel
- **Domain:** [FOUNDER INPUT NEEDED — primary domain for app and dashboard]

**Why this stack:** Vercel + Supabase = zero DevOps overhead for a 3-person team. Both scale automatically. AI SDK 6 provides native agent orchestration (tool calling, streaming, multi-model routing) without custom infrastructure. MCP protocol means each venue agent is a configuration, not a deployment — adding a new venue = adding a data source, not spinning up a server.

## POS Integration Strategy

### Priority Order

| POS System | Priority | Market Share (India) | Integration Approach | Timeline |
|-----------|----------|---------------------|---------------------|----------|
| **Petpooja** | P0 — First integration | Dominant in Bengaluru indie F&B | REST API (well-documented) | Phase 1B MVP |
| **PosBistro** | P1 | Growing in premium segment | API available | Post-MVP, Month 3–4 |
| **DotPe** | P1 | Strong in QR ordering | API + webhook-based | Post-MVP, Month 3–4 |
| **Posist** | P2 | Enterprise/chain focus | API available | Month 6+ (when chains onboard) |

### Integration Approach

- **Method:** API-first, not middleware. Direct REST API calls from CheckIn backend to POS systems.
- **Data flow:** CheckIn reads menu items, order history, and bill data from POS. CheckIn writes VC redemptions as discounts/adjustments back to POS.
- **Fallback:** For POS systems without APIs, manual entry via venue dashboard (staff confirms quest completion, enters bill total). This works for MVP.
- **Privacy:** Customer data stays in CheckIn. POS integration is read-only for menu/orders, write for VC redemptions only.

## Data Architecture

### Core Data Flow

```
Diner scans QR at venue
  → Browser app loads (Vercel Edge)
  → Auth via Supabase (phone OTP or social login)
  → GPS validation confirms venue presence
  → Auto-follow: diner profile linked to venue in Community Graph
  → Active quests loaded from Quest Engine (Supabase real-time)
  → Diner completes actions (orders, visits, social)
  → Quest Engine validates completion (POS data or manual confirmation)
  → Value Engine mints VCs to diner wallet
  → Venue Dashboard updates in real-time (Supabase subscriptions)
  → Synapse Engine (AI) analyzes patterns, suggests next quest
  → AI Agent sends personalized follow-up (if enabled by venue)
```

### Key Data Entities

| Entity | Storage | Privacy Level |
|--------|---------|---------------|
| Diner profiles | Supabase (Postgres) | Venue-owned (visible to venues diner has checked into) |
| Visit history | Supabase (Postgres) | Venue-owned per venue, aggregated for platform analytics |
| Quest progress | Supabase (real-time) | Diner-owned, venue can see completion status |
| Credit balances (VC/GC) | Supabase (Postgres, transactional) | Diner-owned, venue sees circulation metrics |
| Community graph | Supabase (Postgres) | Platform-level, anonymized for analytics |
| AI inference logs | Supabase (Postgres) | Platform-internal, used for cost tracking and model improvement |

### Privacy Architecture

- **Venue data sovereignty:** Each venue sees only diners who have checked in at their venue. No cross-venue diner data sharing without diner opt-in.
- **Diner data portability:** Diners can export their full profile (visit history, credits, preferences) at any time.
- **Data deletion:** GDPR-aligned right to deletion. Diner can delete profile; venue loses access to that diner's data.
- **Encryption:** All data encrypted at rest (Supabase default) and in transit (TLS 1.3).

---

Sources: Check-in - Thesis, Checking V2-Working Doc, Checkin Whitepaper v1.1
