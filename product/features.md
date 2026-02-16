# Feature Inventory — Prioritized

> Last synthesized: Feb 16, 2026

## Phase 1A: Prototype Features (Full Vision Demo)

The prototype demonstrates the complete system end-to-end. Not deployed to real venues — it's the vision made tangible for investors and venue partners.

**Diner Side (Browser):** QR check-in with auto-follow, quest system with progress tracking, validation systems, table-side ordering with recommendations, VC earning/redemption, gated rewards (leaderboards/collectibles locked behind app download).

**Diner Side (App):** Discovery flow, user profile with taste data, venue feed, reward discovery, coin tracker, leaderboards, collections, premium memberships, streaks, personal AI agent.

**Venue Side:** WhatsApp AI agent for business updates/quest suggestions, analytics dashboard, campaign builder, feedback loop, plugin ecosystem showcase.

**Ecosystem:** Money flow diagrams, payment integration demos.

## Phase 1B: MVP Features (First Deployment)

The focused slice deployed to real venues.

### Core Check-In & Identity
- **QR Code Check-In:** Scan venue QR → browser-based check-in (no app required initially). Auto-follows the venue on check-in — diner joins venue's community, reachable via notifications and feed. Diner can unfollow anytime.
- **Frictionless Signup:** Mobile number + OTP only. Minimal friction to first check-in.
- **User Wallet:** Transparent credit/star balances per venue with expiry rules.
- **Gated App Download:** Browser is the hook — leaderboards, collectibles, premium rewards visible but locked behind app download. App is the commitment.

### Quest System
- **Welcome Aboard:** First check-in bonus credits
- **Raise the Stakes:** Minimum bill value quests ("Spend ₹2,000 → earn 200 credits")
- **Loyalty Pays:** Visit frequency rewards ("Visit 3 Fridays in a row → free cocktail")
- **Beat the Clock:** Time-based challenges (happy hour specials)
- **Taste Adventure:** Menu item-based quests ("Try 5 dishes → secret menu item")
- **Group Quests:** Squad mode — pool credits, compete as a table, redeem together
- **Dynamic Scaling:** Quests automatically adjust rewards based on group size

### Rewards & Credits
- **Venue Credits (₹):** 1 Credit = ₹1, venue-specific, instant redemption
- **Stars:** Status points for leaderboard ranking (non-spendable)
- **Current Table Pot:** All credits earned during a session pool in shared temporary pot — fosters teamwork

### Bill & Payment
- **Bill Payment Flow:** Payer enters total → inputs per-person contributions → option to use Table Pot portion → staff verifies against POS → credits deducted → remaining pot split equally
- **Bill Splitting:** Integrated equal or manual custom splits — inherently viral in groups

### Community
- **Leaderboards:** Weekly/monthly ranking by Stars within each venue
- **Venue Announcement Feed:** Direct venue-to-customer communication (no WhatsApp spam)
- **Friend Activity Visibility:** Opt-in — see where friends are regulars
- **Birthday Rewards:** Automated birthday recognition

### Venue Dashboard
- **Quick Onboarding:** RM-assisted setup
- **Quest Creation:** Template-based — all MVP quest types available
- **Credit/Redemption Rules:** Venue controls caps, percentages, expiry
- **Real-Time Activity:** Live check-in monitoring
- **Analytics Dashboard:** Total check-ins, credits utilized, new members, quest effectiveness, ROI metrics
- **Customer Directory:** Basic check-in history and balances per customer
- **Announcement Reach:** Metrics on communication effectiveness

## V1.5 Features (Near-Term Post-MVP)

### Enhanced Gamification
- **Collectable Wall / Annual Event Passport:** Venues define signature events → users earn digital stickers/badges → displayed on personal "Collector Board." Drives targeted event attendance with "gotta catch 'em all" mechanics.
- **Dual Wallet System:** Split credit wallet into "Immediate" (50% redeemable on current bill) and "Later/Personal Vault" (fully redeemable on future visits — transfers after 24hr). Creates return-visit incentive.
- **Diminishing Value for Inactive Credits:** Credits gradually decrease with inactivity (e.g., 10 credits/week after 1+ month inactive) rather than binary expire. Continuous psychological nudge via loss aversion.
- **Venue-Specific Daily Streaks:** Consecutive daily check-in multipliers (Day 2: 1.1x, Day 3: 1.2x, capping at 2x). Venues can toggle on/off. Especially powerful for coffee shops and high-frequency venues.

