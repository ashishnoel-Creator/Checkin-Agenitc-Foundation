# PRD — Venue Dashboard

> **Product:** CheckIn Venue Dashboard (Web Portal)
> **Last updated:** February 16, 2026
> **Owner:** Ashish
> **Platform:** Desktop/tablet web app (responsive, optimized for laptop + iPad)
> **Users:** Venue owners, venue managers, staff with dashboard access
> **Phase:** Phase 1A (Prototype) + Phase 1B (MVP deployment)

---

## Overview

The Venue Dashboard is how venue operators interact with CheckIn. It's a web-based control center where they set up their venue presence, create and manage quests, monitor real-time customer activity, view analytics, manage credits and rewards, communicate with their community, and — in later phases — interact with their AI agent.

The dashboard is designed for two personas: the **venue owner** (who cares about ROI, customer insights, and revenue impact) and the **venue manager/staff** (who handles day-to-day operations like verifying quests, confirming bills, and checking redemption codes).

**Core Design Principles**
- ROI-visible at every level — every screen should connect to business outcomes
- Quick setup, gradual depth — onboarding in under 30 minutes, advanced features revealed over time
- Real-time where it matters — check-ins, quest completions, and table activity update live
- Staff-friendly operations — bill verification, redemption codes, and quest confirmations are designed for speed during service
- Template-first quest creation — venues shouldn't need to design quests from scratch
- Data sovereignty — venue sees full profiles of their customers, not aggregated anonymized data

---

# Screen-by-Screen Flows

## Screen 1: Onboarding Wizard

*First-time setup — RM-assisted or self-service*

### 1A: Welcome & Account Setup

- Business name, legal entity name
- Primary contact: name, phone, email
- Location: address, Google Maps pin (auto-detected)
- Venue type: Café / Restaurant / Bar / Brewery / Pub / Cloud Kitchen / Other
- Cuisine tags: multi-select from standardized list
- Operating hours: per day of week, with holiday overrides
- Account role assignment: Owner (full access), Manager (operational access), Staff (verification-only access)

### 1B: Venue Branding

- Upload venue logo (square, for app cards and QR page)
- Upload hero/banner image (wide, for venue landing page)
- Accent color picker (used for CTA buttons on diner-facing pages)
- Tagline: short text (max 100 chars) — "Craft beer, live music, good vibes"
- Preview: live mockup of how the venue page will look to diners
- "Powered by CheckIn" badge placement shown (not removable)

### 1C: Menu Upload

- Option 1: Upload PDF menu → system extracts items (AI-assisted, manual review)
- Option 2: Manual entry — item name, price, category, dietary tags, photo (optional)
- Option 3: POS sync (if Petpooja/DotPe integrated) — auto-import menu items
- Categories: system suggests standard categories (Starters, Mains, Drinks, Desserts), venue can customize
- Dietary tags per item: Veg / Non-Veg / Vegan / Gluten-Free
- Menu can be updated anytime after setup

### 1D: Initial Quest Setup

- System presents 3 pre-configured quest templates (venue can customize rewards):
  - **Welcome Aboard:** "First check-in → {X} VCs" (default: 50 VCs)
  - **Raise the Stakes:** "Spend ₹{X}+ → earn {Y} VCs" (default: Spend ₹2,000 → 200 VCs)
  - **Loyalty Pays:** "Visit {X} times in {Y} days → {reward}" (default: 3 visits in 30 days → 100 VCs)
- Venue adjusts reward amounts and thresholds
- "Add more quests later" option — don't overwhelm during onboarding
- Brief explanation of each quest type with expected ROI estimates

### 1E: Credit & Redemption Rules

- VC redemption rate: how much value does 1 VC have? (Default: 1 VC = ₹1, venue adjustable)
- Bill coverage cap: max % of bill payable via VCs (default: 30%, venue adjustable)
- VC expiry: days until inactive VCs start decaying (default: 60 days)
- Welcome bonus: VCs given to first-time visitors (default: 50 VCs, venue adjustable)
- Rewards catalog: set up initial rewards ("Free Espresso: 500 VCs", "10% Off: 300 VCs", etc.)

