# CLAUDE.md — AI Agent Instructions for CheckIn Brain

> Last updated: Feb 16, 2026

## What This Repo Is

This is **CheckIn's internal knowledge base** — a structured, version-controlled repository containing the company's strategy, product thinking, market research, fundraise materials, and operational docs. It serves as the single source of truth for the founding team and any AI agents working on CheckIn-related tasks.

**CheckIn** is an AI-native F&B customer engagement platform. We help venues own their customer relationships through gamified experiences, a dual credit economy (Venue Credits + Global Credits), and per-venue AI agents. CheckIn is a **platform** ("Powered by CheckIn") — each venue gets a deep, customizable presence within it, but CheckIn is visible and branded, not white-label. We are starting with Food & Beverage in Bengaluru, India.

## Team

| Name | Role | Focus Areas |
|------|------|-------------|
| **Ashish** | Product / Builder / Technical Lead | Architecture, engineering, product build, investor relations |
| **Aravind** | Product / Compliance / Economy | Product strategy, regulatory structure, credit system compliance, legal frameworks |
| **Shash** | Marketing / Growth / Positioning | GTM strategy, branding, influencer playbook, user acquisition, content, positioning |

**Important:** Ashish is the primary technical builder and product lead. Do not confuse roles.

## Current Phase

- **Stage:** Pre-seed fundraise preparation
- **Target:** April 2026 fundraise
- **Location:** Bengaluru, India (beachhead market)
- **Status:** Building Phase 1A prototype (full vision demo) and Phase 1B MVP (first deployment slice), conducting customer discovery interviews, refining pitch materials

## Documentation Status (Feb 16, 2026)

**Investor-ready:** Deck outline, elevator pitches, Q&A prep (17+ questions), competitive landscape, credit system, revenue model, architecture, compliance, branding, marketing strategy

**Structure ready — awaiting founder inputs:** Financials (full model framework, needs raw numbers), team bios (template ready, each founder fills their own), runway (derived from financials), investor list (52 investors researched, needs warm intro mapping and live verification)

**Post-raise:** Learnings logs, influencer playbook details, partnership conversations, weekly standups

## Naming Conventions

- **Brand spelling:** "CheckIn" (capital C, capital I) — not "Checkin", "Check-In", or "CHECKIN"
- **Credit terminology:** "Venue Credits (VC)" — "Partner Coins (PC)" is deprecated
- **Founder-dependent content:** Marked with `[FOUNDER INPUT NEEDED]` — these are blocking items that require human input
- **Post-raise items:** Marked with `[POST-RAISE]` or left in Phase 4 files
- **Source doc references:** Original Google Drive doc names appear in source attribution lines (e.g., "Checkin: Investor Pitch Deck") — these reference the original doc names, not the brand spelling

## Key Files to Read First

1. `CLAUDE.md` — You're here. Start here always.
2. `product/overview.md` — What CheckIn is and why it exists
3. `product/credit-system.md` — The VC/GC dual credit economy (core IP)
4. `product/competitive-landscape.md` — How we position against incumbents
5. `fundraise/deck-outline.md` — Investor pitch structure and key messages
6. `fundraise/elevator-pitches.md` — Approved pitches for different audiences
7. `operations/compliance.md` — Regulatory and tax structure (India-specific)

## Work Conventions

### Branching
- `main` = source of truth (always deployable/readable)
- `ashish/*` = Ashish's working branches
- `aravind/*` = Aravind's working branches
- `shash/*` = Shash's working branches
- All merges to `main` require PR approval from at least one other co-founder

### Editing Rules
- **Never delete content** — move deprecated content to `archive/` with a date stamp
- **Date-stamp all edits** — add "Last updated: [date]" at top of any modified file
- **Source attribution** — when synthesizing from Google Drive docs, list source doc names at bottom of file
- **Mark uncertainty** — use `[NEEDS REVIEW]` for anything unverified, `[FOUNDER INPUT NEEDED]` for gaps requiring human input, `[POST-RAISE]` for items deferred until after funding

### File Format
- All content files are Markdown (`.md`)
- Use headers (`##`) for sections, not deep nesting
- Keep files focused — one topic per file, cross-reference with relative links
- Tables for structured comparisons, prose for narrative content

## Repo Structure

