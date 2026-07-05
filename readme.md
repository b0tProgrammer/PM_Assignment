# Age-Aware Privacy: DPDP Act 2023 Consent Flow

An end-to-end, interactive front-end prototype demonstrating how a high-scale consumer platform (YouTube) can seamlessly integrate India's Digital Personal Data Protection (DPDP) Act, 2023, without destroying the user onboarding experience. 

Designed and developed as a Product/UX assignment for Vedantu.

## 🚀 What I Did

I designed a friction-minimized onboarding and data management flow that legally categorizes users, secures verifiable parental consent, and provides an accessible "Data Wallet" for privacy controls. 

The deliverables include:
*   **Product Thinking Strategy:** A framework balancing strict legal mandates (Section 6 and Section 9 of the DPDP Act) with user retention and daily active user (DAU) metrics.
*   **Clickable Prototype:** A responsive, zero-dependency web application simulating the "happy path" of age verification, parental handoff, and itemized data consent.

## 🧠 The Problem Context

The DPDP Act 2023 introduces massive friction for consumer apps:
1.  **Verifiable Parental Consent:** Users under 18 cannot legally consent to data processing. Platforms must verify a guardian's identity. 
2.  **Strict Minor Protections:** Platforms are entirely prohibited from tracking minor behavioral data or serving targeted ads.
3.  **Right to Erasure:** Users must be able to withdraw consent and delete their data just as easily as they provided it—outlawing deeply buried privacy settings.
4.  **The UX Paradox:** Forcing every user to upload a government ID (like an Aadhaar card) to prove their age causes severe user drop-off and violates the principle of "Data Minimization."

## 🛠️ How I Solved This Problem

To resolve the tension between legal compliance and user experience, I engineered a flow relying on progressive verification and edge-case routing.

### 1. Stateless AI Age Estimation
Instead of demanding hard documents upfront, the app uses a simulated front-facing camera scan to estimate the user's age. The image is processed as a mathematical vector and instantly dropped from memory (Stateless Processing), meaning no biometric data is ever stored. This instantly clears the vast majority of adult users with zero friction.

### 2. The "Buffer Zone" Strategy
Because AI estimation has a margin of error (~3 years), the adult threshold is strategically set to 21 instead of 18. 
*   **Estimated ≥ 21:** Instantly categorized as an adult.
*   **Estimated < 21:** Placed in the legal buffer zone and safely routed to the Guardian verification flow to prevent false-negative liabilities.

### 3. Verifiable Guardian Handoff & DOB Confirmation
For users flagged as minors, the app enters a locked, untracked state. The minor triggers an SMS handoff to a guardian. The guardian completes a secure OTP verification and manually inputs the student's exact Date of Birth. This satisfies the legal verification mandate and allows the system to automatically upgrade the account when the student legally turns 18.

### 4. The Privacy "Data Wallet"
To comply with the "ease of withdrawal" mandate, the traditional settings menu is replaced with a centralized Data Wallet. It features:
*   Itemized toggle switches for specific data processing (Location, Watch History).
*   A clear "Privacy Protection %" score.
*   A high-contrast, one-click "Clear My Data" function.
*   **Minor Lockout:** In the guardian-managed wallet, behavioral tracking toggles are permanently disabled to comply with Section 9(3) bans on minor profiling.

## 💻 Tech Stack
*   **HTML5 & CSS3:** Custom, responsive layout designed for modern mobile viewports.
*   **Vanilla JavaScript:** Handles state management, view routing, dynamic UI updates, and OTP input logic without external libraries.
*   **Zero Dependencies:** Runs entirely in the browser for maximum portability.

## 🏃‍♂️ How to Run Locally

1.  Clone this repository to your local machine.
2.  Navigate to the project directory.
3.  Double-click `index.html` to open it in any modern web browser.
4.  Use the interactive left-hand sidebar to jump between different user states (Adult, Minor, Guardian OTP).

---
**Author:** Sandaka Mohith Kumar