### 1F: QR Code Generation

- System generates unique venue QR code
- Option for table-specific QR codes (generates batch: Table 1, Table 2, ... Table N)
- QR download in print-ready formats: PDF (A5 table tent), PNG (high-res)
- QR encodes: `checkin.app/{venue-slug}?table={table-id}`
- Preview: scan QR with phone to see the diner's landing page

### 1G: Onboarding Complete

- Checklist summary: ✓ Profile setup, ✓ Branding, ✓ Menu (or skipped), ✓ Quests configured, ✓ Credits set, ✓ QR generated
- "Your venue is live on CheckIn!"
- CTA: "Go to Dashboard →"
- Time target: complete onboarding in under 30 minutes

→ *Onboarding complete → Screen 2 (Dashboard Home)*

---

## Screen 2: Dashboard Home (Overview)

*The default screen — daily snapshot of venue performance*

### 2A: Top Navigation Bar

- Venue name + logo (top-left)
- Navigation tabs: **Home** | **Quests** | **Customers** | **Credits** | **Analytics** | **Community** | **Settings**
- Account menu (top-right): user name, role badge (Owner/Manager/Staff), switch venue (for multi-location), logout
- Notification bell: pending verifications, quest completions requiring action, system alerts

### 2B: Today's Snapshot (Hero Section)

Real-time metrics for the current day:

| Metric | Display | Why |
|--------|---------|-----|
| Check-ins today | "23 check-ins" with live counter | Primary engagement indicator |
| Active right now | "8 diners currently checked in" (live) | Shows real-time venue activity |
| Quests completed today | "14 quests completed" | Engagement depth |
| VCs earned today | "2,400 VCs distributed" | Credit circulation health |
| VCs redeemed today | "800 VCs redeemed" | Proves credits have real value |
| New followers | "+5 new followers today" | Community growth |

Each metric is tappable → drills into the relevant detail screen.

### 2C: Live Activity Feed

Real-time scrolling feed of events:
- "Rahul just checked in at Table 7" (2 min ago)
- "Priya completed 'Taste Adventure' — earned 300 VCs" (5 min ago)
- "Table 3 redeemed 'Free Espresso' — verify code: AX3K" (8 min ago)
- "New follower: Arjun S." (15 min ago)
- "Group of 4 checked in at Table 12 — Group Quest eligible" (20 min ago)

Each item has quick-action buttons where relevant (e.g., "Verify" on redemption items).

### 2D: Quick Actions Panel

- **Verify Redemption** → Enter/scan redemption code (most used during service)
- **Confirm Bill** → Approve pending bill submissions from diners
- **Create Quest** → Quick-launch quest creation
- **Send Announcement** → Push a message to all followers
- **Download QR** → Quick access to QR codes

### 2E: Performance Trends (Mini Charts)

- Check-ins: last 7 days trend line
- Quest completion rate: last 7 days
- VC circulation: earned vs. redeemed trend
- Top-performing quest this week

→ *Navigation tabs for all other screens*

---

## Screen 3: Quest Management

*Create, edit, monitor, and optimize quests*

### 3A: Active Quests List

Table view of all currently active quests:

| Column | Data |
|--------|------|
| Quest Name | "Taste Adventure", "Loyalty Pays", etc. |
| Type | Welcome / Bill Value / Frequency / Time-Based / Menu / Social / Group |
| Status | Active / Paused / Scheduled / Expired |
| Participants | Number of diners currently enrolled |
| Completion Rate | % of enrolled diners who completed |
| VCs Distributed | Total VCs awarded via this quest |
| Created | Date + who created it |
| Actions | Edit / Pause / Duplicate / Archive |

Sort by: newest, most popular, highest completion rate, most VCs distributed.

### 3B: Quest Creation (Template-Based)

**Step 1: Choose Quest Type**

