# Product Requirements Document (PRD) — VolunteerHQ

## 1. Problem Statement
College and community event organisers struggle to track volunteer shift capacities, on-site check-ins, and sudden last-minute volunteer cancellations. When someone drops out minutes before a shift, organisers lack immediate visibility into which role became understaffed and who is available to replace them.

## 2. Target Users
- **Event Organisers / Leads:** Need real-time visibility into shift capacities, understaffed roles, and instant replacement recommendations.
- **Event Volunteers:** Need a fast way to sign up for shifts and check in on-site.

## 3. Core Goals & Requirements
1. **Shift & Capacity Management:** Create roles with title, time, location, required volunteer count, and required skill tag.
2. **Sign-Up & Check-In Workflow:** Allow volunteers to sign up and check in on arrival with real-time capacity bars.
3. **Minute 40 Twist (Last-Minute Dropout & Reassignment):** Simulate a last-minute cancellation, immediately highlight the understaffed shift, and recommend ranked replacement volunteers from available pools based on skill match and availability.
4. **Non-Negotiable Constraints:** Browser-first execution, fictional mock data only, no .env secrets, and no external SMS/WhatsApp APIs.
