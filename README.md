# VolunteerHQ — Problem Card 23 (VibeSprint 2026)

> **🎯 30-Second Judge Quickstart:** Open `index.html` (or the live GitHub Pages preview URL) and click the 3 numbered buttons in the top **30-Second Judge Verification Bar**:
> 1. **1️⃣ Step 01: Show Capacities & Sign-Ups**
> 2. **2️⃣ Step 02: Simulate Last-Minute Dropout (Minute 40 Twist)**
> 3. **3️⃣ Step 03: Auto-Reassign Best Replacement**

---

## DOC-01: README & Quickstart

* **Project Purpose:** **VolunteerHQ** (Problem Card 23) enables event organisers to create volunteer shifts with required capacities and skill tags, allows volunteers to sign up and check in on-site, highlights understaffed roles in real time, and recommends skill-matched replacement volunteers when a last-minute dropout occurs.
* **Core Features:**
  1. **Create Roles / Shifts:** Input validation for Role Title, Shift Time Window, Venue/Zone, Required Volunteer Capacity (1–25), and Skill Tag.
  2. **Volunteer Sign-Up & Check-In Workflows:** Instant volunteer sign-up and 1-click on-site check-in toggle.
  3. **Real-Time Capacity Calculations:** Live event-wide staffing summary bar and per-shift progress bars.
  4. **Minute 40 Twist (Last-Minute Dropout & Intelligent Reassignment):** Simulating a cancellation immediately highlights the understaffed role in pulsing red and ranks available replacement volunteers from the Standby Pool and cross-shift rosters based on Skill Match, Availability Window, and Campus Zone.
  5. **1-Click CSV Staffing Export:** Downloads a complete attendance and staffing spreadsheet locally in the browser.
* **No-Secret Setup Steps:**
  1. Clone or download this repository.
  2. Double-click `index.html` to open directly in any modern browser (Chrome, Edge, Firefox, Safari). Zero `.env` files, zero API keys, and zero package installations required.
* **Pre-Loaded Demo Data:** Loads immediately with 3 fictional shifts (*Registration & Welcome Desk*, *AI-ML Lab 4 Judge & Tech Runner*, *Refreshments & Logistics Counter*) and 5 fictional standby volunteers.
* **Known Limitations:** Data persists locally per browser via `localStorage`; external SMS/WhatsApp notifications are intentionally simulated via the on-screen *Local In-App Dispatch Log* per competition rules.

---

## DOC-02: Judge Runbook (60-Second Demo Script)

1. **0–10s (Starting State):** Open the live app. Observe the top **Real-Time Capacity Bar** (`6 / 7` volunteers staffed across 3 fictional shifts) and the pre-loaded understaffed shift in *AI-ML Lab 4*.
2. **10–25s (Step 01 — Role Capacity & Sign-Ups):** Look at *Registration & Welcome Desk* (`3 / 3` capacity). Click **Check In** next to *Kabir Menon (Mock)*.
   * **Expected Output:** Checked-in count updates to `3 / 3` in real time and logs in the *Local In-App Dispatch Log*.
3. **25–45s (Step 02 — Where the Twist Appears):** Click **2️⃣ Step 02: Simulate Last-Minute Dropout** in the top bar (or click **⚡ Simulate Last-Minute Dropout** on any shift card).
   * **Expected Output:** One volunteer cancels, the shift card border pulses red with an `⚠️ UNDERSTAFFED` alert badge, and the yellow **Minute 40 Twist Suggested Replacement Volunteers** panel appears inside the card.
4. **45–60s (Step 03 — Suggested Replacement Volunteer):** Click **3️⃣ Step 03: Auto-Reassign Best Replacement** (or click **✨ Reassign & Check In** next to the top-ranked candidate).
   * **Expected Output:** The highest-scoring available volunteer is reassigned and checked in on-site, restoring full capacity and turning the card green (`✓ FULLY STAFFED`).
5. **Simulated Features Note:** Volunteer notifications are simulated via the on-screen *Local In-App Dispatch Log* (no external SMS/WhatsApp APIs required).

---

## DOC-03: Five-Test Checklist

