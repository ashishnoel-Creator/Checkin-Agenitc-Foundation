# PRD — Webapp (Venue Check-In Experience)

> **Product:** CheckIn Browser Webapp (Phase 1B MVP)
> **Last updated:** February 16, 2026
> **Owner:** Ashish
> **Platform:** Mobile browser (PWA-ready, no app install required)
> **Entry point:** QR code at venue (table tent, receipt, bar counter, entrance)

---

## Overview

The Webapp is CheckIn's primary entry point — the first thing a diner interacts with. It runs entirely in the mobile browser (no app install required). The diner scans a QR code at a venue, checks in, sees quests, earns credits, redeems rewards, and splits bills — all without downloading anything.

The browser experience is deliberately designed to be the hook. Premium features (leaderboards, collectibles, personal AI agent, discovery feed) are visible but gated behind app download. This creates a natural conversion funnel: scan → check-in → engage → download app.

**Core Design Principles**
- Zero friction to first value — check-in in under 15 seconds
- Mobile-first, thumb-friendly — designed for one-handed use at a table
- Venue-branded — feels like the venue's system, "Powered by CheckIn"
- Gated progression — browser is free, app unlocks the full experience
- Group-native — bill splitting, group quests, table pot are core, not afterthoughts

---

# Screen-by-Screen Flows

## Screen 1: QR Scan → Venue Landing Page

*Entry point — first impression of CheckIn*

**Trigger**

Diner scans a QR code placed at the venue (table tent, bar counter, entrance, receipt). QR encodes a URL: `checkin.app/{venue-slug}?table={table-id}`

**What the diner sees**
- Venue hero image / banner (full-width, venue-branded)
- Venue name, logo, and tagline
- "Powered by CheckIn" badge (subtle, bottom corner)
- Live pulse indicator: "{X} people checked in right now" (social proof)
- Primary CTA button: "Check In →" (large, prominent, venue accent color)
- Secondary info: venue address, hours, cuisine tags
- Preview peek: "3 active quests • Earn up to 500 credits today" (teaser below CTA)

**States**
- **New visitor:** Shows "Check In →" button. No account yet.
- **Returning visitor (not checked in):** Shows "Welcome back, {name}! Check In →" with their avatar. Auto-detected via browser cookie/local storage.
- **Already checked in:** Redirects straight to Screen 4 (Quest Dashboard). Shows "You're checked in ✓"

**Edge Cases**
- QR scanned outside venue (GPS mismatch): Show venue page but disable check-in. Message: "Visit {venue} to check in and start earning!"
- Venue is closed: Show "Opens at {time}" with option to follow venue for updates
- Invalid/expired QR: Redirect to CheckIn homepage with venue search

→ *Diner taps "Check In" → Screen 2*

---

## Screen 2: Authentication (Sign Up / Sign In)

*Minimal friction — phone OTP only for MVP*

**What the diner sees**
- Phone number input field (auto-detected country code +91)
- "Continue" button
- Fine print: "By continuing, you follow {venue name} and agree to CheckIn Terms"
- Alternative: "Sign in with Google" button (secondary option)

**Flow: Phone OTP**
- Step 1: Diner enters phone number → taps "Continue"
- Step 2: OTP input screen (4-digit code, auto-read from SMS)
- Step 3: If new user → Screen 2B (Name Entry). If returning user → Screen 3 (Check-In Confirmation)

**Screen 2B: Name Entry (New Users Only)**
- First name input (required)
- Optional: profile photo upload (can skip)
- "Start Exploring →" button
- This screen appears only once, ever. Returning users skip it.

**What happens in the background**
- Supabase Auth creates/verifies user session
- GPS validation confirms diner is physically at the venue
- Auto-follow: diner profile linked to venue in Community Graph
- Welcome Credits: new users get a small VC bonus (configurable per venue, e.g., 50 VCs)

**Edge Cases**
- OTP not received: "Resend" button appears after 30 seconds. Fallback: "Try Google Sign-In instead"
- GPS permission denied: Allow check-in but flag it. Venue staff can manually verify. Message: "For the best experience, enable location"
- Phone number already linked to account: Auto-detect, skip name entry, welcome back

→ *Auth complete → Screen 3*

---

## Screen 3: Check-In Confirmation

*The "moment of commitment" — auto-follow happens here*

**What the diner sees (celebration micro-interaction, 2-3 seconds)**
- Animated check-in confirmation: "✓ You're checked in at {Venue Name}!"
- Confetti / particle animation (brief, delightful)
- Welcome credits awarded: "+50 VCs — Welcome Aboard!" (with coin animation)
- Auto-follow confirmation: "You now follow {Venue}. You'll see their updates in your feed."
- Quick stats: "You're visitor #{X} today" (social proof)

**Auto-transitions after 2-3 seconds to Screen 4**

