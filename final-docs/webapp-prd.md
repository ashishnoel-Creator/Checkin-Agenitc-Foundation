# PRD — Webapp (Venue Check-In Experience)

> **Product:** CheckIn Browser Webapp (Phase 1B MVP)
> **Last updated:** February 16, 2026
> **Owner:** Ashish
> **Platform:** Mobile browser (PWA-ready, no app install required)
> **Entry point:** QR code at venue (table tent, receipt, bar counter, entrance)

---

## 1. Introduction

The Webapp is CheckIn's primary entry point — the first thing a diner interacts with. It runs entirely in the mobile browser (no app install required). The diner scans a QR code at a venue, checks in, sees quests, earns credits, redeems rewards, and splits bills — all without downloading anything.

The browser experience is deliberately designed to be the hook. Premium features (leaderboards, collectibles, personal AI agent, discovery feed) are visible but gated behind app download. This creates a natural conversion funnel: scan → check-in → engage → download app.

### Core Design Principles
1.  **Zero Friction:** Check-in in under 15 seconds. No password creation, just OTP.
2.  **Thumb-Friendly:** Designed for one-handed use at a table. Critical actions (Check In, Redeem) in thumb zone.
3.  **Venue-Branded:** Feels like the venue's system, "Powered by CheckIn". Venue colors/logos take precedence.
4.  **Group-Native:** Bill splitting and Table Pot are core features, not afterthoughts.
5.  **Gated Progression:** Browser is free; App unlocks the full experience (discovery, global credits).

---

## 2. User Stories

| ID | As a... | I want to... | So that... |
|----|---------|--------------|------------|
| **US-01** | First-time Diner | Check in by scanning a QR code | I can start earning rewards without downloading an app. |
| **US-02** | Returning Diner | Be recognized instantly when I scan | I don't have to sign in again. |
| **US-03** | Diner | See what quests are active | I know what to order or do to earn credits. |
| **US-04** | Group of Diners | Pool our credits together | We can earn a larger reward as a team. |
| **US-05** | Payer | Use my credits to pay part of the bill | I get immediate value for my loyalty. |
| **US-06** | Payer | Split the remaining bill easily | We don't have to do awkward math at the table. |
| **US-07** | Venue Manager | Validate quests and redemptions securely | Customers can't game the system. |

---

## 3. User Flows

### Flow 1: First-Time Check-In (The "Hook")

**Goal:** New user scans QR, signs up via OTP, and lands on the dashboard.
**Trigger:** Scanning physical QR code at venue.

| Step | Screen ID | User Action | System Response |
|------|-----------|-------------|-----------------|
| 1 | **WA-01** (Landing) | Taps "Check In" button | Checks local storage. No session found → Navigates to **WA-02**. |
| 2 | **WA-02** (Auth) | Enters Mobile Number. Taps "Get OTP". | Validates number format. Sends OTP via SMS. Slides to **WA-02-B**. |
| 3 | **WA-02-B** (OTP) | Enters 4-digit OTP. | Verifies OTP. Checks DB for existing user. If new → Navigates to **WA-02-C**. |
| 4 | **WA-02-C** (Name) | Enters First Name. Taps "Start". | Creates user record. Links to venue. Awards Welcome Credits. Navigates to **WA-03**. |
| 5 | **WA-03** (Confirm) | Views animation (auto-advance). | Displays "You're checked in!" confetti. Auto-transitions to **WA-04** after 2s. |
| 6 | **WA-04** (Dash) | Lands on Dashboard. | Validates GPS. Loads active quests. |

### Flow 2: Returning User Check-In (The "Instant" Flow)

**Goal:** Recognized user checks in with one tap.

| Step | Screen ID | User Action | System Response |
|------|-----------|-------------|-----------------|
| 1 | **WA-01** (Landing) | Page loads. Cookie detected. | Shows "Welcome back, Ashish!" and "Check In" button. |
| 2 | **WA-01** (Landing) | Taps "Check In" button. | Verifies token validity. Checks GPS. Navigates to **WA-03**. |
| 3 | **WA-03** (Confirm) | Views animation (auto-advance). | Records check-in. Auto-transitions to **WA-04** after 2s. |

