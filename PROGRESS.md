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

## Files In Progress
- src/types/roles.ts (written in chat, not yet pasted)
- src/context/AuthContext.tsx (written in chat, not yet pasted)
- src/hooks/usePermissions.ts (written in chat, not yet pasted)
- src/hooks/useRoleRoute.ts (written in chat, not yet pasted)
- src/components/ProtectedSection.tsx (written in chat, not yet pasted)

## Pending
- App.tsx (routing)
- Dashboard.tsx
- PeopleRecords.tsx
- AdminReports.tsx
- StudentPortal.tsx

## Name Research
Checked and cleared: Orbis (no conflicts in education software space)