This screen is intentionally brief — it's a celebration moment, not a decision point. The diner shouldn't have to tap anything. The animation plays, credits are awarded, and the screen transitions to the Quest Dashboard.

**What happens in the background**
- Check-in event recorded in database (timestamp, venue, table, GPS)
- Auto-follow: venue appears in diner's followed venues list
- Welcome Quest triggered (if first visit)
- Venue dashboard updates in real-time: new check-in notification
- If table ID was in QR: diner is associated with that table for bill/group features

→ *Auto-transition → Screen 4*

---

## Screen 4: Quest Dashboard (Main Hub)

*The primary screen during a visit — quests, credits, actions*

### 4A: Header Bar
- Venue name + logo (top-left)
- Diner avatar + name (top-right, tappable → profile)
- Credit balance pill: "🪙 {X} VCs" (always visible, tappable → Screen 7)

### 4B: Active Quests Section

Horizontally scrollable quest cards. Each card shows:
- Quest name and icon (e.g., "🔥 Loyalty Pays", "🍕 Taste Adventure")
- Progress bar: "2/3 visits completed"
- Reward preview: "Earn 200 VCs"
- Time remaining (if time-limited): "Ends in 2h 15m"
- Tap on card → Screen 5 (Quest Detail)

**Quest Types in MVP**

| Quest Type | Name | Mechanic | Example |
|-----------|------|----------|---------|
| First Visit | Welcome Aboard | Auto-complete on check-in | Check in → 50 VCs |
| Bill Value | Raise the Stakes | Min spend threshold | Spend ₹2,000 → 200 VCs |
| Visit Frequency | Loyalty Pays | X visits in Y days | 3 Fridays in a row → free cocktail |
| Time-Based | Beat the Clock | Check in during window | Happy hour check-in → 100 VCs |
| Menu Exploration | Taste Adventure | Try X different items | Try 5 dishes → secret menu item |
| Social / Referral | Squad Mode | Bring X friends who check in | Bring 2 friends → 300 VCs each |
| Group Quest | Table Challenge | Group completes together | Table spends ₹5K → pool gets 500 VCs |

### 4C: Table Pot (Group Feature)

If multiple people are checked in at the same table:
- Shared "Table Pot" display: "🪙 Table Pot: 350 VCs (3 people)"
- Credits earned during this session pool into the pot
- Pot splits equally at bill time (or can be used toward bill)
- Animated coin-drop when someone earns credits ("Rahul earned +100 VCs for the table!")

### 4D: Quick Actions Bar (Bottom)
- **📋 Menu:** View menu with recommendations → Screen 6
- **🪙 Rewards:** See and redeem rewards → Screen 7
- **💰 Bill:** View/split bill → Screen 8
- **🏆 Leaderboard:** Venue leaderboard (visible but gated → prompts app download)

**Gated Features (Visible but Locked)**

These are visible on the quest dashboard as greyed-out / locked cards with an app download prompt:
- 🔒 Leaderboard position: "Download the app to see your rank"
- 🔒 Collections & Badges: "Unlock collectibles in the app"
- 🔒 Venue Feed: "Get updates from {venue} in the app"
- 🔒 Discovery: "Find new venues with Global Credits in the app"

→ *Tap quest card → Screen 5 | Tap Menu → Screen 6 | Tap Rewards → Screen 7 | Tap Bill → Screen 8*

---

## Screen 5: Quest Detail

*Expanded view of a single quest with progress and rules*

**What the diner sees**
- Quest name, icon, and description
- Full progress tracker: visual steps (e.g., 3 circles, 2 filled)
- Reward details: "Complete this quest to earn 200 VCs + ⭐ 50 Stars"
- Quest rules / fine print: "Visit must be at least 30 minutes. Bill must be ₹500+."
- Time remaining (if applicable)
- Quest history: "You completed this quest 2 times before"

**Validation Methods (per quest type)**

| Quest Type | How It's Validated | Fallback |
|-----------|-------------------|----------|
| Welcome Aboard | Auto-complete on check-in | N/A |
| Raise the Stakes | POS bill data (if integrated) OR staff confirms bill total | Diner enters bill total, staff approves via dashboard |
| Loyalty Pays | System tracks check-in history automatically | N/A |
| Beat the Clock | Check-in timestamp within time window | N/A |
| Taste Adventure | POS order data (if integrated) OR diner self-reports + staff confirms | Photo upload of dishes (future) |
| Squad Mode | Friends' check-in detected at same venue/table | Referral code entered by friend at check-in |
| Group Quest | Combined table bill total from POS or manual entry | Staff confirms via dashboard |

**Quest Completion State**
- Animation: quest card turns gold, confetti, credit coins fly to balance
- "+{X} VCs earned!" notification
- If Stars earned: "+{X} Stars — you're now #{rank} on the leaderboard!" (with app download prompt to see full board)
- Next quest suggestion: "Up next: Taste Adventure — try 5 new dishes for 300 VCs"

