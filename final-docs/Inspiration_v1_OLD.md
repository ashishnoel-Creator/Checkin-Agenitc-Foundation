
# **Checkin MVP \- User Flow Document**

**Version 1.0 \- May 27, 2025**

## **1\. Introduction**

This document outlines the primary user flows for the "Checkin" Minimum Viable Product (MVP). It details the sequence of screens and key interactions a user experiences within both the initial web application (triggered by QR code scan) and the native mobile application (iOS & Android) to achieve specific objectives. The screen IDs used (e.g., W1, N5, V1) correspond to the wireframes discussed.

## **2\. Web App Flows (Initial Interaction & App Download Drive)**

These flows describe the user's first encounter with Checkin, typically initiated by scanning a QR code at a partner venue. The primary goals are to provide immediate value for the current session and strongly encourage native app download.

### **Flow 1.1: First-Time User \- QR Scan to Web App Session & Native App Prompt**

* **Goal:** A brand new user scans a venue QR, completes a lightweight web-based signup & check-in, experiences core quest mechanics for the current session, and is strongly encouraged to download the native app.  
* **Trigger:** User scans a venue QR code with their phone's camera.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | (External) | QR Scan | User scans venue QR code. | Browser opens URL from QR code. |
| 2 | W0 | Web App \- Animated Welcome & Value Proposition | (Passive viewing) | Auto-transitions after 3-5 seconds. |
| 3 | W1 | Web App \- Mobile Number Entry | User enters mobile number; taps "Continue". | System checks if mobile is new to Checkin. If new \-\> **W1.B**. If existing (unlikely for this flow, but possible) \-\> **W1.C**. |
| 4 | W1.B | Web App \- Name Collection | User enters First & Last Name; taps "Next". | Proceeds to **W1.C**. |
| 5 | W1.C | Web App \- Location Permission Request | User taps "Allow Location & Continue" OR "Continue without Location". | Browser location prompt appears if "Allow" chosen. `location_access` status set. Proceeds to **W1.A**. |
| 6 | W1.A | Web App \- OTP Verification | User enters OTP; taps "Verify & Proceed". | Validates OTP. Proceeds to **W2**. |
| 7 | W2 | Web App \- Personalized Welcome & Location Status | (Passive viewing or tap to continue) | Displays message based on `location_access` & GPS check. Auto-transitions or user tap. Proceeds to **W3**. |
| 8 | W3 | Web App \- Venue Quest Dashboard | View quests, manage table (W3A), view leaderboard (W3B), etc. | `location_verified_at_venue` status enables/disables features. User interacts with quests (may trigger **UTIL\_PIN\_MODAL**). User sees "Download App" CTA. |
| 9 | (External) | App Store / Google Play | User taps "Download App" CTA on W3. | User is redirected to the respective app store. |

Export to Sheets

### **Flow 1.2: Returning Web App User \- QR Scan to Web App Session**

* **Goal:** A user who has previously used the web app (but may not have the native app) scans a QR and re-engages.  
* **Trigger:** User scans a venue QR code.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1-2 |  | (Same as Flow 1.1, Steps 1-2) |  |  |
| 3 | W1 | Web App \- Mobile Number Entry | User enters mobile number; taps "Continue". | System recognizes existing mobile (W1.B skipped). Proceeds to **W1.C**. |
| 4 | W1.C | Web App \- Location Permission Request | User taps "Allow Location & Continue" OR "Continue without Location". | Browser location prompt if "Allow" chosen. `location_access` status set. Proceeds to **W1.A**. |
| 5 | W1.A | Web App \- OTP Verification | User enters OTP; taps "Verify & Proceed". | Validates OTP. Proceeds to **W2**. |
| 6 | W2 | Web App \- Personalized Welcome & Location Status | (Passive viewing or tap to continue) | Displays message based on `location_access` & GPS check. Auto-transitions or user tap. Proceeds to **W3**. |
| 7 | W3 | Web App \- Venue Quest Dashboard | User interacts as in Flow 1.1, Step 8\. | User sees "Download App" CTA or ends web session. |