### Platform Utility
- **Wi-Fi Access on Check-In:** Auto-authenticate venue Wi-Fi on successful check-in. Eliminates password/captive portal friction. Also serves as location verification. [NEEDS REVIEW: Requires hardware partnerships — Cisco Meraki, Aruba]
- **Dynamic In-App Event Banner:** Special scrolling banner when venue has active event/live promoter ("LIVE NOW: DJ Gemini on the decks!"). Creates dynamic "live" feeling.
- **Live Visual Editor ("Brand Studio"):** WYSIWYG in venue dashboard — real-time preview of venue page customization (profile pic, banner, colors, icons). Reduces support overhead.

## V2.0+ Features (Longer-Term)

### Advanced Engagement
- **Integrated Mobile Ordering:** Digital menu → in-app cart → order submission → real-time status tracking ("Preparing → Cooking → Delivered"). Variant: QR Code Injection where user builds order, generates QR, server scans into POS. [NEEDS REVIEW: Requires deep POS/KDS integration — major technical undertaking]
- **AI-Powered Group Outing Planner:** Create group → AI analyzes collective preferences, credit balances, active offers → suggests optimal venue. Solves "where should we go?" friction.
- **Promoter Engine ("Proof of Influence"):** Dedicated dashboard for venues to manage performance-based influencer/DJ collaborations. Tracks entire customer cohort attributed to each promoter (footfall, spend, retention). Gives promoters verified "Proof of Influence" metrics. [NEEDS REVIEW: Privacy — only aggregated data, never individual details]

### Community & Social
- **Enhanced Public User Profiles:** Optional showcase of F&B identity — favorite venues, cuisines, check-in badges, leaderboard positions. Granular privacy controls (public/private/friends-only).
- **User-Driven Meetups ("Open Tables"):** Users host themed events at partner venues ("Book Club Meetup," "Board Game Night"). Set entry contribution, publicize to community. Drives pre-organized traffic.
- **User-Generated Content:** Venue-scoped, moderated reviews and content
- **Sub-Groups/Clubs:** Community segmentation within venues
- **Direct Messaging:** Venue-to-patron and patron-to-patron within community

### Platform Evolution
- **Open Venue Presence (Skins/Themes):** Theme Store + Plugin Architecture Marketplace with validated third-party plugins
- **Plugin Examples:** Table Booking, Karaoke Module (browse/request/upvote songs), DJ Song Suggestions, Advanced Feedback (AI-powered), Spin the Wheel, Scratch & Win
- **Global Credits Wallet:** Cross-venue credits with full ad platform for brand-funded quests
- **In-App Ordering with POS Integration:** Full kitchen display system integration
- **Predictive Cost Delivery-as-a-Service:** Replace commission-based delivery with subscription-based logistics (tiered radius model or hybrid subscription + capped 5–7% commission vs. aggregators' 25–30%)

## V3.0+ Features (Year 2–4)

- Full event management and ticketing
- CheckIn POS solutions (proprietary)
- Integrated ratings/reviews system
- AI-powered discovery engine
- Expanded plugin marketplace (open to 3rd-party developers)
- Advanced CRM with AI segmentation

## Endgame (Year 4+)

- Global expansion with CKIN governance token
- Integrated delivery logistics
- Full proprietary POS
- Advanced AI (predictive insights, automated quest optimization)
- Mature open marketplace
- Vertical expansion: Retail, Wellness, Live Events
- Single indispensable app for all F&B experiences

## Feature Prioritization Principles

1. **Retention first, acquisition second, ecosystem third** — this is the core roadmap philosophy
2. **Group features over individual features** — social mechanics drive organic virality
3. **Venue ROI before platform revenue** — prove value for venues before extracting value from network
4. **Low POS-dependency first** — MVP features should work without deep POS integration

---

Sources: Checkin: Future Features & Concepts Idea Dump, Checkin Whitepaper v1.1, Checkin: Investor Pitch Deck (Full Script & Content), Checking V2-Working Doc
