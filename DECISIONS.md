# Technical Decisions & Rationale — VolunteerHQ

## 1. Single-File Vanilla JS + Tailwind CDN vs. Heavy Framework
- **Decision:** Built the entire prototype inside a self-contained index.html using vanilla JavaScript and Tailwind CSS CDN.
- **Rationale:** Guarantees zero build failures, instant preview loading on GitHub Pages, and 100% compliance with Rule 01 (Browser-First) and Rule 02 (No .env dependency).

## 2. Skill + Cross-Shift Reassignment Scoring Algorithm
- **Decision:** Ranked replacement volunteers using a composite score of Skill Tag match (Tech Support, Hospitality, Logistics, General), reliability rating, and cross-shift availability.
- **Rationale:** Directly satisfies the Minute 40 Twist requirement to suggest intelligent reassignments when a last-minute dropout causes a role to become understaffed.

## 3. LocalStorage with Instant Sample Reset
- **Decision:** Persisted changes in localStorage while providing a top-level Reset Data button.
- **Rationale:** Allows judges to test the 3-step verification path repeatedly without losing state on refresh.
