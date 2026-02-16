# Compliance & Regulatory Structure

> Last updated: Feb 16, 2026
> Aligned with: `product/credit-system.md` (canonical)

## Overview

CheckIn's dual credit economy requires careful regulatory structuring to operate legally in India while preserving economic viability. The core architectural decision: **both Venue Credits (VCs) and Global Credits (GCs) are structured as non-VDA loyalty points** under Indian law.

The original design treated GCs as VDA tokens (ERC-20, 30% tax, crypto infrastructure). The revised architecture eliminates the entire VDA tax burden, removes RBI scrutiny, avoids FEMA complications, and creates a simpler narrative for investors and users. Blockchain may be used as backend infrastructure in the future, but the user-facing product is a clean loyalty engine.

## Venue Credits (VC) — Non-VDA Loyalty Point Classification

### Legal Framework

VCs are structured as **closed-loop reward points exempt from VDA definition** under CBDT Notification No. 74/2022, which excludes "mileage points, reward points or loyalty card, being a record given without direct monetary consideration under an award, reward, benefit, loyalty, incentive, rebate or promotional program that may be used or redeemed only to obtain goods or services or a discount on goods or services."

Three criteria that MUST be maintained:

1. **No Direct Monetary Consideration:** VCs earned via non-monetary actions only (quests, streaks, check-ins — never purchased for cash)
2. **Service Redemption Only:** Usable only for goods/services within the venue (never convertible to fiat, no cash-out)
3. **Non-Transferable (with limits):** Social gifting within platform may be permitted, but no off-ramp to INR or third-party exchange

**RBI classification:** No PPI license needed. Closed System PPIs are exempt from RBI authorization. VCs are even simpler than closed-loop PPIs — they're loyalty points, not stored value.

### Tax Treatment

| Tax Type | Treatment | Basis |
|----------|----------|-------|
| **Income Tax** | Excluded from VDA definition → no 30% capital gains tax | CBDT Notification No. 74/2022 |
| **TDS** | No 1% TDS on internal VC transfers | Not classified as VDA |
| **Tax on Users** | Zero — loyalty point earnings function as a rebate on engagement, not income | Same treatment as credit card rewards, airline miles, CRED coins |
| **GST** | Trade discount at time of supply. Conservative approach: charge GST on full bill value regardless of VC payment method | See GST Treatment section below |

### B2B Circulation

Venues accumulate VCs from customer redemptions into a Merchant Wallet. They can use accumulated VCs to offset SaaS subscription payments to CheckIn (e.g., ₹5,000 cash + ₹3,000 VC value for ₹8,000/month subscription). This creates economic switching costs — leaving CheckIn means forfeiting accumulated VC balance.

## Global Credits (GC) — Non-VDA Loyalty Point Classification

### Legal Framework

**Critical update (Feb 2026):** GCs are now classified as **non-VDA loyalty points** — the same classification as VCs. The original design treated GCs as VDA-adjacent due to their cryptographic nature and cross-venue portability. The revised architecture eliminates this entirely.

GCs are structurally identical to multi-brand loyalty programs like airline miles, CRED coins, or Paytm cashback. They are earned through non-monetary activity, redeemable only for goods/services, and not convertible to cash. The same Notification 74/2022 exemption applies.

**What makes this work:**
- GCs are earned through quests/referrals/activity — never purchased for cash
- GCs are redeemable only for goods/services at CheckIn venues — no fiat off-ramp
- GCs sit on a centralized database ledger — NOT blockchain, NOT ERC-20 tokens
- GCs cannot be traded on any exchange — public or private
- No P2P transfers that could create a shadow market

**What would break this:**
- Allowing users to buy GCs for cash → makes them a PPI, requires RBI license
- Allowing fiat off-ramp → makes them a payment instrument
- Putting them on a public blockchain → risks VDA classification
- Allowing P2P trading → creates exchangeability that breaks the exemption
- Pegging to a floating exchange rate → implies speculative value

### Tax Treatment

| Tax Type | Treatment | Basis |
|----------|----------|-------|
| **Income Tax** | Excluded from VDA definition → no 30% capital gains tax | CBDT Notification No. 74/2022 (same as VCs) |
| **TDS** | No 1% TDS on GC transfers | Not classified as VDA |
| **Tax on Users** | Zero — same loyalty point treatment as VCs | Same treatment as airline miles, CRED coins, Paytm cashback |
| **GST on Platform Fee** | 18% GST on service fee retained from brand campaigns | Supply of Marketing Services |
| **GST on Redemptions** | Venue pays GST on full bill value when GC used | Third-Party Consideration per Section 2(31) |
| **Breakage (Expired GCs)** | No supply → ₹0 taxable → 0% GST | CBIC Circular No. 243/37/2024 |

### GC-Specific Mitigations (Belt and Suspenders)

Even though GCs qualify for non-VDA exemption, additional safeguards reduce any residual risk:
- **Usage cap:** GC bill payments capped at X% of bill value to prevent "surrogate currency" designation per RBI concerns
- **No public exchange:** GCs cannot be traded on public crypto exchanges; remain within CheckIn ecosystem
- **No fiat off-ramp:** Users cannot convert GCs back to cash
- **Centralized ledger:** No blockchain, no ERC-20 tokens — pure database entries

## GST Treatment — Detailed

| Event | GST Treatment | Basis |
|-------|---------------|-------|
| VC redemption at venue | Venue applies trade discount. If 100% VC bill, taxable value adjusted accordingly. Venue should still charge GST on the discounted value. | Trade discount at time of supply |
| GC redemption at venue | Third-party consideration: venue receives reimbursement from CheckIn. GST applies on full bill value. | Section 2(31) — third-party consideration |
| GC breakage (expired) | No supply occurred → ₹0 taxable → 0% GST | CBIC Circular 243/37/2024 |
| CheckIn platform fee | 18% GST on service fee retained from brand campaigns | Supply of marketing services |

