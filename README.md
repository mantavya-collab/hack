# VolunteerHQ — Problem Card 23 (VibeSprint 2026)

## Overview
**VolunteerHQ** is a browser-first prototype that enables event organisers to create volunteer shifts, allows volunteers to sign up and check in on-site, highlights understaffed roles in real time, simulates sudden volunteer dropouts, and recommends skill-matched replacement volunteers from a standby pool.

## Core Features & Judge Verification Path
1. **Step 01 — Role Capacity & Sign-Ups:** Displays shifts with time, location, skill tag, required volunteer capacity, live sign-up counts, and on-site check-in toggles.
2. **Step 02 — Simulate Dropout & Understaffed Alert:** Clicking **"⚠️ Simulate Dropout"** removes a volunteer, triggers a visual dropout alert banner, and highlights the shift card in red as **UNDERSTAFFED**.
3. **Step 03 — Suggested Replacement Volunteer:** Whenever a role is understaffed, the app automatically matches an available volunteer from the fictional Standby Replacement Pool by skill tag and allows 1-click assignment.

## Non-Negotiable Build Rules Compliance
- **Browser-First & No `.env`:** Runs 100% locally in the browser using `localStorage` and pre-loaded fictional data. Zero external APIs or secret keys required.
- **Fictional Data Only:** All volunteer names and shifts use fictional mock data.

## How to Run Locally
1. Clone or download this folder.
2. Double-click `index.html` to open directly in any web browser (Chrome, Edge, Firefox, Safari).