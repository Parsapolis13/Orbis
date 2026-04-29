# Orbis - Progress Tracker

## App Overview
A streamlined K-12 school management platform — a modern alternative to Blackbaud.
Built with React + TypeScript + Vite.

## Tech Stack
- Frontend: React, TypeScript, Vite
- Styling: Tailwind CSS
- Package manager: npm
- Editor: VSCode
- Auth: Google OAuth (@react-oauth/google + jwt-decode)
- Auth persistence: localStorage

## Design Decisions
- Clean but explicit UI (in between modern SaaS and traditional)
- Master-detail pattern: click a person → side panel opens
- Sidebar navigation: always visible except on Login screen
- Frontend permission checks are for UX only — backend must enforce separately
- Auth state persisted to localStorage so login survives page refresh
- Multi-role support: users can have more than one role simultaneously
- Role priority order: admin > teacher > admissions > parent > student
- Color scheme: Navy blue (#1e3a5f) primary, white cards, light gray backgrounds

## Roles & Access
- admin: Admin & Reports (enrollment, scheduling, reports, tuition)
- teacher: Dashboard, People & Records
- admissions: Admissions page
- parent: Parent Portal (read-only view of their child's data)
- student: Student Portal (own grades, classes, assignments, attendance)

## Files Completed
- .gitignore
- PROGRESS.md
- .env (Google OAuth Client ID stored here)
- src/types/roles.ts
- src/context/AuthContext.tsx (with localStorage persistence)
- src/hooks/usePermissions.ts (multi-role support)
- src/hooks/useRoleRoute.ts (priority-based role routing)
- src/components/ProtectedSection.tsx
- src/components/Sidebar.tsx (styled with Tailwind - navy theme)
- src/pages/Login.tsx (Google OAuth + styled with Tailwind)
- src/pages/Dashboard.tsx (logic complete, styling pending)
- src/pages/AdminReports.tsx (mock data, styling pending)
- src/pages/StudentPortal.tsx (mock data, styling pending)
- src/pages/PeopleRecords.tsx (mock data, master-detail, styling pending)

## Up Next
1. Style Dashboard.tsx
2. Style StudentPortal.tsx
3. Style PeopleRecords.tsx
4. Style AdminReports.tsx
5. Build Parent Portal page (content TBD)
6. Build Admissions page (content TBD)
7. Add Tuition feature to Admin & Reports (content TBD)
8. Backend: Supabase setup (database, real auth, role assignment)
9. Replace all mock data with real Supabase data
10. Audit logging (required before connecting real student data)

## Planned Pages (content TBD)
- Parent Portal (role: parent — read-only view of child's data)
- Admissions page (role: admissions already created)
- Tuition feature (inside Admin & Reports or separate page)

## Google OAuth Setup
- Google Cloud project: Orbis
- OAuth consent screen: configured
- Client ID: stored in .env as VITE_GOOGLE_CLIENT_ID
- Authorized JavaScript origins: http://localhost:5173
- Authorized redirect URIs: http://localhost:5173/login
- JSON credentials: downloaded and stored safely outside project folder

## Name
- Orbis (Latin: "world / circle")
- Everything in your school's world, in one place
- No conflicts found in education software space

## Laws & Compliance Notes
- FERPA (US): protects student education records
- COPPA: applies if any students are under 13
- GDPR: applies if any schools are in Europe
- SOPIPA: California student privacy law
- Frontend permission checks are UX only — backend must enforce independently
- Audit logging required before connecting real student data
- Never commit .env files or OAuth credentials to GitHub

## Backend Plan (Supabase - not started)
- Store users and their roles in database
- Role assignment after Google login
- Replace mock data with real database tables
- Enforce permissions server-side
- Audit logging for FERPA compliance
- Role priority order will be configurable by admins (future feature)

## Styling
- Framework: Tailwind CSS
- Primary color: Navy #1e3a5f
- Accent: Blue #2563eb
- Background: Light gray #f8fafc
- Card: White #ffffff
- Text: Dark gray #1e293b
- Border: Light gray #e2e8f0