```
checkin-brain/
├── CLAUDE.md                          # AI agent instructions (this file)
├── README.md                          # Repo overview for humans
├── company/                           # Company-level docs
│   ├── vision.md                      # Mission, vision, values
│   ├── team.md                        # Team bios, roles, strengths
│   ├── decisions-log.md               # Key decisions and rationale
│   └── runway.md                      # Financial runway tracking
├── product/                           # Product docs
│   ├── overview.md                    # What CheckIn is
│   ├── architecture.md                # Technical architecture (3-tier stack)
│   ├── features.md                    # Feature inventory (prioritized)
│   ├── roadmap.md                     # Phased development plan
│   ├── competitive-landscape.md       # Competitor analysis + positioning
│   ├── credit-system.md              # VC/GC dual credit economy
│   ├── revenue-model.md              # Monetization strategy
│   └── user-research/
│       ├── venue-interviews.md        # Customer discovery framework + findings
│       ├── personas.md                # User and venue personas
│       └── insights.md               # Synthesized research insights
├── fundraise/                         # Fundraise materials
│   ├── timeline.md                    # Fundraise milestones
│   ├── investor-list.md              # Target investors
│   ├── deck-outline.md               # Pitch deck structure
│   ├── financials.md                  # Financial projections
│   ├── qa-prep.md                     # Investor Q&A preparation
│   └── elevator-pitches.md           # Approved elevator pitches
├── marketing/                         # Marketing docs
│   ├── strategy.md                    # Marketing strategy
│   ├── branding.md                    # Brand guidelines
│   ├── influencer-playbook.md        # Influencer campaign playbook
│   └── campaigns/                     # Campaign-specific docs
├── operations/                        # Operations docs
│   ├── venue-pipeline.md             # Venue onboarding pipeline
│   ├── compliance.md                  # Regulatory and compliance
│   ├── partnerships.md               # Partnership strategy
│   └── weekly-standup.md             # Standup template/notes
├── learnings/                         # Individual learning logs
│   ├── ashish-builder-log.md         # Ashish's builder log
│   ├── shash-marketing-log.md        # Shash's marketing log
│   ├── aravind-product-log.md        # Aravind's product log
│   └── ai-to-product-map.md         # AI capabilities mapped to product
├── templates/                         # Reusable templates
│   ├── weekly-update.md              # Weekly update template
│   ├── venue-interview.md            # Venue interview template
│   └── decision-record.md           # Decision record template
└── archive/                           # Deprecated content (never delete, move here)
```

## Context for AI Agents

When working on tasks for CheckIn, keep these principles in mind:

- **We are pre-product, pre-revenue.** Everything is hypothesis-driven right now. Customer discovery is ongoing.
- **F&B is our beachhead, not our ceiling.** The platform is designed to expand to retail, wellness, and live events.
- **The dual credit system is our core moat.** VC (Venue Credits) for local loyalty, GC (Global Credits) for cross-venue liquidity. Understand it deeply before writing about it.
- **We compete on experience, not price.** Zomato/Swiggy have deeper pockets. We win through gamification, community, and venue data sovereignty.
- **CheckIn is a platform, not white-label.** Each venue has a deep customizable presence within CheckIn, but CheckIn is visible and branded. When a diner leaves the venue page, they're on the broader CheckIn platform.
- **CheckIn does aggregate venues — but differently.** We're not an aggregator in the Zomato/Swiggy sense. Revenue comes from SaaS + agentic value, not per-order commissions. If CheckIn provides payment gateway services, a per-transaction processing fee applies — that's infrastructure cost recovery, not a food commission.
- **Data asymmetry is nuanced.** Aggregators give venues aggregate dashboard data (order volumes, AOV, ratings). What they don't share is individual customer identity — masked phone numbers, no per-diner behavioral profiles. The accurate framing: venues get reporting (backward-looking dashboards), not intelligence (forward-looking, per-diner, actionable).
- **Check-in = auto-follow.** When a diner checks in, they auto-follow the venue. No consent popups — the physical act of visiting is the consent. Diner can unfollow anytime.
- **Bengaluru first.** All GTM plans center on Koramangala, Indiranagar, HSR Layout clusters.
- **April 2026 fundraise deadline.** All work should ladder up to being investor-ready.

---

Sources: Checkin: Investor Pitch Deck (Full Script & Content), Check-in - Thesis, Checking V2-Working Doc, Dual-Coin Economy for CheckIn, GC/VC Specific - Utility and Compliance, Customer Discovery v2 Final