Export to Sheets

## **3\. Native Mobile App Flows**

These flows describe user interactions within the installed native Checkin application.

### **Flow 2.1: New User \- Native App Onboarding (Post-Download)**

* **Goal:** A new user who has just downloaded the native app completes the onboarding process.  
* **Trigger:** User opens the Checkin native app for the first time.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | N1 | Native App \- Splash/Welcome Screen | (Passive viewing) | Auto-transitions. |
| 2 | N2 | Native App \- Login/Signup Screen | User enters mobile number; taps "Continue". | Proceeds to **N\_OTP1**. |
| 3 | N\_OTP1 | Native App \- OTP Verification | User enters OTP; taps "Verify". | System recognizes mobile as new. Proceeds to **N3**. |
| 4 | N3 | Native App \- Basic Profile Setup Screen | User enters Name, optional Photo/DoB; taps "Save & Continue". | Profile data saved. Proceeds to **N4**. |
| 5 | N4 | Native App \- Permissions Request Screens | User grants/denies Location, Contacts, Notifications. | Permissions status recorded. Proceeds to **N5**. |
| 6 | N5 | Native App \- Home Screen | User lands on the main discovery hub. |  |

Export to Sheets

### **Flow 2.2: Existing User \- Native App Login**

* **Goal:** An existing native app user logs into the app.  
* **Trigger:** User opens the Checkin native app.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1-2 |  | (Same as Flow 2.1, Steps 1-2) |  |  |
| 3 | N\_OTP1 | Native App \- OTP Verification | User enters OTP; taps "Verify". | System recognizes existing user. Proceeds to **N5**. |
| 4 | N5 | Native App \- Home Screen | User lands on the main discovery hub. |  |

Export to Sheets

### **Flow 3.1: Venue Discovery & Initiating Check-in**

* **Goal:** User explores venues within the native app and decides to check into one.  
* **Trigger:** User is on the Home Screen (N5) or Venue Listing (N6).

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | N5 / N6 | Home Screen / Full Venue Listing/Map View | User browses venues. Taps Search Icon \-\> **N\_SEARCH1** \-\> **N\_SEARCH2**. Taps Filter \-\> **N6.A**. | User identifies a venue of interest. |
| 2 | V1 | Venue Profile Screen | User reviews venue info, quests. Taps "Scan QR to Check In & Participate". | Proceeds to **QRS1**. |
| 3 | QRS1 | QR Scanner View | User scans QR code at venue table. | System decodes QR, performs location verification (`location_verified_at_venue` status set). Proceeds to **V1.A**. |
| 4 | V1.A | Confirm Table Number Screen | User confirms/enters table number; taps "Confirm Table & View Quests". | Table association confirmed. Proceeds to **V2**. |
| 5 | V2 | In-Session Venue Dashboard | User is now checked in and engaging with quests, table pot, etc. | `location_verified_at_venue` status enables/disables features. |

Export to Sheets

### **Flow 3.2: Direct QR Scan Check-in**

* **Goal:** User is at a venue and directly uses the app's main QR scanner to check in.  
* **Trigger:** User taps "Scan QR" icon in Bottom Navigation Bar.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | QRS1 | QR Scanner View | User scans QR code at venue table. | System decodes QR, performs location verification (`location_verified_at_venue` status set). Proceeds to **V1.A**. |
| 2 | V1.A | Confirm Table Number Screen | User confirms/enters table number; taps "Confirm Table & View Quests". | Table association confirmed. Proceeds to **V2**. |
| 3 | V2 | In-Session Venue Dashboard | User is now checked in and engaging. | `location_verified_at_venue` status enables/disables features. |

Export to Sheets

### **Flow 4.1: In-Session Quest Engagement & Validation**

