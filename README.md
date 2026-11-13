# VolunteerHQ — Event Volunteer & Intelligent Reassignment System

## Project Overview
**VolunteerHQ** (Problem Card 23) is a browser-first web prototype built for VibeSprint 2026. Event organisers can create volunteer shifts with required capacities and skill tags, volunteers can sign up and check in on-site, and organisers can handle **last-minute dropouts (Minute 40 Twist)** with real-time understaffed alerts and intelligent replacement recommendations.

## Core Features
- **Shift Creation & Real-Time Capacity Calculations:** Tracks total event staffing percentage, required vs. signed-up counts, and live check-ins.
- **Volunteer Sign-Up & Check-In Workflows:** 1-click sign-up and on-site check-in status toggles.
- **Minute 40 Twist — Last-Minute Dropout & Intelligent Reassignment:** When a volunteer cancels last-minute, the interface immediately highlights the understaffed role in red and ranks available replacement volunteers by skill match and availability (from both the Available Standby Pool and cross-shift unassigned volunteers).
- **100% Browser-First & Privacy Safe:** Uses local state (localStorage) and fictional sample data. Zero external APIs, SMS/WhatsApp integrations, or .env keys required.

## Installation & Run Instructions
1. Clone or download this repository.
2. Open index.html directly in any modern web browser (Chrome, Edge, Firefox, Safari). No build step or server installation is required.
