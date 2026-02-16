# Future Features & Concepts — Idea Dump

> Last updated: Feb 16, 2026

This document captures post-MVP feature ideas discussed by the founding team. Each is categorized by domain and tagged with a target phase. These are hypotheses — not commitments.

**Phase key:** V1.5 = near-term post-MVP | V2.0+ = longer-term | V3.0+ = ambitious/platform-level

---

## 1. Gamification & Loyalty Mechanics

### 1.1 Collectable Wall / Annual Event Passport `V1.5`

Venues pre-define signature events for the year (Summer Fest, Oktoberfest, NYE). Each event has a unique digital sticker/badge. Diners must attend and complete a special "Collectable Quest" to earn it for their personal Collector Board.

- **Why:** "Gotta catch 'em all" psychology. Drives targeted attendance to specific high-value events and creates long-term engagement loops.
- **Requires:** Events module in venue dashboard, digital collectable asset system, new quest type, collector leaderboard.

### 1.2 Dual Wallet System `V1.5`

Split VC wallet into two sub-wallets:
- **Session Pot ("Immediate"):** Credits earned during current visit. Only ~50% redeemable on current bill.
- **Personal Vault ("Later"):** Unused session credits transfer here after 24 hours. Fully redeemable on future visits (up to venue-defined cap).

- **Why:** Instant gratification now + strong return-visit incentive later. Users can strategically save for bigger redemptions (e.g., hosting a party).
- **Requires:** Backend logic for credit batches with different redemption rules. Clear UI to avoid user confusion.

### 1.3 Diminishing Value for Inactive Credits `V1.5`

Instead of binary expiry, credits gradually decrease with inactivity — e.g., 10 credits/week diminish after 1+ month of no visits.

- **Why:** Continuous loss-aversion nudge is more engaging than a sudden expiry. Gentler but persistent psychological pull.
- **Requires:** Weekly background job checking inactivity across all user-venue pairs. Clear communication so it doesn't feel punitive.

### 1.4 Venue-Specific Daily Streaks `V1.5 → V2.0`

Consecutive daily check-in multiplier on earned credits. Day 2: 1.1x → Day 3: 1.2x → caps at 2x. Miss a day, streak resets. Venues toggle it on/off.

- **Why:** Ideal for high-frequency spots (coffee shops, juice bars, lunch spots). Gamifies daily routines.
- **V1.5 scope:** Simple backend tracker, toggle in venue dashboard, flame icon with streak count (🔥) on venue page.
- **V2.0 enhancements:** Venue-controlled multiplier rates, "Streak Freeze" items, streak leaderboards, reminder notifications.

---

## 2. Platform Utility & User Experience

### 2.1 Wi-Fi Access on Check-In `V1.5/V2.0`

Auto-authenticate diner's device with venue Wi-Fi upon successful check-in. No passwords, no captive portals.

- **Why:** Immediate, tangible utility for every check-in. Also doubles as physical presence verification (anti-spoofing).
- **Requires:** Partnerships with Wi-Fi hardware providers (Cisco Meraki, Aruba) that offer authentication APIs. Low standardization across venues — selective rollout first. `[NEEDS REVIEW]`

### 2.2 Integrated Mobile Ordering & Order Tracking `V2.0+`

Two approaches considered:

**Option A — Full In-App Ordering:** Browse menu → in-app cart → order submission → real-time status ("Preparing → Cooking → Delivered to Table") with ETAs. Venue gets KDS-style dashboard.

**Option B — QR Code Injection (preferred for V2):** User builds order in app → generates one-time QR → server/bartender scans → injects order into POS/KDS. Real-time tracker starts on user's phone.

- **Why:** Reduces wait times and verbal order errors (especially in loud venues). Auto-validates transaction-based quests. Rich item-level data for personalization.
- **Requires:** Deep POS/KDS integration (major undertaking), Menu Management System in venue dashboard, real-time WebSocket infrastructure. `[NEEDS REVIEW]`

### 2.3 Dynamic In-App Event Banner `V1.5`

When a checked-in diner is at a venue with an active event/promoter, a scrolling banner appears: "LIVE NOW: DJ Gemini on the decks!" or "TONIGHT'S SPECIAL: Oktoberfest Happy Hour!"

- **Why:** Creates dynamic "live" feeling. Drives participation in active events. Adds visibility for promoters and event organizers.
- **Requires:** New field in venue dashboard (banner text + schedule/promoter link). Conditional banner rendering on venue page post-check-in. Primarily front-end work.

### 2.4 Live Visual Editor / Brand Studio `V1.5`

WYSIWYG editor in venue dashboard — real-time preview of how venue page looks in the app. Change profile pic, banner image, colors, icon styles instantly.