* **Goal:** While checked in (on V2), user views quest details and validates a quest requiring staff PIN.  
* **Trigger:** User is on Screen V2 (In-Session Venue Dashboard).

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | V2 | In-Session Venue Dashboard | User views active quests. Taps a Quest Card (or navigates via Q1 to a Quest Card). | Proceeds to **Q2**. |
| 2 | Q2 | Quest Detail Screen | User reviews quest. Taps "Validate Quest with Staff" (if eligible & requires manual validation). | Opens **UTIL\_PIN\_MODAL**. |
| 3 | UTIL\_PIN\_MODAL | Staff PIN Validation Modal | Staff enters Venue PIN; taps "Confirm Quest Completion". | System validates PIN. If successful, awards Credits (to Table Pot/Personal Wallet) & Stars. Closes modal. |
| 4 | Q2 / V2 | Quest Detail / In-Session Venue Dashboard | Quest shows as "Completed". User sees success feedback. Table Pot/Wallet on V2 updates. | User continues session. |

Export to Sheets

### **Flow 5.1: Bill Payment with Comprehensive Credit Pooling & Utilization**

* **Goal:** Payer utilizes personal and table-earned credits to reduce the bill, with staff verification.  
* **Trigger:** User taps "Ready to Pay / Utilize Credits" on Screen V2.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | BP1 | Enter Total Bill Amount Screen/Modal | Payer enters total bill amount from physical bill; taps "Next: Add Credits". | Proceeds to **BP2**. |
| 2 | BP2 | Contribute from Personal Wallets Screen/Modal | Payer inputs amounts each table member contributes from their personal venue wallets; taps "Next". | Tentatively reserves personal credits. Proceeds to **BP3**. |
| 3 | BP3 | Utilize from "Current Table Pot" Screen/Modal | Payer selects amount of "Current Table Pot" credits to utilize; taps "Review & Confirm". | Tentatively reserves Table Pot credits. Proceeds to **BP4**. |
| 4 | BP4 | Summary & Staff Verification Screen/Modal | User shows screen to staff. Staff verifies original bill amount, enters Venue PIN; taps "Authorize". | System validates PIN. If successful, deducts all committed credits (personal & pot). Proceeds to **BP5**. |
| 5 | BP5 | Payment Confirmation Screen | User views final amount payable to venue & credit utilization summary; taps "Done". | Backend finalizes session billing, distributes remaining Table Pot credits. Navigates to **V2** (updated) or **N5**. |

Export to Sheets

### **Flow 5.2: Bill Splitting (Post-Credit Utilization)**

* **Goal:** Payer splits the final net bill amount (after credits) among table members.  
* **Trigger:** User taps "Split This Amount with Your Table" on Screen BP5, or a "Split Last Bill" button on V2.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | BS1 | Initiate Bill Split Screen | Payer reviews final amount to split; taps "Choose How to Split". | Proceeds to **BS2**. |
| 2 | BS2 | Select Split Method Screen | Payer selects "Split Equally" OR "Enter Custom Amounts". | If "Split Equally" \-\> Calculates shares, proceeds to **BS4**. If "Enter Custom Amounts" \-\> Proceeds to **BS3**. |
| 3 | BS3 | Custom Split Input Screen | Payer inputs custom amounts for each member until total matches. Taps "Review Split Summary". | Proceeds to **BS4**. |
| 4 | BS4 | Bill Split Summary Screen | Users review individual shares. Payer taps "Done". | Informs users to settle externally. Navigates to **V2** or **N5**. |

Export to Sheets

### **Flow 6.1: Managing "My Rewards"**

* **Goal:** User views their overall rewards and detailed history for a specific venue.  
* **Trigger:** User taps "My Rewards" in Bottom Navigation Bar.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | R1 | "My Rewards" Main Screen | User views summary & list of venues with rewards. Taps a Venue Card. | Proceeds to **R2** for the selected venue. |
| 2 | R2 | Venue-Specific Wallet Screen | User views credit/star balance & transaction history for that venue. Filters history. Taps "Back". | Returns to **R1**. |

