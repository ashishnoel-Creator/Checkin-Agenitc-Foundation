# Technical Architecture

> Last synthesized: Feb 15, 2026

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
- **Database:** Supabase (Postgres + real-time + auth + edge functions)
- **Agent Protocol:** MCP (Model Context Protocol) — each venue agent connects to venue-specific data via MCP servers
- **Models:** Multi-model routing — Haiku for simple tasks, Sonnet for recommendations, Opus for complex campaign strategy
- **Cost per venue agent:** $4–14/month in inference costs vs ₹3K–15K/month pricing

[TODO: Hosting, CI/CD, monitoring, deployment pipeline details]

## POS Integration Strategy

[TODO: Priority POS systems for integration (Petpooja, PosBistro, DotPe). API approach vs. middleware. Timeline.]

## Data Architecture

[TODO: Data flow diagrams, privacy architecture, analytics pipeline]

---

Sources: Check-in - Thesis, Checking V2-Working Doc, Checkin Whitepaper v1.1