| # | Test Category | Exact Steps | Expected Result |
| :--- | :--- | :--- | :--- |
| **1** | **Invalid Input Test** | Click **+ Create Shift Role** with empty fields (or click **Run Test 1** inside the on-page DOC-03 card). | Form submission is blocked; a red validation error banner displays. |
| **2** | **Happy Path Test** | Create shift *Stage Mic Runner* (Time: `03:45 PM - 04:30 PM`, Venue: `Main Auditorium`, Capacity: `1`), sign up *Devika Nair (Mock)*, and click **Check In** (or click **Run Test 2**). | New shift appears at top of board, capacity reaches `1 / 1 (100%)`, and status badge turns green (`✓ FULLY STAFFED`). |
| **3** | **Twist Check** | Click **⚡ Simulate Last-Minute Dropout** on any staffed shift, then click **✨ Reassign & Check In** on the top suggested replacement. | Shift highlights red (`⚠️ UNDERSTAFFED`), displays ranked replacements by skill/availability, and returns to `✓ FULLY STAFFED` upon reassignment. |
| **4** | **Reset / Refresh Check** | Make changes to shifts, refresh the browser (`F5`) to verify persistence, then click **🔄 Reset Demo**. | All edits survive browser refresh via `localStorage`; clicking **Reset Demo** cleanly restores initial sample data. |
| **5** | **Boundary Case Test** | Attempt to enter required capacity `0` or `>25`, or trigger dropout on a shift with `0` volunteers (or click **Run Test 5**). | Action is safely blocked with a warning alert banner; volunteer counts never drop below `0`. |

---

## DOC-04: User Quickstart (Four-Step Guide)

1. **What the App Does:** VolunteerHQ is an all-in-one command center for event organisers to create volunteer shifts, check in volunteers on arrival, spot understaffed roles immediately, and auto-fill last-minute dropouts.
2. **What Input to Provide:**
   * **Organisers:** Fill in Role Title, Shift Time Window, Venue/Zone, Required Capacity (1–25), and Skill Tag in the left panel and click **+ Create Shift Role**.
   * **Volunteers:** Enter a fictional name in any shift card's bottom input box and click **+ Sign Up**.
3. **What Result to Expect:** Instant recalculation of top capacity metrics, live progress bars on every shift card, red pulsing alerts when a role is understaffed, and ranked replacement suggestions.
4. **How to Recover from a Mistake:** Click **Undo Check-In** to revert an accidental check-in, or click **🔄 Reset Demo** in the top verification bar to restore the clean default state immediately.

---

## DOC-05: Data & Privacy Note

* **Stored Fields Schema:**
  * **shifts:** `id`, `role`, `time`, `location`, `requiredCount`, `skillTag`, `lastDropout`, and `volunteers[{ name, checkedIn, skill }]`
  * **availablePool:** `id`, `name`, `skill`, `currentStatus`, `freeWindow`, and `reliability`
  * **auditLogs:** Timestamped array of local check-in, dropout, and reassignment strings
* **Local Browser Storage Only:** All state is stored strictly inside the user's browser via `window.localStorage` keys (`vhq_win_shifts`, `vhq_win_pool`, `vhq_win_logs`, `vhq_win_reassigned`).
* **Demo / Fictional Data Only:** All pre-loaded and user-added volunteer profiles use fictional mock names tagged with `(Mock)`. No real student PII, phone numbers, or emails are collected.
* **Zero External Network Transmission & Zero Secrets:** The application never sends form data, attendance logs, or messages to any external server, database, or SMS/WhatsApp service. **Confirmed: Zero API keys, zero tokens, and no `.env` files are included anywhere in this repository.**

---

## DOC-06: Handoff & Limitations

* **Main Files & Components:**
  * `index.html`: Self-contained Single-Page Application containing the UI, real-time capacity calculator, Minute 40 Twist reassignment engine, and embedded DOC-01 to DOC-06 cards.
  * `README.md`, `PRD.md`, `ARCHITECTURE.md`, `AGENTS.md`, `TASKS.md`, `DECISIONS.md`, `CONTEXT.md`: Complete product and engineering documentation artifacts.
* **Where Core Logic Lives:** Inside the embedded ES6 JavaScript block of `index.html`:
  * `renderAll()` computes real-time capacity percentages and updates the DOM.
  * `simulateDropout()` triggers the Minute 40 Twist cancellation state and understaffed alerts.
  * `getIntelligentRecommendations()` scores standby and cross-shift replacement candidates by Skill Tag match, availability window, and zone proximity.
* **How Demo Data is Reset:** Clicking **🔄 Reset Demo** runs `resetDemoData()`, overwriting `localStorage` with fresh copies of the default fictional shifts and standby pool.
* **What is Deliberately Mocked:** Multi-device database synchronization, login authentication, and external SMS/WhatsApp push notifications are deliberately mocked via the local Dispatch Audit Log in accordance with VibeSprint rules.
* **Top 3 Improvements Needed for Real Deployment:**
  1. **Real-Time Multi-Device Sync:** Connect state to a WebSocket/Supabase/Firebase backend so multiple organisers across different gates see live check-ins simultaneously.
  2. **Role-Based Auth & QR Check-In:** Separate Organiser Admin dashboards from Volunteer views with unique QR codes for scan-to-check-in at event venues.
  3. **Automated Time-Conflict Parser & Opt-In Push Alerts:** Parse exact `HH:MM` shift timestamps to prevent overlapping sign-ups and send opt-in web push notifications when a volunteer is reassigned..
     