Export to Sheets

### **Flow 7.1: Engaging with Venue Community Features**

* **Goal:** User views a venue's leaderboard or announcements.  
* **Trigger:** User is on Screen V1 (Venue Profile) or V2 (In-Session Dashboard).

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1a | V1 / V2 | Venue Profile / In-Session Dashboard | User taps "View Full Leaderboard" or "Leaderboard" chip. | Proceeds to **L1**. |
| 2a | L1 | Native Venue Leaderboard Screen | User views leaderboard, selects timeframe. Taps "Back". | Returns to **V1 / V2**. |
| 1b | V1 / V2 | Venue Profile / In-Session Dashboard | User taps "View All Announcements" or "Updates" chip. | Proceeds to **A1**. |
| 2b | A1 | Native Venue Announcements Screen | User views announcements feed. Taps "Back". | Returns to **V1 / V2**. |

Export to Sheets

### **Flow 8.1: Managing Profile & Settings**

* **Goal:** User views their profile and accesses various settings.  
* **Trigger:** User taps "Profile" in Bottom Navigation Bar.

| Step | Screen ID | Screen Name | Key User Actions on this Screen | System Response / Next Screen |
| ----- | ----- | ----- | ----- | ----- |
| 1 | P1 | User Profile Main Screen | User views profile summary & activity. Taps "Edit Profile" OR a settings menu item. | If "Edit Profile" \-\> **P1.A**. If "Notification Settings" \-\> **P2.A**. If "App Permissions" \-\> **P2.B**. If "Privacy Controls" \-\> **P3**. If "Help" \-\> **SUP1**. If "Logout" \-\> Confirmation \-\> **N2**. |
| 2 | P1.A | Edit Profile Screen | User edits Name, Username, Photo, DoB; taps "Save" or "Cancel". | If "Save" & valid \-\> Returns to **P1** (updated). If "Cancel" \-\> Returns to **P1**. |
| 3 | P2.A | Notification Settings Screen | User toggles notification preferences. Taps "Back". | Preferences saved. Returns to **P1**. |
| 4 | P2.B | App Permissions Management Screen | User views permission info, taps links to OS settings. Taps "Back". | Returns to **P1**. |
| 5 | P3 | Privacy Controls Screen | User adjusts privacy toggles/selections. Taps "Back". | Preferences saved. Returns to **P1**. |

Export to Sheets

### **Flow 9.1: General Utility Flows**

* **Viewing Notifications:**  
  * **Trigger:** User taps Notification Bell on N5.  
  * **N\_NOTIF1 (Notifications Screen):** User views list, taps a notification to go to relevant context (e.g., Q2, R2, A1). Taps "Back". Returns to **N5**.  
* **Searching:**  
  * **Trigger:** User taps Search Icon on N5.  
  * **N\_SEARCH1 (Initial Search Screen):** User types query, taps "Search" or selects suggestion. \-\> **N\_SEARCH2 (Search Results Screen)**.  
  * **N\_SEARCH2:** User views results (Venues/Quests), taps a result. \-\> **V1** or **Q2**. Taps "Back". \-\> **N\_SEARCH1** or **N5**.  
* **Changing Discovery Location:**  
  * **Trigger:** User taps Location Indicator on N5.  
  * **N\_LOC\_MODAL1 (Location Change Modal):** User selects "Use Current Location" or searches for a new location; taps "Apply". \-\> Updates discovery results on **N5** (or **N6** if initiated there). Modal closes.

## **4\. Conclusion**

This User Flow Document provides a comprehensive map of the key user journeys within the Checkin MVP. It serves as a foundation for detailed UI design, development, and testing, ensuring a cohesive and intuitive user experience. Future iterations will build upon these core flows to incorporate advanced features and enhancements.