| Template | Mechanic | Best For |
|----------|----------|----------|
| Welcome Aboard | Auto-complete on first check-in | Acquiring new visitors |
| Raise the Stakes | Min bill value threshold | Increasing average order value |
| Loyalty Pays | X visits in Y days | Driving repeat visits |
| Beat the Clock | Check in during specific time window | Filling slow hours |
| Taste Adventure | Try X menu items from a category | Menu exploration, cross-selling |
| Squad Mode | Bring X friends who check in | Viral growth |
| Table Challenge | Group bill exceeds threshold | Group spend |

**Step 2: Configure Parameters**

Each quest type has specific configuration fields:

*Example: Loyalty Pays*
- Visits required: [3] (number input)
- Time window: [30 days] (dropdown)
- Specific days only?: [Any day] / [Fridays only] / [Weekends only] / [Custom]
- Reward: [100 VCs] OR [specific reward from catalog]
- Auto-renewal: Yes/No (does quest reset after completion?)
- Max completions per user: [unlimited] / [specific number]

**Step 3: Set Validation Method**

| Method | Description | When to Use |
|--------|-------------|-------------|
| Automatic | System validates via check-in data, timestamps, POS data | Best for: Welcome, Loyalty Pays, Beat the Clock |
| Staff confirms | Dashboard notification → staff taps "Verify" | Best for: Bill value (no POS), Taste Adventure (no POS) |
| POS-linked | Auto-validate from POS bill/order data | Best for: Raise the Stakes, Taste Adventure (with POS integration) |

**Step 4: Preview & Launch**

- Preview: how the quest card looks to diners on the webapp
- Schedule: launch now OR schedule for future date/time
- "Launch Quest" button

### 3C: Quest Analytics (Per Quest)

When you click into a specific quest:
- Enrollment: how many diners are currently in progress
- Completion rate over time (line chart)
- Average time to completion
- Revenue impact: estimated additional revenue attributed to this quest
- VCs distributed vs. estimated COGS impact
- Drop-off analysis: at which stage do diners abandon?
- Top completers: which diners have completed this quest the most?

### 3D: AI Quest Suggestions (Phase 2)

- "Your Tuesday evenings have 40% fewer check-ins than average. Consider a 'Beat the Clock' quest for Tuesday 6-8pm with a 50% VC bonus."
- "Your Paneer Tikka hasn't been ordered this week. Create a 'Taste Adventure' quest featuring it?"
- "'Raise the Stakes' at ₹2,000 has a 65% completion rate. Try ₹2,500 to optimize revenue?"

Suggestions are actionable — "Create this quest" button turns the suggestion into a pre-filled quest creation flow.

---

## Screen 4: Customer Directory

*Every diner who has checked in — full profiles, not aggregated data*

### 4A: Customer List

Searchable, filterable table of all diners who have ever checked in:

| Column | Data |
|--------|------|
| Name | Diner name + avatar |
| Phone | Phone number (visible to venue — this is the key differentiator from aggregators) |
| Total Visits | Lifetime check-in count |
| Last Visit | Date of most recent check-in |
| VC Balance | Current VCs held at this venue |
| VCs Earned (Lifetime) | Total VCs ever earned here |
| VCs Redeemed (Lifetime) | Total VCs ever spent here |
| Quests Completed | Count of completed quests |
| Status | Active (visited in last 30 days) / At Risk (30-60 days) / Churned (60+ days) |
| Tags | Auto-tagged: "Regular", "High Spender", "Group Leader", "New" |

**Filters:**
- Status: Active / At Risk / Churned
- Tags: Regular / High Spender / Group Leader / New / Birthday This Month
- Visit frequency: Daily / Weekly / Monthly / One-Time
- VC balance: High (500+) / Medium (100-499) / Low (<100) / Zero
- Date range: first visit date, last visit date

**Actions on selection (multi-select):**
- Send targeted announcement to selected diners
- Create a quest visible only to selected segment
- Export customer list (CSV)

### 4B: Individual Customer Profile

Click into any diner:

