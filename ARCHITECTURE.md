# System Architecture — VolunteerHQ

## 1. High-Level Structure
VolunteerHQ uses a zero-dependency, browser-first Single-Page Application (SPA) architecture contained within index.html using semantic HTML5, Tailwind CSS (via CDN), and vanilla JavaScript ES6+.

## 2. Core Components
- **State & Persistence Layer (localStorage):** Stores shifts, vailablePool, and uditLogs locally in the browser with instant fallback to pre-loaded fictional sample data.
- **Real-Time Capacity Calculator:** Dynamically computes total event staffing (signedUp / requiredCount), percentage filled, checked-in counts, and understaffed alerts on every state change.
- **Intelligent Reassignment Engine (getIntelligentRecommendations):** Evaluates available standby volunteers and non-checked-in volunteers from other shifts, scoring candidates by exact skill match (+50 pts) and reliability score to display the top 3 replacement recommendations.
- **Audit Log Component:** Records timestamped check-ins, shift creations, last-minute dropouts, and reassignments.

## 3. Data Flow
User Action (Create / Sign Up / Check In / Simulate Dropout / Reassign) -> JavaScript State Mutation -> localStorage Sync -> Instant DOM Re-render & Capacity Recalculation.
