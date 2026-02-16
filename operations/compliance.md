# Compliance & Regulatory Structure

> Last synthesized: Feb 15, 2026

## Overview

CheckIn's dual credit economy requires careful regulatory structuring to operate legally in India while preserving economic viability. The core challenge: avoiding the **VDA Tax Trap** (30% flat tax + 1% TDS on Virtual Digital Assets) while maintaining a high-velocity digital economy.

The solution is a **Hybrid Stack** that legally separates high-frequency venue utility from long-term platform value accrual.

## Venue Credits (VC) — Non-VDA Loyalty Point Classification

### Legal Framework

VCs are structured as **closed-loop reward points exempt from VDA definition** under Notification No. 74/2022. Three criteria must be maintained:

1. **No Direct Consideration:** VCs earned via non-monetary actions only (quests, streaks, check-ins — never purchased for cash)
2. **Service Redemption Only:** Usable only for goods/services within the ecosystem (bill coverage, song requests, table auctions — never convertible to fiat)
3. **Non-Transferable P2P (with limits):** Social gifting within platform permitted, but no off-ramp to INR or third-party crypto

### Tax Treatment

| Tax Type | Treatment | Basis |
|----------|----------|-------|
| **GST** | Redemptions = Trade Discounts at time of supply. 100% VC bill → taxable value ₹0 → venue GST liability effectively nullified | Standard trade discount treatment |
| **Income Tax** | Excluded from VDA definition → no 30% capital gains tax | Notification No. 74/2022 |
| **TDS** | No 1% TDS on internal VC transfers | Not classified as VDA |

### B2B Circulation

Venues accumulate VCs from customer redemptions into a Merchant Wallet. They can use accumulated VCs to offset SaaS subscription payments to CheckIn (e.g., ₹5,000 cash + ₹3,000 VC value for ₹8,000/month subscription). This creates economic switching costs — leaving CheckIn means forfeiting accumulated VC balance.

## Global Credits (GC) — VDA-Adjacent Classification

### Legal Framework

GCs are **likely classified as VDAs** under Section 2(47A) of the Income Tax Act due to their cryptographic nature and cross-venue portability.

**Mitigation strategies:**
- **Usage cap:** GC bill payments strictly capped at X% of bill value to prevent "surrogate currency" designation per RBI concerns
- **Governance utility:** GC balances determine Social Credibility Tiers (Gold, Platinum) with voting rights and early access — providing non-monetary utility justification
- **No public exchange:** GCs cannot be traded on public crypto exchanges; remain within CheckIn ecosystem
- **No fiat off-ramp:** Users cannot convert GCs back to cash

### Tax Treatment

| Tax Type | Treatment | Basis |
|----------|----------|-------|
| **Flat 30% Tax** | Any "gain" realized by user from GC (e.g., swapping airdropped GC) taxed at 30% | Section 115BBH |
| **1% TDS** | All GC transfers trigger 1% TDS obligation | Section 194S |
| **GST on Platform Fee** | CheckIn pays 18% GST on retained margin from brand campaigns | Supply of Marketing Services |
| **GST on Redemptions** | Venue pays GST on full bill value when GC used | Third-Party Consideration per Section 2(31) |
| **Breakage (Expired GCs)** | No supply → ₹0 taxable → 0% GST | CBIC Circular No. 243/37/2024 |

### Detailed Tax Calculation Example

Brand pays ₹100 for campaign:

1. **Platform Fee (₹20):** Supply of Services → 18% GST → ₹3.60 tax
2. **Redeemed Credits (₹64, assuming 80% redemption):** Supply of OIDAR Services → 18% GST → ₹11.52 tax
3. **Breakage (₹16, unredeemed):** No Supply per CBIC Circular → 0% GST → ₹0 tax

## Global Expansion — Multi-Rail Design

### Step 1: Onshore Loyalty (India)
- Operational credit system as Centralized Database Ledger (not blockchain)
- Maintains "Loyalty Point" tax exemption
- Avoids heavy VDA issuer compliance burden

### Step 2: Offshore Value Accrual (Global)
- Establish **Offshore Foundation** (Singapore under MAS or Dubai under VARA) to issue governance token (**CKIN**)
- Global users earn and trade CKIN directly as compliant digital asset under MiCA or MAS frameworks
- Indian users accumulate GCs internally; at "Platinum Tier," can elect **"Burn-to-Claim"** event:
  - Burn internal GCs
  - Receive CKIN tokens airdropped by Offshore Foundation to self-custodial wallet

### FEMA & Cross-Border Settlement

**Challenge:** Settling value for Indian user redemptions at foreign brands involves FEMA (Foreign Exchange Management Act) considerations.

**Solution — Structured as B2B Marketing Service Agreement:**

1. **B2B Settlement:** CheckIn India doesn't send money per user transaction. CheckIn Global Entity (Offshore) pays foreign brands directly.
2. **Export/Import of Services:** Relationship structured as Marketing Service Agreement — CheckIn India "exports" user engagement data to Global entity; credit settlement treated as inter-company adjustment for marketing services.
3. **No LRS Impact:** User redeeming "Loyalty Points" (no independent cash-out value) for discount typically NOT treated as outward remittance under the Liberalised Remittance Scheme (LRS).

## Key Regulatory Risks

| Risk | Severity | Mitigation |
|------|----------|-----------|
| GC reclassified as VDA | High | Strict closed-loop design, no public exchange, usage cap on bills |
| RBI "surrogate currency" concern | Medium | Cap GC bill payments at X%, maintain governance utility focus |
| VC loses loyalty point exemption | Low | Maintain three criteria: no cash purchase, service-only redemption, limited P2P |
| FEMA cross-border issues | Medium | B2B Marketing Service Agreement structure, no per-user remittance |
| GST on GC transactions | Low | Follow CBIC Circular 243/37/2024 for breakage treatment |

## Key Compliance Contacts

[TODO: Add legal counsel details, CA firm, compliance advisor]

## Regulatory Timeline

[TODO: Map key regulatory milestones — PPI license application, GST registration, offshore foundation setup]

---

Sources: Dual-Coin Economy for CheckIn: Regulatory Arbitrage, Corporate Structuring, and Economic Viability; GC/VC Specific - Utility and Compliance
