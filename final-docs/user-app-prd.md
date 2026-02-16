# PRD — User Application (Native App)

> **Product:** CheckIn Native App (iOS + Android)
> **Last updated:** February 16, 2026
> **Owner:** Ashish
> **Phase:** Phase 1A (Prototype) + Phase 2 (Post-Seed deployment)
> **Entry points:** App Store download, gated prompt from browser webapp, referral links, organic search

---

## Overview

The CheckIn app is where the full platform experience lives. While the browser webapp handles the in-venue check-in (scan → quest → earn), the app is the persistent relationship layer between visits. It's where diners discover new venues, manage their credits across the platform, follow their favourite spots, track streaks, and interact with their personal AI agent.

The app unlocks everything the browser gates: leaderboards, collectible badges, venue feed, Global Credits economy, cross-venue discovery, and the personal AI concierge. The conversion from browser to app is the key growth metric.

**Core Design Principles**
- The app is the relationship, the browser is the transaction
- Feed-first home screen — always something new from followed venues
- Credits are the connective tissue — VC/GC balances visible everywhere
- Discovery through rewards — GCs incentivize trying new places
- Personal AI agent as the primary navigation aid — "What should I eat tonight?"
- Social without being a social network — friend activity, group quests, leaderboards

---

## Relationship to Browser Webapp

| Aspect | Browser Webapp | Native App |
|--------|---------------|------------|
| When | During a venue visit | Between visits + during visits |
| Entry | QR scan at venue | App icon on home screen |
| Auth | Phone OTP (session-based) | Persistent login (biometric) |
| Check-in | ✓ Full flow | ✓ Full flow + NFC/Bluetooth (future) |
| Quests | ✓ Active quests at current venue | ✓ All quests across all venues |
| Credits | ✓ VCs for current venue | ✓ Full wallet: all VCs + GCs |
| Discovery | ✘ Gated | ✓ Browse venues, map, recommendations |
| Feed | ✘ Gated | ✓ Updates from all followed venues |
| Leaderboard | ✘ Gated (preview only) | ✓ Venue + platform rankings |
| Collections | ✘ Gated | ✓ Badges, achievements, collectibles |
| AI Agent | ✘ Not available | ✓ Personal concierge |
| GC Economy | ✘ Not available | ✓ Earn, swap, discover via GCs |

---

# Screen-by-Screen Flows

## Screen 1: Onboarding & First Launch

*First-time app open — account setup or login*

**1A: Welcome Carousel (3 screens, swipeable)**
- Screen A: "Own your dining experience" — illustration of check-in + quests
- Screen B: "Earn rewards everywhere you go" — illustration of VCs + GCs flowing
- Screen C: "Your personal food concierge" — illustration of AI agent chat
- CTA: "Get Started →"

**1B: Authentication**
- If user already checked in via browser: "Welcome back, {name}! We found your account." → auto-login via phone match
- If new: Phone OTP flow (identical to browser Screen 2)
- After auth: quick preference onboarding (Screen 1C)

**1C: Taste Profile Setup (One-Time, Skippable)**
- Cuisine preferences: tap to select from grid (Indian, Italian, Japanese, Chinese, Continental, Cafe, Bar, etc.)
- Dietary restrictions: Veg / Non-Veg / Vegan / Gluten-Free (multi-select)
- Spice tolerance: slider (Mild → Medium → Fire)
- Budget preference: ₹ / ₹₹ / ₹₹₹ / ₹₹₹₹
- "Skip for now" option — AI agent refines preferences over time from actual behavior

**1D: Location Permission**
- Prompt: "Allow CheckIn to use your location to find venues near you"
- If denied: app works but discovery defaults to city-level, not proximity

→ *Onboarding complete → Screen 2 (Home Feed)*

---

## Screen 2: Home Feed

*The default screen — what users see every time they open the app*

### 2A: Top Bar
- CheckIn logo (top-left)
- Search icon (top-right) → Screen 6 (Search)
- Notification bell with unread count → Screen 10 (Notifications)
- Profile avatar (top-right) → Screen 5 (Profile)

### 2B: Credit Summary Strip
- Horizontal card always visible below top bar:
- Left: "🪙 GC: {balance}" (tappable → Screen 4 Wallet)
- Right: "VCs at {X} venues" (tappable → Screen 4 Wallet)
- Subtle animation when credits change (coin pulse)