- **Profile header:** Name, phone, avatar, member since date, total visits
- **Visit timeline:** Every check-in with date, time, duration, table number, group size
- **Quest history:** Every quest attempted and completed, with dates and rewards
- **Credit ledger:** Full transaction history at this venue (earned, redeemed, decayed)
- **Current VC balance** + expiry countdown
- **Spending behavior:** Average bill value (if POS integrated), frequency, preferred days, preferred items
- **Taste profile snapshot:** Cuisine preferences, dietary tags, order history highlights (if POS data available)
- **Social connections:** Friends who also visit this venue (opt-in data)
- **Notes:** Venue staff can add manual notes ("Birthday June 12", "Allergic to peanuts", "VIP — always give window seat")

### 4C: Customer Segments (Phase 2 — AI-Powered)

Pre-built and custom segments:
- **Regulars:** 4+ visits in last 30 days
- **At Risk:** Haven't visited in 30-60 days, had 3+ previous visits
- **Churned:** Haven't visited in 60+ days
- **High Spenders:** Top 20% by total bill value
- **Social Connectors:** Brought 3+ unique friends via Squad Mode
- **Credit Hoarders:** VC balance > 500, haven't redeemed in 30+ days
- **Birthday This Week:** Diners with upcoming birthdays

Each segment shows: count, trends (growing/shrinking), recommended actions.

---

## Screen 5: Credits & Rewards Management

*Control the venue's credit economy*

### 5A: Credit Overview

- **VCs in circulation:** Total VCs currently held by all diners at this venue
- **VCs earned (this month):** Total distributed
- **VCs redeemed (this month):** Total spent
- **Redemption rate:** % of earned VCs that get redeemed (health indicator)
- **Breakage (expired):** VCs lost to decay/expiry
- **Merchant Wallet balance:** VCs accumulated in the venue's B2B wallet (from diner redemptions)
- **VC liability estimate:** Current outstanding VC balance × redemption rate (accounting view)

Trend charts: earned vs. redeemed over last 30/90 days. Healthy economy = earned and redeemed lines close together.

### 5B: Rewards Catalog

Manage the rewards diners can redeem VCs for:

| Column | Data |
|--------|------|
| Reward Name | "Free Espresso", "10% Off Bill", "Secret Menu Item" |
| VC Cost | 500 VCs, 300 VCs, 1000 VCs |
| Category | Food / Drink / Experience / Discount |
| COGS Estimate | What this reward actually costs the venue |
| Redemptions (total) | How many times it's been redeemed |
| Status | Active / Paused / Sold Out |
| Inventory | Unlimited / Limited ({X} remaining) |

**Actions:**
- Add new reward
- Edit pricing / availability
- Pause / reactivate
- Set limited inventory (e.g., "Secret Menu Item — only 10 per week")

### 5C: Credit Rules Configuration

Editable settings (initially set during onboarding):
- VC redemption rate: ₹ value per VC
- Bill coverage cap: max % of bill payable via VCs
- Decay settings: inactivity days before decay starts, decay rate
- Welcome bonus amount
- Quest reward budgets: monthly cap on total VCs distributable

### 5D: GC Swap Management (Phase 2)

When Global Credits are active:
- Toggle: "Accept GC redemptions at this venue" (Yes/No)
- Reimbursement rate: shown as "CheckIn reimburses you ₹{X} per GC redeemed" (set by platform)
- Active swap bonuses: create/manage "Swap GC→VC" offers with minting bonuses
  - Bonus %: e.g., 50% bonus
  - Duration: active dates
  - Budget cap: max GCs accepted for swap
- GC redemption history: which diners redeemed GCs, amounts, reimbursement status

### 5E: Verification Queue

Live list of pending actions requiring staff attention:

| Item | Action Needed |
|------|--------------|
| Redemption code: AX3K (Table 7, Rahul) | "Free Espresso" — Tap to verify |
| Bill confirmation: ₹3,200 (Table 3, Priya) | Confirm bill amount matches POS |
| Quest completion: Taste Adventure (Table 12, Arjun) | Confirm diner ordered the required items |

Each item: one-tap verify or reject (with reason). Designed for speed — staff should process each in under 5 seconds.

---

## Screen 6: Analytics

*ROI-focused insights — prove CheckIn is working*