- **Why:** Empowers venues to own their digital storefront without support tickets. Foundation for the more advanced Skins/Themes system later.
- **Requires:** Front-end component mimicking mobile UI within the web dashboard. Guardrails (curated color palette) to prevent garish combinations. Image upload/resize pipeline.

---

## 3. Community & Social Features

### 3.1 AI-Powered Group Outing Planner `V2.0+`

Create a temporary group with friends → CheckIn AI analyzes collective preferences, credit balances, active offers → suggests optimal venue.

- **Why:** Solves the universal "where should we go?" friction. Helps users optimize their credits. Drives traffic to partner venues.
- **Requires:** Robust user preference data, recommendation engine (AI/ML), simple group creation UI. Consent-aware.

### 3.2 Enhanced Public User Profiles `V2.0+`

Optional, privacy-controlled public profile showcasing a diner's F&B identity: favorite venue types, preferred cuisines, check-in badges (e.g., "50 unique cafés"), leaderboard positions.

- **Why:** Social discovery by shared taste. Status and self-expression layer within the ecosystem.
- **Requires:** Granular privacy controls (public / private / friends-only per field). `Privacy-first design is non-negotiable.`

### 3.3 User-Driven Meetups ("Open Tables") `V2.0+`

Users host themed events at partner venues — "Book Club Meetup," "Board Game Night," "Startup Founders Networking." Set entry contribution (if any), publicize to community or invite-only.

- **Why:** User-generated community layer. Drives pre-organized, guaranteed traffic to venues. Positions CheckIn as a social hub, not just loyalty.
- **Requires:** Event creation, RSVPs, optional pre-payments, moderation/safety tools, venue partnership facilitation.

### 3.4 Promoter Engine ("Proof of Influence") `V2.0+`

Platform within venue dashboard for managing performance-based promoter/influencer collaborations. Promoters get unique invite codes → system tracks attributed cohort (footfall, total spend, visit frequency, retention). Promoter gets a verified metrics dashboard.

- **Why:** Measurable influencer ROI for venues. "Proof of Influence" dashboard gives promoters verified KPIs to negotiate better rates. Bridges digital influence → real-world commerce.
- **Requires:** New "Promoter" role with separate analytics dashboard. Cohort attribution engine. `Privacy: promoter dashboards show only aggregated/anonymized data — never individual user details.`

---

## 4. Venue Platform & Business Model Evolution

### 4.1 Open Venue Presence — Skins, Themes & Plugins `V2.0+/V3.0+`

**Theme Store:** Venues purchase/select pre-designed themes to customize their page, quest list, and menu appearance.

**Plugin Marketplace:** Open SDK/API for validated third-party or internal plugins:
- Table Booking & Reservation
- Karaoke Module (browse songs, submit requests, upvote/downvote queue)
- DJ Song Suggestion (patrons suggest songs, see what's next)
- Advanced Feedback (AI-powered categorization and actionable insights)
- Gamification Plugins (Spin the Wheel, Scratch & Win)

- **Why:** Deeper brand expression for venues. More engaging diner experiences. High-margin revenue stream (premium themes, marketplace cut). Developer ecosystem = network effect accelerator.
- **Requires:** Robust plugin architecture, developer onboarding/validation, marketplace with payments. Must maintain baseline usability and CheckIn brand consistency.

### 4.2 Predictive Cost Delivery-as-a-Service (DaaS) `V3.0+`

Replace commission-based delivery (25–30% on aggregators) with subscription-based logistics. Venues pre-pay monthly for delivery capacity priced per-km. Three pricing models considered:

| Model | Structure | Best For |
|-------|-----------|----------|
| **Tiered Radius** | Flat monthly fee per tier (e.g., ₹X for 200 orders within 3km) | Simplicity — easy for owners to budget |
| **Hybrid** | Lower subscription + capped 5–7% commission per order | Lower risk for onboarding hesitant venues |
| **Dynamic Boost** | Base plan + pay-per-boost for temporary radius expansion during off-peak | Flexibility — venues control spend precisely |

- **Why:** Predictable costs for venues. Delivery + loyalty in one platform. Stable B2B recurring revenue. Completes the 360° loop (discover → visit → engage → re-order from home).
- **Requires:** 3PL integration (Dunzo, Shadowfax, etc.), pricing/billing engine, POS/KDS integration. `Ambitious — major strategic pivot. Places CheckIn adjacent to delivery giants. Key differentiator = predictable cost + loyalty integration.`

---

## Cross-Reference

These ideas feed into the phased roadmap in `product/roadmap.md` and the prioritized feature inventory in `product/features.md`. Many are already reflected there in condensed form.

**Prioritization principles** (from features.md):
1. Retention first, acquisition second, ecosystem third
2. Group features over individual features
3. Venue ROI before platform revenue
4. Low POS-dependency first

---

Sources: Checkin: Future Features & Concepts Idea Dump (June 5, 2025)