→ *Back → Screen 4*

---

## Screen 6: Menu & Recommendations

*Browse menu, see AI recommendations, track quest-relevant items*

**What the diner sees**
- Full venue menu organized by category (Starters, Mains, Drinks, Desserts)
- Each item: name, price, photo (if available), dietary tags (V, VG, GF)
- **✨ Quest Highlight:** Items that count toward active quests are badged. E.g., if "Taste Adventure" quest is active, untried dishes show a "🌟 Try this for your quest!" badge.
- **🤖 AI Recommendation (Phase 2):** "Based on your taste profile: try the Truffle Mushroom Risotto" — greyed out in MVP, shows "Unlock personalized picks in the app"

**Ordering (MVP Scope)**

In MVP, the menu is browse-only — ordering happens through the venue's existing process (waiter, POS, separate QR ordering system). CheckIn's menu is for discovery and quest tracking.

Future (Phase 2+): In-app ordering with cart, table-side submission to POS/KDS. This requires deep POS integration and is deferred.

**Edge Cases**
- Menu not uploaded by venue: Show "Menu coming soon. Ask your server!" with venue contact
- Item out of stock (if POS-integrated): Grey out with "Sold out" badge

→ *Back → Screen 4*

---

## Screen 7: Rewards & Wallet

*VC balance, available rewards, redemption flow*

### 7A: Wallet Summary
- VC balance: "🪙 1,250 Venue Credits at {Venue Name}"
- Stars balance: "⭐ 340 Stars — Rank #12" (with "See leaderboard in app" link)
- Expiry warning (if applicable): "150 VCs expire in 14 days — use them!"
- Transaction history link: "View history" → list of earned/redeemed credits

### 7B: Available Rewards

Grid of reward cards, each showing:
- Reward name: "Free Espresso", "10% Off Next Visit", "Secret Menu Access"
- Cost in VCs: "🪙 500 VCs"
- Availability: "Available now" or "Need 200 more VCs"
- Tappable: if affordable → Redemption Confirmation (Screen 7C)

### 7C: Redemption Confirmation
- Modal/bottom sheet: "Redeem {Reward} for {X} VCs?"
- New balance preview: "Balance after: {remaining} VCs"
- "Confirm Redemption" button
- On confirm: QR code or alphanumeric code generated for staff to verify
- Code valid for: 15 minutes (configurable per venue)
- Staff scans/enters code on venue dashboard → reward fulfilled

**Edge Cases**
- Insufficient VCs: Card shows "Need {X} more VCs" with suggestion to complete a quest
- Reward sold out (limited quantity): "Sold out — check back tomorrow"
- Redemption code expired: "Code expired. Tap to generate a new one" (VCs refunded)

→ *Back → Screen 4*

---

## Screen 8: Bill & Payment

*Bill entry, table pot usage, credit redemption, bill splitting*

### 8A: Bill Entry

The bill amount is entered into CheckIn so credits can be applied and quests validated.

- Option 1 (POS-integrated): Bill auto-populated from POS system. Diner sees itemized bill.
- Option 2 (Manual, MVP default): Payer enters total bill amount manually. "Your bill: ₹____"
- Staff verification: venue dashboard shows pending bill for staff to confirm amount

### 8B: Apply Credits
- Table Pot display: "Table Pot: 350 VCs available"
- Slider or input: "Use VCs toward this bill: {amount}"
- Real-time calculation: "Bill: ₹3,000 − ₹200 (VCs) = ₹2,800 to pay"
- VC coverage cap: venue sets max % of bill payable via VCs (e.g., 30%)
- "Apply" button confirms credit usage

### 8C: Bill Split

If multiple people are checked in at the table:
- **Equal split:** "Split equally between {X} people" → shows per-person amount
- **Custom split:** Each person enters their share. Running total shows remaining.
- **Per-person VC usage:** Each person can choose to apply their personal VCs to their share
- Table Pot portion distributed: pot split equally before individual VCs applied

### 8D: Payment Confirmation

