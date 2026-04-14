# Orbis - Progress Tracker

## App Overview
A streamlined K-12 school management platform — a modern alternative to Blackbaud.
Built with React + TypeScript + Vite.

## Tech Stack
- Frontend: React, TypeScript, Vite
- Package manager: npm
- Editor: VSCode
- Auth: Google OAuth (in progress)

## Design Decisions
- 4 screens: Dashboard, People & Records, Admin & Reports, Student Portal
- 3 roles: teacher, admin, student
- Style: clean but explicit (in between modern SaaS and traditional)
- Master-detail pattern: click a student → side panel opens
- Frontend permission checks are for UX only — backend must enforce separately
- Auth state persisted to localStorage so login survives page refresh

## Roles & Access
- teacher: Dashboard, People & Records, gradebook, attendance
- admin: Admin & Reports screen (enrollment, scheduling, reports)
- student: Student Portal only (own grades, classes, assignments, attendance)

## Files Completed
- .gitignore
- PROGRESS.md
- .env (Google OAuth client ID stored here)
- src/types/roles.ts
- src/context/AuthContext.tsx (with localStorage persistence)
- src/hooks/usePermissions.ts
- src/hooks/useRoleRoute.ts
- src/components/ProtectedSection.tsx
- src/pages/Dashboard.tsx
- src/pages/AdminReports.tsx (mock data)
- src/pages/StudentPortal.tsx (mock data)
- src/pages/PeopleRecords.tsx (mock data, master-detail working)

## Files In Progress
- src/pages/Login.tsx (Google OAuth setup done, UI not built yet)

## Up Next
1. Build real Login page UI with Google OAuth button
2. Wire up Google OAuth using @react-oauth/google package
3. Build navigation sidebar
4. Style all pages (cards, colors, layout)
5. Backend (API, database, real auth enforcement)

## Google OAuth Setup
- Google Cloud project: Orbis
- OAuth consent screen: configured
- Client ID: stored in .env as VITE_GOOGLE_CLIENT_ID
- Authorized JavaScript origins: http://localhost:5173
- Authorized redirect URIs: http://localhost:5173/login
- JSON credentials: downloaded and stored safely outside project folder

## Name Research
Checked and cleared: Orbis (no conflicts in education software space)
Latin meaning: "world / circle" — everything in your school's world, in one place

## Laws & Compliance Notes
- FERPA (US): protects student education records
- COPPA: applies if any students are under 13
- GDPR: applies if any schools are in Europe
- Frontend permission checks are UX only — backend must enforce independently
- Audit logging required before connecting real student data
- Never commit .env files or OAuth credentials to GitHub
