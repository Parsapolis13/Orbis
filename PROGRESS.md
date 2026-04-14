# Orbis - Progress Tracker

## App Overview
A streamlined K-12 school management platform — a modern alternative to Blackbaud.
Built with React + TypeScript + Vite.

## Tech Stack
- Frontend: React, TypeScript, Vite
- Package manager: npm
- Editor: VSCode

## Design Decisions
- 4 screens: Dashboard, People & Records, Admin & Reports, Student Portal
- 3 roles: teacher, admin, student
- Style: clean but explicit (in between modern SaaS and traditional)
- Master-detail pattern: click a student → side panel opens
- Frontend permission checks are for UX only — backend must enforce separately

## Roles & Access
- teacher: Dashboard, People & Records, gradebook, attendance
- admin: everything teachers see + Admin & Reports screen
- student: Student Portal only (own grades, classes, assignments, attendance)

## Files Completed
- .gitignore
- PROGRESS.md
- src/types/roles.ts
- src/context/AuthContext.tsx
- src/hooks/usePermissions.ts
- src/hooks/useRoleRoute.ts
- src/components/ProtectedSection.tsx
- src/pages/Dashboard.tsx
- src/pages/PeopleRecords.tsx (placeholder)
- src/pages/AdminReports.tsx (complete - mock data)
- src/pages/StudentPortal.tsx (placeholder)

## Up Next
- Build out StudentPortal.tsx (classes, grades, assignments, attendance)
- Build out PeopleRecords.tsx (student/teacher list with master-detail panel)
- Build out AdminReports.tsx (enrollment, scheduling, reports)
- Build real Login page with proper form
- Add navigation sidebar

## Name Research
Checked and cleared: Orbis (no conflicts in education software space)

## Laws & Compliance Notes
- FERPA (US): protects student education records — must not share without authorization
- COPPA: applies if any students are under 13
- Frontend permission checks are UX only — backend must enforce independently
- Audit logging required before connecting real student data