### 6A: Executive Summary

Top-level metrics with period comparisons (this week vs. last week, this month vs. last month):

| Metric | What It Shows |
|--------|--------------|
| Total check-ins | Volume of engaged diners |
| Unique visitors | Deduped — how many different people |
| New vs. returning | % split — is CheckIn driving repeat visits? |
| Return visit rate | % of visitors who come back within 30 days |
| Average visits per diner | Frequency metric |
| Quest completion rate | % of quests started that get completed |
| VC redemption rate | Are credits valuable enough to use? |
| Estimated revenue impact | Additional revenue attributed to CheckIn (quest-driven spend) |
| Community size | Total followers |
| Community growth rate | New followers per week/month |

### 6B: Check-In Analytics

- Check-ins by hour of day (heatmap — find peak and dead hours)
- Check-ins by day of week (bar chart — find slow days)
- Check-ins by table (if table-specific QRs — find popular vs. underused tables)
- Group size distribution: solo / pairs / 3-4 / 5+ (group engagement health)
- Check-in source: QR scan vs. app vs. search (where are diners coming from?)

### 6C: Quest Performance

- Completion rates by quest type (which mechanics work best for this venue?)
- Revenue per quest: estimated additional spend driven by each quest
- Quest ROI: VC cost (distributed) vs. revenue impact (additional spend)
- Time to completion: how long do quests take on average?
- Abandonment analysis: where do diners drop off?
- Comparative: this venue vs. platform average (anonymized benchmarking)

### 6D: Customer Insights

- Cohort analysis: retention curves by signup month (are newer cohorts more engaged?)
- Spending tiers: breakdown of diner base by spend level
- Visit frequency distribution: how many visit once, twice, 3+?
- Churn analysis: when do diners typically stop coming? What's the warning pattern?
- Top 10 customers by: visits, spend, quests completed, VCs earned

### 6E: Credit Economy Health

- VC circulation velocity: average time from earned → redeemed
- VC liability tracking: outstanding balance over time (should not grow unchecked)
- Earning vs. redemption balance (healthy = roughly equal)
- Decay/breakage trends: are credits expiring unused? (too much = reward catalog needs improvement)
- Reward popularity: which rewards are redeemed most/least?

### 6F: AI Insights (Phase 2)

- "Your Tuesday check-ins are 45% below average. A 'Beat the Clock' quest could drive 20-30 additional visits per month."
- "12 regular diners haven't visited in 3+ weeks. Sending them a personalized re-engagement offer could recover 6-8 visits."
- "Your 'Raise the Stakes' quest at ₹2,000 has a 70% completion rate. Consider testing ₹2,500 to optimize revenue."
- "Paneer Tikka has been ordered 40% less this week. A 'Taste Adventure' quest featuring it could move 15-20 portions."

Each insight has: data basis, confidence level, recommended action, and one-click quest creation.

---

## Screen 7: Community & Communication

*Direct channel to all diners who've checked in*

### 7A: Announcement Feed

Create and manage venue announcements visible to all followers:

- **New Post:** Rich text editor with image upload
  - Title, body text, image (optional)
  - Category: Event / Special Offer / Menu Update / General
  - Schedule: publish now or schedule for later
  - Preview: how it appears in the diner's app feed

- **Published Posts:** List with metrics per post:
  - Impressions (how many saw it)
  - Engagement (taps, reactions)
  - Resulting check-ins (diners who checked in within 48h of seeing the post)

### 7B: Targeted Messaging (Phase 2)

Send messages to specific customer segments:
- "Send to: Churned customers (60+ days)" → re-engagement message with bonus VCs
- "Send to: Birthday this week" → birthday reward offer
- "Send to: High spenders" → VIP event invitation
- "Send to: Credit hoarders" → redemption reminder

Channel: in-app notification + push notification (if enabled by diner). Never SMS or WhatsApp — all communication stays within CheckIn.

### 7C: Feedback & Reviews (Phase 2+)

