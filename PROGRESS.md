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
- Class structure: subjects with grade-level sections, expandable card UI

## Roles & Access
- admin: Admin & Reports, all classes, gradebook, people, assignments
- teacher: Dashboard, My Classes, Gradebook, Assignments, People & Records
- admissions: Admissions page
- parent: Parent Portal (child's grades + class newsletters)
- student: Student Portal (own grades, classes, assignments, attendance)

## School Structure
- K-8 same teacher: Art, Music, Makers, PE
- K-8 split teacher (K-5 / 6-8): Science, French
- K-5 only: Homeroom
- 6-8 only: Academic Workshop, Advisory, Math (Pre-Alg/Algebra/Geometry), English, History, Latin
- 6-8 Electives: Debate, CS (fixed for now, changes yearly)

## Files Completed
- .gitignore
- PROGRESS.md
- .env (Google OAuth Client ID stored here)
- src/types/roles.ts
- src/context/AuthContext.tsx (with localStorage persistence)
- src/hooks/usePermissions.ts (multi-role support)
- src/hooks/useRoleRoute.ts (priority-based role routing)
- src/components/ProtectedSection.tsx
- src/components/Sidebar.tsx (styled - navy theme)
- src/pages/Login.tsx (Google OAuth + styled)
- src/pages/Classes.tsx (mock data, expandable subject cards)
- src/pages/ClassHomepage.tsx (mock data, tabbed: home/resources/grades)
- src/pages/Gradebook.tsx (mock data, editable grade grid)
- src/pages/Assignments.tsx (mock data, create new assignments)
- src/pages/Dashboard.tsx (logic complete, styling pending)
- src/pages/AdminReports.tsx (mock data, styling pending)
- src/pages/StudentPortal.tsx (mock data, styling pending)
- src/pages/PeopleRecords.tsx (mock data, master-detail, styling pending)

## Up Next
1. Build Parent Portal page (child grades + newsletters)
2. Build Admissions page (content TBD)
3. Add Tuition feature to Admin & Reports (content TBD)
4. Style Dashboard, StudentPortal, PeopleRecords, AdminReports
5. Backend: Supabase setup
6. Replace all mock data with real Supabase data
7. Audit logging (FERPA compliance)

## Planned Features
- Assignment submission (future)
- Role priority customizable by admin (future)
- Additional languages beyond French (future)
- Electives update yearly via admin panel (future)

## Google OAuth Setup
- Google Cloud project: Orbis
- OAuth consent screen: configured
- Client ID: stored in .env as VITE_GOOGLE_CLIENT_ID
- Authorized JavaScript origins: http://localhost:5173
- Authorized redirect URIs: http://localhost:5173/login
- JSON credentials: downloaded safely outside project folder

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
- Role priority order configurable by admins (future)

## Styling
- Framework: Tailwind CSS
- Primary: Navy #1e3a5f
- Accent: Blue #2563eb
- Background: Light gray #f8fafc
- Card: White #ffffff
- Text: Dark gray #1e293b
- Border: Light gray #e2e8f0