### 2C: Active Quests Banner (if any)
- Horizontal scroll of active quest cards from followed venues
- Shows: venue logo, quest name, progress, time remaining
- "3 active quests — complete them to earn 800 VCs" (motivational)
- Tap → deep-links to quest detail for that venue

### 2D: Feed (Main Content)

Chronological + algorithmically weighted feed of updates from followed venues:

- **New Quest:** "{Venue} just launched a new quest: Taste Adventure — try 5 dishes for 300 VCs"
- **Event:** "{Venue} is hosting Live Jazz Night this Friday — bonus 2x credits"
- **Special:** "{Venue} has a limited-time swap bonus: GC→VC at 50% extra today!"
- **Streak Reminder:** "Your streak at {Venue} expires tomorrow — visit to keep it alive!"
- **Friend Activity:** "Rahul just completed Loyalty Pays at Toit — he's now #3 on their leaderboard" (opt-in)
- **New Venue Nearby:** "Third Wave Coffee just joined CheckIn — 50 GC welcome bonus for first check-in!"

**Feed Empty State (New User)**
- "No updates yet! Follow some venues to see what's happening."
- CTA: "Discover venues near you →" → Screen 3
- Suggested venues based on location + taste preferences

### 2E: Bottom Navigation Bar

| Tab | Icon | Screen | Description |
|-----|------|--------|-------------|
| Home | 🏠 | Screen 2 | Feed + active quests |
| Discover | 🔍 | Screen 3 | Find new venues, map, GC opportunities |
| Wallet | 🪙 | Screen 4 | All credits, transaction history, rewards |
| Profile | 👤 | Screen 5 | Taste profile, collections, settings |
| AI Agent | ✨ | Screen 9 | Personal concierge chat |

→ *Bottom nav controls all primary navigation*

---

## Screen 3: Discover

*Find new venues, browse by category, GC-powered discovery*

### 3A: Search Bar + Filters
- Search: "Search venues, cuisines, areas..."
- Filter chips: Cuisine type, Area, Price range, "Has active quests", "GC welcome bonus"
- Sort: Nearest / Trending / New on CheckIn / Best rewards

### 3B: Map View (Toggle)
- Interactive map showing nearby CheckIn venues as pins
- Pin color indicates: 🟢 active quest available, 🔵 no active quest, ✨ GC welcome bonus
- Tap pin → venue preview card (name, photo, cuisine, distance, active quests count)
- Tap card → Screen 3C (Venue Profile)

### 3C: Venue List View (Default)

Scrollable list of venue cards, each showing:
- Venue photo + name + cuisine tags
- Distance from current location
- Active quests count: "3 active quests"
- Top reward preview: "Earn up to 500 VCs"
- GC welcome bonus (if available): "🌟 50 GC for first check-in"
- Friend presence: "2 friends follow this venue" (if applicable)
- Tap → Screen 3D (Venue Detail Page)

### 3D: Venue Detail Page (Pre-Visit)

Full venue page accessible from Discover. Same branded experience as the browser, but richer since they're in the app:

- Hero image + venue branding
- About: cuisine, hours, address, phone, Instagram link
- Active quests: full list with progress (if already following)
- Rewards available: grid of what you can earn
- Leaderboard preview: top 5 + your rank (if you're on it)
- Community stats: "{X} followers • {Y} check-ins this week"
- "Check In" button (if at venue, detected via GPS)
- "Follow" button (if not at venue — follow for feed updates without checking in)
- GC→VC Swap Offers: if venue has an active swap bonus, prominently displayed
- Reviews/photos (future: user-generated content)

**GC-Powered Discovery**

The Discover tab is where Global Credits drive cross-venue exploration:
- "Earn 50 GC for your first check-in at any of these new venues" — discovery quests
- "Visit 3 new cafes this month → 200 GC" — exploration quest
- "Swap your GCs for VCs at {Venue} — 50% bonus today!" — venue-specific offers
- GC balance always visible, reminding users they have "money to spend" at new places

→ *Tap venue → Screen 3D Venue Detail | Tap "Check In" → Browser check-in flow*

---

## Screen 4: Wallet & Credits

*Complete financial picture — all VCs, GCs, history, rewards*

### 4A: Global Credits Section
- Big balance display: "🪙 {X} Global Credits"
- Equivalent value: "≈ ₹{X}" (1:1 peg, always shown)
- "How to earn more GCs" expandable section:
  - Visit a new venue: +50 GC
  - Refer a friend: +100 GC
  - Complete a Global Quest: varies
- "Swap GCs → VCs" button → shows venues with active swap bonuses

### 4B: Venue Credits Section

List of all venues where diner holds VCs:
- Each row: Venue logo + name, VC balance, expiry date
- Sorted by: balance (highest first) or recency (last visited first)
- Tap venue row → expanded view: rewards available at that venue, redemption options, transaction history
- Expiry warnings: ⚠️ "150 VCs at Toit expire in 14 days"
- Total VC value shown at top: "VCs across {X} venues: {total} VCs"

### 4C: Transaction History
- Chronological feed of all credit events:
- "Earned 200 VCs at Toit (Raise the Stakes quest)" — Feb 15
- "Redeemed 100 VCs at Toit (Free Espresso)" — Feb 14
- "Earned 50 GC (First check-in at Third Wave)" — Feb 12
- "Swapped 500 GC → 750 VCs at Arbor Brewing (50% bonus)" — Feb 10
- Filter by: venue, credit type (VC/GC), earned/spent, date range

### 4D: GC → VC Swap Flow

When diner taps 'Swap GCs' or a venue's swap offer:
- Step 1: Select venue to swap into
- Step 2: Enter GC amount to swap
- Step 3: Preview: "500 GC → 750 VCs at {Venue} (50% bonus!)"
- Step 4: Confirm swap
- Step 5: Celebration animation. VCs appear in venue wallet instantly.
- Warning: "VCs at {Venue} can't be converted back to GCs" (clear, no surprises)

**Edge Cases**
- No GCs: "Earn Global Credits by visiting new venues or referring friends" with CTA to Discover
- VC decay warning: "Your VCs at {Venue} will start decreasing in 15 days due to inactivity"
- Venue no longer on CheckIn: "This venue is no longer active. Your remaining VCs have been converted to GCs at 50% value." (safety net)

→ *Tap venue → Venue rewards | Tap swap → Swap flow*

---

## Screen 5: Profile & Collections

*Diner identity, achievements, taste profile, settings*

### 5A: Profile Header
- Profile photo, name, member since date
- Headline stats: "{X} check-ins • {Y} venues • {Z} quests completed"
- "Edit Profile" button

### 5B: Taste Profile Card
- Visual taste map: radar chart showing cuisine preferences (auto-generated from actual order data + initial setup)
- Top cuisines: "Indian • Italian • Japanese"
- Dietary: "Non-Veg • No restrictions"
- Spice: "Medium-High 🌶️"
- Budget: "₹₹₹"
- AI-refined: "Based on your last 23 check-ins and 47 orders"
- Editable: diner can override any AI-generated preference

### 5C: Collections & Badges

Grid of earned badges and collectibles:
- **Venue Badges:** "Toit Regular" (10+ visits), "Third Wave Explorer" (first visit), "Arbor VIP" (500+ VCs earned)
- **Quest Badges:** "Taste Adventurer" (try 20 unique dishes), "Social Butterfly" (refer 5 friends), "Streak Master" (7-day streak)
- **Platform Badges:** "Early Adopter", "10 Venues", "100 Quests", "GC Whale" (1000+ GC earned)
- Locked badges visible as silhouettes with "How to earn" explanation
- Shareable: tap badge → share to Instagram Stories / WhatsApp

### 5D: Leaderboard Summary
- Per-venue rankings: "Toit: #12 • Third Wave: #3 • Arbor: #45"
- Platform ranking: "#234 overall"
- Tap → full leaderboard (Screen 8)

### 5E: Visit History
- Timeline of all check-ins with dates, venues, credits earned
- Streak tracker: "Current streak: 3 weeks at Toit 🔥"
- Monthly summary: "Feb 2026: 8 check-ins, 4 venues, 1,200 VCs earned"

### 5F: Settings
- Notification preferences (per venue: on/off, frequency)
- Privacy: friend activity visibility (show/hide)
- Data export: download full profile data (GDPR-aligned)
- Delete account: clear all data, forfeit credits
- Linked accounts: phone, Google
- Help & support, Terms, Privacy Policy

→ *Edit profile → Edit flow | Tap badge → Share | Tap leaderboard → Screen 8*

---

## Screen 6: Search

*Universal search across venues, quests, friends*

**Search Functionality**
- Single search bar: "Search venues, quests, friends, cuisines..."
- **Venue results:** Name, cuisine, area matches
- **Quest results:** "Taste Adventure" shows all venues with that quest active
- **Area results:** "Koramangala" shows all venues in that area
- **Friend results:** Find friends on CheckIn by name

**Recent Searches + Trending**
- Recent: last 5 searches
- Trending: "Trending in Bangalore: Toit, Third Wave, Arbor Brewing"
- AI suggestion (Phase 2): "Based on your taste: try searching for 'Japanese Koramangala'"

→ *Tap result → Venue Detail / Quest Detail / Friend Profile*

---

## Screen 7: Venue Page (In-App, During Visit)

*When user checks in via the app instead of browser*

When a diner checks in via the app (either scanning QR or tapping 'Check In' on a venue page while at the venue), the in-app experience mirrors the browser webapp but with full app features unlocked:

- Same quest dashboard as browser Screen 4, but with full leaderboard access
- Real-time table pot with push notifications when group members earn credits
- Personal AI recommendations: "Based on your taste profile, try the Mushroom Risotto"
- Bill splitting with in-app payment tracking
- Badge/collectible unlocks animate directly in-app
- Post-visit: no app download prompt needed (they're already in the app)
- Post-visit: streak tracker, next-quest suggestion, GC earning opportunities

**Key Difference from Browser**

The app check-in is seamless — no OTP, no sign-up friction. The diner is already authenticated. GPS detects venue proximity, one tap to check in. Everything syncs in real-time with the browser sessions of other table members.

---

## Screen 8: Leaderboard

*Venue-level and platform-level competitive rankings*

### 8A: Venue Leaderboard
- Rankings within a single venue based on Stars earned
- Top 10 displayed with avatar, name, Stars count
- Your position highlighted (even if outside top 10)
- Time filter: This Week / This Month / All Time
- "How Stars work: Stars are earned alongside VCs but can't be spent. They're your status."

### 8B: Platform Leaderboard
- Rankings across all CheckIn venues
- Category filters: Overall / Most Venues Visited / Longest Streak / Most Quests
- City filter: "Bangalore" (future: cross-city)
- Friend filter: "Among your friends"

### 8C: Gamification Elements
- Tier system: Bronze → Silver → Gold → Platinum (based on cumulative Stars)
- Tier benefits: increased VC earning rates, exclusive quests, early access to new venues
- Weekly reset for "This Week" board creates recurring engagement
- Animated rank-up celebrations when user moves up tiers

---

## Screen 9: Personal AI Agent

*The AI concierge — the most differentiated feature*

**Interface**
- Chat-style interface (like iMessage/WhatsApp)
- Always accessible via bottom nav "✨" tab
- Agent has a personality: friendly, knowledgeable about food, slightly witty
- Agent avatar: CheckIn branded character

**What the Agent Can Do**

### Venue Recommendations
- User: "Where should I eat tonight?"
- Agent: "Based on your love of Italian and your ₹₹ budget, I'd suggest Toscano in Indiranagar. They have a Taste Adventure quest running — try 3 pastas, earn 300 VCs. Plus you have 200 GCs you could swap for 300 VCs there with today's bonus!"

### Quest Guidance
- User: "What quests can I complete today?"
- Agent: "You have 3 active quests: Loyalty Pays at Toit (1 more visit needed — your streak expires tomorrow!), Taste Adventure at Arbor (2 more dishes), and a Global Quest (visit any new venue for 50 GC)."

### Credit Optimization
- User: "I have 500 GCs, what should I do with them?"
- Agent: "Arbor Brewing has a 50% swap bonus today — your 500 GCs would become 750 VCs. That's enough for a free craft beer flight! Otherwise, Third Wave has a 30% bonus. Or keep them liquid if you're exploring this weekend."

### Group Planning
- User: "Planning dinner for 6 people, mix of veg and non-veg"
- Agent: "For a group of 6 with mixed preferences, I'd suggest Truffles (great for both, Group Quest running: table spends ₹6K → everyone gets 300 VCs), or Sahib Sindh Sultan (amazing veg options alongside non-veg). Want me to check if any of your friends follow these?"

### Morning Brief (Push Notification)
- Daily personalized update (opt-in): "Good morning, Ashish! Your Toit streak hits 4 weeks tomorrow. Third Wave has a new quest today. And you have 150 VCs expiring in 5 days at Arbor."

**Limitations (MVP / Phase 2)**
- Agent cannot make reservations (future integration)
- Agent cannot place orders
- Agent is text-only (no voice in MVP)
- Agent recommendations limited to CheckIn venues

**Data Sources for Agent**
- Diner's taste profile + visit history + credit balances
- Venue quest data + reward availability + swap bonuses
- Friend activity (opt-in)
- Location + time of day
- Previous agent conversations (context memory)

---

## Screen 10: Notifications

*All alerts and updates in one place*

**Notification Types**

| Type | Example | Priority |
|------|---------|----------|
| Quest progress | "1 more visit to complete Loyalty Pays at Toit!" | High |
| Streak warning | "Your streak expires tomorrow — visit Toit!" | High |
| Credit expiry | "150 VCs at Arbor expiring in 5 days" | High |
| New quest | "{Venue} launched a new quest: Beat the Clock" | Medium |
| Swap bonus | "{Venue} is offering 50% GC→VC bonus today" | Medium |
| Friend activity | "Rahul just hit #1 on Toit's leaderboard" | Low |
| New venue | "Third Wave Coffee just joined CheckIn near you" | Low |
| Event | "{Venue} is hosting Live Jazz Night this Friday" | Low |
| AI Morning Brief | "Your daily CheckIn summary" | Medium |
| Badge earned | "You just earned the Streak Master badge!" | Medium |

**Notification Preferences**
- Per-venue: on/off toggle for each followed venue
- Per-type: on/off for each notification category
- Quiet hours: no notifications between 11pm–7am (configurable)
- AI Morning Brief: on/off, configurable time

---

## Screen Map (Quick Reference)

| Screen | Name | Purpose | Bottom Nav Tab |
|--------|------|---------|----------------|
| 1 | Onboarding | First launch, auth, taste setup | — |
| 2 | Home Feed | Default screen, venue updates, active quests | 🏠 Home |
| 3 | Discover | Find venues, map, GC discovery | 🔍 Discover |
| 3D | Venue Detail | Pre-visit venue info + follow/check-in | 🔍 Discover |
| 4 | Wallet | GCs + all VCs + history + swap | 🪙 Wallet |
| 5 | Profile | Taste profile, collections, badges, settings | 👤 Profile |
| 6 | Search | Universal search | Via search icon |
| 7 | Venue (In-Visit) | Full quest experience during visit | Via check-in |
| 8 | Leaderboard | Venue + platform rankings | Via profile/venue |
| 9 | AI Agent | Personal concierge chat | ✨ AI |
| 10 | Notifications | All alerts | Via bell icon |

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| Browser → App conversion | >20% | Browser users who download app within 30 days |
| DAU / MAU | >30% | Daily active / monthly active ratio |
| Feed engagement | >50% | Users who interact with at least 1 feed item per session |
| Discovery conversion | >15% | Discover tab users who check in at a new venue within 7 days |
| GC → VC swap rate | >40% | GCs earned that get swapped to VCs within 60 days |
| AI Agent usage | >25% | Weekly active users who chat with agent at least once |
| Notification opt-in | >60% | Users who keep push notifications enabled |
| Collections engagement | >30% | Users who view their badges at least monthly |
| Multi-venue users | >25% | Users who check in at 2+ venues within 30 days |
| Retention D30 | >40% | Users who open app at least once 30 days after install |

---

*Sources: product/features.md (Phase 1A app features, V1.5, V2.0), product/overview.md (core loop, agentic vision), product/roadmap.md (Phase 2 deployment), product/credit-system.md (GC economy, swap mechanism), product/architecture.md (tech stack).*