- Post-visit feedback requests (automated, configurable timing)
- Feedback dashboard: ratings, text feedback, sentiment analysis (AI-powered)
- Response management: venue can respond to feedback
- Flagging: alert venue owner if rating drops below threshold

---

## Screen 8: AI Agent Interface (Phase 2)

*The venue's AI assistant — conversational control*

### 8A: Chat Interface

WhatsApp-style chat with the venue's AI agent. The venue owner/manager can:

- Ask questions: "How many check-ins did we have this week?"
- Request analysis: "Which quests are performing best?"
- Get suggestions: "What should I do about slow Tuesdays?"
- Create quests via conversation: "Create a happy hour quest for Thursday 5-7pm, 100 VCs"
- Review AI actions: see what the agent did autonomously (if autonomous mode is enabled)

### 8B: Agent Autonomy Settings

Configure what the AI agent can do without manual approval:

| Action | Autonomy Level |
|--------|---------------|
| Suggest quests | Always (suggestions only, no auto-creation) |
| Create quests | Needs approval (owner taps "Approve" in chat) / Auto-create within budget |
| Adjust quest parameters | Needs approval / Auto-adjust within bounds |
| Send announcements | Needs approval always |
| Customer re-engagement | Auto-send within approved templates / Needs approval |
| Analytics reports | Auto-generate and send weekly summary |

### 8C: Agent Activity Log

Transparent log of everything the agent has done:
- "Suggested 'Beat the Clock' quest for Tuesday 6-8pm" — Pending approval
- "Auto-adjusted Raise the Stakes threshold from ₹2,000 to ₹2,200 (completion rate was 85%)" — Within approved bounds
- "Sent weekly analytics summary to owner" — Automated
- "Flagged: 8 regular diners haven't visited in 3 weeks" — Awaiting owner response

---

## Screen 9: Settings

*Venue configuration, team access, integrations*

### 9A: Venue Profile

Edit all onboarding fields: name, address, hours, cuisine tags, logo, banner, tagline, accent color.

### 9B: Team Management

| Field | Description |
|-------|-------------|
| Invite member | Email/phone → role assignment |
| Roles | Owner (full access), Manager (all except billing/settings), Staff (verification + live activity only) |
| Access log | Who did what, when (audit trail) |
| Remove member | Revoke access |

### 9C: POS Integration

- Connect POS system: Petpooja / DotPe / PosBistro / Posist
- Connection status: ✓ Connected / ⚠ Sync error / ✗ Not connected
- Sync settings: menu auto-import, bill auto-populate, order data for quest validation
- Test connection: verify data is flowing correctly
- Fallback: if POS not connected, show "Manual mode active — staff confirms bills and quest completions"

### 9D: Subscription & Billing

- Current plan: Free / Premium / Enterprise
- Usage this month: check-ins, quests active, AI agent calls (Phase 2)
- Upgrade/downgrade plan
- Billing history: past invoices
- Merchant Wallet: VC balance that can offset subscription cost
- Payment method: card / UPI / bank transfer

### 9E: QR Code Management

- View/download all QR codes (venue-level and table-specific)
- Regenerate QR (if compromised)
- Generate additional table QRs
- Print templates: A5 table tent, A4 poster, receipt footer

### 9F: Notifications Preferences

- Email alerts: daily summary, real-time alerts for redemptions, weekly analytics report
- Dashboard alerts: which events show in the notification bell
- AI agent notifications: weekly summary, quest suggestions, churn alerts

---

## Staff Mode (Simplified View)

*Stripped-down interface for floor staff during service*

When a staff member logs in with the "Staff" role, they see only:

### Staff Screen 1: Live Activity

- Current checked-in diners (table assignments)
- Active group quests at each table

### Staff Screen 2: Verification Queue

- Pending redemption codes → one-tap verify
- Pending bill confirmations → one-tap approve/adjust
- Pending quest verifications → one-tap confirm/reject

### Staff Screen 3: Quick Search

- Search diner by name or phone → view their VC balance and active quests
- Useful for: "I have 500 credits, can I use them?" → staff can quickly check

Staff mode is optimized for mobile phone screens — designed to be used while walking the floor.