### Flow 3: Quest Engagement

**Goal:** User views a quest and completes it.

| Step | Screen ID | User Action | System Response |
|------|-----------|-------------|-----------------|
| 1 | **WA-04** (Dash) | Taps "Raise the Stakes" quest card. | Navigates to **WA-05**. |
| 2 | **WA-05** (Quest) | Reads rules. Taps "Check Status". | Checks current bill total (if POS integrated) or prompts manual entry. |
| 3 | **WA-05** (Quest) | (If manual) Enters bill amount. | Validates against threshold. If success → Awards credits. |
| 4 | **WA-05** (Quest) | Views Success Modal. | Updates VC balance. Updates progress bar. Confetti animation. |

### Flow 4: Bill Payment & Redemption

**Goal:** User pays bill using credits and splits remainder.

| Step | Screen ID | User Action | System Response |
|------|-----------|-------------|-----------------|
| 1 | **WA-04** (Dash) | Taps "Bill" icon in bottom nav. | Navigates to **WA-08**. |
| 2 | **WA-08** (Bill) | Enters total bill amount: ₹3000. | Calculates max redeemable VCs. Shows slider. |
| 3 | **WA-08** (Bill) | Slides to use 500 VCs (₹500 off). | Updates "You Pay" to ₹2500. |
| 4 | **WA-08** (Bill) | Taps "Pay & Split". | Navigates to **WA-08-B**. |
| 5 | **WA-08-B** (Split) | Selects "Split Equally (3 people)". | Shows ₹833.33 per person. Generates payment links/QR. |
| 6 | **WA-08-B** (Split) | Taps "Mark Settled". | Records transaction. Navigates to **WA-09**. |

---

## 4. Screen Specifications

### WA-01: Venue Landing
*First impression. Must feel like the venue's own app.*

**UI Elements:**
- **Hero Image:** Full-width venue photo (top 30% of screen).
- **Venue Logo:** Circular, overlapping hero image (left aligned).
- **Venue Name:** H1, Bold (e.g., "Third Wave Coffee").
- **Live Pulse:** "🟢 12 people checked in now".
- **Primary CTA:** Large button "Check In to Earn Rewards" (Venue Accent Color).
- **Teaser Cards:** "Active Quests: 3", "Your Potential Earnings: 500 VCs".
- **Footer:** "Powered by CheckIn" (subtle).

**Edge Cases:**
- **Venue Closed:** Show "Opens at 8:00 AM". CTA changes to "Remind Me".
- **GPS Mismatch:** Show warning "You seem to be far away" below CTA.

### WA-02: Authentication (OTP)
*Frictionless entry. Phone number only.*

**UI Elements:**
- **Input Field:** Mobile Number (+91 pre-filled). Auto-focus.
- **CTA:** "Get OTP" (inactive until 10 digits entered).
- **Social Login:** "Or continue with Google" (secondary, outlined button).
- **Terms:** "By continuing, you likely CheckIn Terms & Privacy Policy".

**Interaction:**
- Tapping "Get OTP" slides in **WA-02-B** (OTP Input).
- **WA-02-B:** 4-digit input. Auto-submit on 4th digit.
- **WA-02-C (New Users):** "What should we call you?" (First Name input).

### WA-03: Check-In Confirmation
*The "Dopamine Hit". Auto-transition.*

**UI Elements:**
- **Animation:** Large Checkmark (Lottie animation).
- **Text:** "You're checked in!"
- **Reward:** "+50 Welcome VCs" (Coin animation flying to top right).
- **Social Proof:** "Visitor #42 today".
- **Auto-Action:** No buttons. Transitions to WA-04 after 2.5 seconds.