**Important note:** The GST treatment of loyalty point redemptions is an evolving area. The precise treatment should be validated with a GST advisor, especially for 100% VC bill scenarios. The conservative approach: venue charges GST on the original bill value and treats VC redemption as a payment method, not a discount. This needs a formal legal opinion before launch.

### Detailed Tax Calculation Example

Brand pays ₹100 for campaign:

1. **Platform Fee (₹20):** Supply of Services → 18% GST → ₹3.60 tax
2. **Redeemed Credits (₹64, assuming 80% redemption):** Third-party consideration → 18% GST on full bill value at venue
3. **Breakage (₹16, unredeemed):** No Supply per CBIC Circular → 0% GST → ₹0 tax

## Global Expansion — Multi-Rail Design

### Step 1: Onshore Loyalty (India)

- Operational credit system as Centralized Database Ledger (not blockchain)
- Both VCs and GCs maintain "Loyalty Point" non-VDA tax exemption
- No PPI license required, no VDA issuer compliance burden

### Step 2: Offshore Value Accrual (Global — Deferred to Post-PMF)

- Establish **Offshore Foundation** (Singapore under MAS or Dubai under VARA) to issue governance token (**CKIN**)
- Relevant only for non-India markets and only after India PMF is proven
- No development or legal work on CKIN needed pre-fundraise

### FEMA & Cross-Border Settlement

**Challenge:** Settling value for Indian user redemptions at foreign brands involves FEMA (Foreign Exchange Management Act) considerations.

**Solution — Structured as B2B Marketing Service Agreement:**

1. **B2B Settlement:** CheckIn India doesn't send money per user transaction. CheckIn Global Entity (Offshore) pays foreign brands directly.
2. **Export/Import of Services:** Relationship structured as Marketing Service Agreement — CheckIn India "exports" user engagement data to Global entity; credit settlement treated as inter-company adjustment for marketing services.
3. **No LRS Impact:** User redeeming loyalty points (no independent cash-out value) for discount typically NOT treated as outward remittance under the Liberalised Remittance Scheme (LRS).

## Key Regulatory Risks

| Risk | Severity | Mitigation |
|------|----------|-----------|
| GCs reclassified as VDA | Medium | Maintain strict non-VDA criteria: no cash purchase, no fiat off-ramp, no public blockchain, no P2P trading, no floating exchange rate |
| RBI "surrogate currency" concern | Low-Medium | Cap GC bill payments at X% of bill value, maintain that GCs are not a payment instrument but a loyalty currency |
| VC loses loyalty point exemption | Low | Maintain three criteria: no cash purchase, service-only redemption, limited P2P. Document all compliance measures. |
| GST treatment challenged | Medium | Get formal GST opinion before launch. Conservative approach: charge GST on full bill value regardless of VC/GC payment method |
| FEMA cross-border issues | Medium | B2B Marketing Service Agreement structure, no per-user remittance |
| Credit inflation/devaluation | Medium | AI agent monitors faucet/sink ratios. Dynamic decay on VCs. Strict 1:1 GC backing. Per-venue VC budget caps. |

## Key Compliance Contacts

[FOUNDER INPUT NEEDED — Aravind to fill:]

- **Startup Lawyer:** [Name, firm, contact — Bengaluru-based, startup/fintech experience preferred]
- **CA Firm:** [Name, contact — for GST registration, tax filings, compliance advisory]
- **Compliance Advisor:** [Name, contact — if separate from lawyer, for PPI/VDA regulatory guidance]

Recommended profiles to look for in Bengaluru:
- Lawyer with fintech/loyalty/payments experience (understands PPI and VDA classification)
- CA firm experienced with startup taxation, ESOPs, and Section 56 valuations
- Consider firms like Ikigai Law, Khaitan & Co, or Trilegal for regulatory matters

## Regulatory Timeline

| Milestone | Owner | Target Date | Status | Notes |
|-----------|-------|-------------|--------|-------|
| Company incorporation (Pvt Ltd) | Aravind | Mar 2026 | [FOUNDER INPUT NEEDED] | Required before fundraise close |
| GST registration | Aravind + CA | Within 30 days of incorporation | Not started | Required once revenue begins |
| PPI license assessment | Aravind + Lawyer | Post-raise M2 | Not started | Likely NOT required given non-VDA structure for both VCs and GCs, but confirm with counsel |
| CA firm retained | Aravind | Feb 2026 | [FOUNDER INPUT NEEDED] | For ongoing tax compliance |
| Startup lawyer retained | Aravind | Feb–Mar 2026 | [FOUNDER INPUT NEEDED] | For incorporation, SHA, fundraise docs |
| Compliance review of credit-system.md | Aravind + Lawyer | Mar 2026 | Not started | External counsel validates VC/GC non-VDA classification |
| GST formal opinion | Aravind + CA | Pre-launch | Not started | Formal legal opinion on loyalty point redemption GST treatment |
| Offshore foundation scoping | Aravind | Post-raise M6+ | Not started | Singapore vs. Dubai — decision needed for CKIN token structure |
| FEMA compliance review | Aravind + Lawyer | Post-raise M6+ | Not started | Only relevant when cross-border GC settlement begins |

---

Sources: product/credit-system.md (canonical), Dual-Coin Economy for CheckIn: Regulatory Arbitrage, Corporate Structuring, and Economic Viability; GC/VC Specific - Utility and Compliance; CBDT Notification 74/2022; CBIC Circular 243/37/2024