---

## Technical Flow Summary

### Data Architecture

```
Venue Dashboard (Next.js web app on Vercel)
  → Authenticates via Supabase Auth (email/password + role-based access)
  → Reads/writes to Supabase Postgres (venue config, quests, credits, customers)
  → Real-time updates via Supabase Realtime subscriptions (check-ins, quest completions)
  → POS integration via REST API (Petpooja etc.) for menu sync and bill validation
  → AI agent powered by Vercel AI SDK 6 + MCP (venue-specific context)
  → Analytics computed server-side (Edge Functions) with pre-aggregated views for performance
```

### Key Technical Decisions

| Decision | Choice | Why |
|----------|--------|-----|
| Platform | Web app (responsive) | Venue owners use laptops; staff use phones. No app install needed. |
| Auth | Email/password + role-based | Venues need team access. Phone OTP unnecessary for B2B. |
| Real-time | Supabase Realtime | Check-ins and verifications must update instantly during service. |
| POS integration | REST API, read-only + write-back for VC redemptions | Minimal integration surface. POS is source of truth for bills. |
| Analytics | Pre-aggregated materialized views + on-demand queries | Balance between real-time freshness and query performance. |
| AI agent chat | Vercel AI SDK 6 streaming + MCP for venue context | Agent can access venue-specific data without custom deployment. |

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| Onboarding completion | >90% | Venues that complete all setup steps within first session |
| Onboarding time | <30 min | Time from first login to venue going live |
| Daily active usage | >60% | Venues that log into dashboard at least once per day |
| Quest creation rate | >3 per venue per month | Venues actively creating/modifying quests |
| Verification turnaround | <2 min | Time from diner submitting redemption to staff verifying |
| Analytics engagement | >40% | Venues that view analytics at least weekly |
| Community post rate | >2 per venue per month | Venues actively posting to their followers |
| Venue NPS | >50 | Net Promoter Score from venue operators |
| Venue retention (3 month) | >80% | Venues still active 3 months after onboarding |
| Staff adoption | >70% | Venues where at least 1 staff member uses Staff Mode |

---

## Screen Map (Quick Reference)

| Screen | Name | Primary User | Key Actions |
|--------|------|-------------|-------------|
| 1 | Onboarding Wizard | Owner (+ RM) | Setup profile, branding, menu, quests, credits, QR codes |
| 2 | Dashboard Home | Owner / Manager | View today's snapshot, live activity, quick actions |
| 3 | Quest Management | Owner / Manager | Create, edit, monitor, and optimize quests |
| 4 | Customer Directory | Owner / Manager | Browse customer profiles, segment, export |
| 5 | Credits & Rewards | Owner / Manager | Manage rewards catalog, credit rules, verification queue |
| 6 | Analytics | Owner | ROI metrics, check-in analytics, quest performance, customer insights |
| 7 | Community | Owner / Manager | Post announcements, targeted messaging, feedback |
| 8 | AI Agent | Owner | Chat with venue AI, configure autonomy, review agent actions |
| 9 | Settings | Owner | Venue profile, team access, POS integration, billing, QR codes |
| Staff | Staff Mode | Staff | Live activity, verification queue, quick search |

---

## Phase Rollout

| Phase | Screens Included | Notes |
|-------|-----------------|-------|
| **1A (Prototype)** | All screens as mockups | Demonstrates full vision for investors |
| **1B (MVP)** | Screens 1, 2, 3, 4, 5, 9, Staff Mode | Core operational dashboard without AI or advanced analytics |
| **Phase 2** | Add Screens 6 (full), 7 (targeted messaging), 8 (AI Agent) | Intelligence layer + communication tools |
| **Phase 3** | Plugin management, multi-venue switcher, advanced CRM | Platform features for chains and power users |

---

*Sources: product/features.md (Venue Dashboard section), product/architecture.md (tech stack, data flow), product/revenue-model.md (pricing tiers, SaaS model), product/credit-system.md (VC mechanics, merchant wallet, B2B circulation), operations/venue-pipeline.md (onboarding process).*
