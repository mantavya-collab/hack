# Agents & Coding Conventions — VolunteerHQ

## AI Agent Guidelines & Prompting Conventions
1. **Browser-First Principle:** All code generated or modified by AI agents must run natively in the browser without Node.js backends, external databases, or secret API keys.
2. **Fictional Data Enforcement:** Never introduce real personal identifiable information (PII), phone numbers, or real emails. Always append (Mock) to sample volunteer identities.
3. **UI & Accessibility Standards:** Maintain high-contrast status indicators (Red pulsing badges for Understaffed roles, Emerald badges for Fully Staffed roles, and Amber panels for Minute 40 Twist reassignment recommendations).
4. **Modular Vanilla JS Functions:** Keep state mutations pure and always call saveState() and enderAll() to guarantee real-time capacity calculations stay synchronized.