In MVP, actual payment happens outside CheckIn (cash, UPI, card via venue's payment system). CheckIn tracks the credit adjustments.

- Summary screen: "Bill settled! ₹2,800 paid. 200 VCs used. Remaining balance: 1,050 VCs"
- Quest validation: if bill meets quest thresholds, auto-complete relevant quests
- "Raise the Stakes" quest check: "You spent ₹3,000 — quest complete! +200 VCs earned"
- Net credit change displayed: "Used 200 VCs, earned 200 VCs = net zero today 🎉"

**Edge Cases**
- Bill amount disputed: "Contact venue staff to adjust" link
- Table Pot leftover after bill: remaining pot credits split equally to each diner's personal wallet
- Solo diner (no split needed): Skip split screen, go straight to apply credits → confirmation
- POS integration failure: fall back to manual bill entry

→ *Bill settled → Screen 9*

---

## Screen 9: Post-Visit Summary & App Download Prompt

*Session wrap-up, achievements, conversion to app*

**What the diner sees**
- Visit summary card: "Your visit to {Venue}"
- Credits earned this visit: "+450 VCs earned today"
- Quests completed: "2 quests completed — Raise the Stakes, Welcome Aboard"
- Current balance: "1,250 VCs at {Venue}"
- Streak tracker: "2-visit streak! Come back Friday for 3x bonus"

**App Download CTA (The Conversion Moment)**

This is the key conversion point. The diner has just had a great experience — credits earned, quests completed, rewards pending. Now show what they're missing:

- 🔓 "See your rank on the leaderboard — you're close to the top!"
- 🔓 "Unlock collectible badges from {Venue}"
- 🔓 "Get personalized restaurant recommendations"
- 🔓 "Discover 50+ venues where your Global Credits work"
- **Big CTA: "Download CheckIn App →"**
- Secondary: "Maybe later" (dismissible, no penalty)

**Post-Visit Notifications (via browser push, if permitted)**
- 24h later: "You have 1,250 VCs at {Venue} — check your rewards!"
- 7 days later: "Your streak expires tomorrow — visit {Venue} to keep it alive!"
- 30 days before VC expiry: "{X} VCs expiring soon at {Venue}"

**Edge Cases**
- Diner closes browser mid-visit: session data persists. On return, resume from last state.
- Diner doesn't settle bill via CheckIn: credits earned from quests still valid. Bill-dependent quests remain incomplete.
- Push notification permission denied: fall back to email (if provided) or in-app notifications when they open CheckIn next

---

## Technical Flow Summary

End-to-end data flow:

QR Scan → Browser loads venue page (Vercel Edge) → Auth via Supabase (phone OTP) → GPS validation confirms venue presence → Auto-follow: diner linked to venue in Community Graph → Active quests loaded (Supabase real-time) → Diner completes actions → Quest Engine validates completion (POS or manual) → Value Engine mints VCs to diner wallet → Venue Dashboard updates in real-time → Session ends → App download prompt

### Key Technical Decisions

| Decision | Choice | Why |
|----------|--------|-----|
| Platform | Mobile browser (PWA) | Zero friction. No app store. QR → instant access. |
| Auth | Phone OTP (Supabase Auth) | Universal in India. No Google/social dependency. |
| Real-time | Supabase Realtime | Table pot, leaderboard, quest progress sync instantly. |
| GPS | Browser Geolocation API | Anti-fraud. Graceful degradation if denied. |
| Offline | Service worker caching | Menu and quest data cached. Credits sync when online. |
| POS fallback | Manual entry + staff confirm | Works without any POS integration for MVP. |

---

## Success Metrics

| Metric | Target | Measurement |
|--------|--------|-------------|
| QR → Landing Page | >95% | Page loads successfully after scan |
| Landing → Check-in | >50% | Visitors who complete auth + check-in |
| Auth completion time | <15 seconds | Phone entry → OTP → checked in |
| Quest engagement | >60% | Checked-in users who view at least 1 quest |
| Quest completion | >40% | Users who complete at least 1 quest per visit |
| VC Redemption | >60% | Earned VCs that get redeemed within 60 days |
| Bill feature usage | >30% | Check-ins that use bill/credit features |
| App download conversion | >20% | Browser users who download the app |
| Return visit (30 day) | >35% | Users who check in again within 30 days |
| Session duration | >25 min | Average time from check-in to session end |

---

## Screen Map (Quick Reference)

| Screen | Name | Purpose | Key Action |
|--------|------|---------|------------|
| 1 | Venue Landing | First impression, social proof | Tap "Check In" |
| 2 | Authentication | Phone OTP sign-up/in | Enter phone, verify OTP |
| 2B | Name Entry | New user only — set name | Enter first name |
| 3 | Check-In Confirm | Celebration + auto-follow | Auto-transition (2-3s) |
| 4 | Quest Dashboard | Main hub during visit | Browse quests, earn credits |
| 5 | Quest Detail | Expanded quest view | Track progress, complete |
| 6 | Menu | Browse menu, quest highlights | Find quest-relevant items |
| 7 | Rewards & Wallet | VC balance, redeem rewards | Redeem VCs for rewards |
| 8 | Bill & Payment | Credit usage, bill split | Apply credits, split bill |
| 9 | Post-Visit | Summary + app download | Download app or dismiss |

---

*Sources: product/features.md (Phase 1B MVP features), product/overview.md (core loop), product/architecture.md (data flow + tech stack), product/credit-system.md (VC mechanics).*