### WA-04: Quest Dashboard (Home)
*The main hub. Scrollable, engaging.*

**UI Elements:**
- **Header:**
    - Left: Venue Logo + Name.
    - Right: User Avatar + Credit Balance (Pill style: "🪙 150").
- **Table Pot (If applicable):**
    - "Table Pot: 450 VCs (3 contributors)".
    - "Add to Pot" button.
- **Active Quests (Horizontal Scroll):**
    - Cards: Icon, Quest Name, Progress Bar (1/3), Reward Amount.
    - "See All" link.
- **Menu/Order Preview:**
    - "Popular nearby" or "Recommended for you" (locked in MVP).
- **Bottom Nav:**
    - Icons: Home (Active), Menu, Rewards, Bill.

**Menu Items (Bottom Nav):**
1.  **Home:** Current screen.
2.  **Menu:** Navigates to WA-06.
3.  **Rewards:** Navigates to WA-07 (Wallet).
4.  **Bill:** Navigates to WA-08.

### WA-05: Quest Detail
*Specifics of a challenge.*

**UI Elements:**
- **Header:** Back button, Quest Name.
- **Hero Icon:** Large graphical representation (e.g., Beer mug for Happy Hour).
- **Description:** "Order any 2 cocktails between 5-7 PM".
- **Progress:** "0/2 Ordered".
- **Reward:** "Earn 200 VCs".
- **CTA:** "Scan Receipt" or "Enter Bill Amount" (depending on integration).
- **Rules:** Accordion, collapsed by default.

### WA-06: Menu & Discovery
*Browse-only menu with quest highlights.*

**UI Elements:**
- **Categories:** Scrollable chips (Starters, Mains, Drinks).
- **List:** Item Name, Price, Description, Photo.
- **Badges:** "🌟 Quest Item" (if matches active quest).
- **Search:** Search bar at top.

### WA-07: Rewards & Wallet
*Redemption center.*

**UI Elements:**
- **Balance Card:** Large VC display. Star count (Tier status).
- **Redeemable Rewards (Grid):**
    - Cards: Reward Name, Cost (e.g., "500 VCs"), Image.
    - Status: "Redeem" (Active) or "Need 100 more" (Disabled).
- **Redemption Modal:**
    - "Redeem Free Coffee for 500 VCs?"
    - "Swipe to Confirm".
    - Generates QR code for staff scan.

### WA-08: Bill & Payment
*Settlement and splitting.*

**UI Elements:**
- **Bill Input:** Large numeric keypad (if manual).
- **Credit Slider:** "Use VCs: 0 ---[O]--- 500".
- **Table Pot Toggle:** "Use Table Pot (450 VCs)?"
- **Split Options:**
    - "Split Equally" (Default).
    - "Enter Custom Amounts".
- **Final Summary:**
    - "Total: ₹3000".
    - "Less VCs: -₹500".
    - "To Pay: ₹2500".

### WA-09: Post-Visit (App Conversion)
*The "Upsell" to native app.*

**UI Elements:**
- **Summary Card:** "You earned 650 VCs today!".
- **Streak:** "2 day streak! Come back tomorrow to keep it."
- **Locked Features (Teasers):**
    - "🔒 You are #5 on the Leaderboard. Download app to see who is #1."
    - "🔒 Unlocked 'regular' badge. Claim in app."
- **Primary CTA:** "Download App to Claim Rewards" (Link to App Store/Play Store).
- **Secondary CTA:** "Maybe Later" (Dismiss to Venue Landing).

---

## 5. Technical Requirements

-   **Auth:** Supabase Auth (Passwordless OTP).
-   **Database:** Supabase (Postgres) for user profiles, transaction logs.
-   **State:** LocalStorage for session persistence (cookie fallback).
-   **Geolocation:** HTML5 Geolocation API for proximity check.
-   **Analytics:** PostHog/Vercel Analytics for tracking conversion funnel.
-   **PWA:** Service Worker for offline menu caching.

