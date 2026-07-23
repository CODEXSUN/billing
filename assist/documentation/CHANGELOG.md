# CODEXSUN Billing Changelog

## Version State

Current version: 1.0.45
Release tag: v-1.0.45
Changelog label: v 1.0.45

## v-1.0.45

### [v 1.0.45] 2026-07-23 11:11 am - Align Framework 1.0.44 dependency

#### Database Changes

- Database update: No.

#### App Codebase Changes

- Refreshed the repository lockfile so Billing resolves the verified `@codexsun/framework`
  `1.0.44` package and its current public contracts.
- Verified Billing API and Web TypeScript compilation and production builds against the updated
  Framework without moving Billing-owned behavior across repository boundaries.
- Bumped repository version to 1.0.45.

## v-1.0.44

### [v 1.0.44] 2026-07-22 11:19 pm - Restore shared bottom-right notifications

#### Database Changes

- Database update: No.

#### App Codebase Changes

- Routed Billing document, settings, and report notifications through the UI-owned Sonner export so
  every module publishes to the toaster mounted by the composing application.
- Removed Billing's direct Sonner dependency while preserving module-owned notification messages.
- Bumped repository version to 1.0.44.

## v-1.0.43

### [v 1.0.43] 2026-07-22 8:52 pm - Finalize Billing lifecycle and repository ownership

#### Database Changes

- Database update: No.
- Extended the tenant connection idle lifetime without changing tables, migrations, seeds, or stored data.

#### App Codebase Changes

- Added the public Billing application metadata contract used by Platform app composition.
- Kept Billing migrations and seeds repository-owned while exposing their lifecycle through public exports.
- Added repository-local Assist rules, release tooling, and documentation, and bumped the repository to 1.0.43.

## v-1.0.42

### [v 1.0.42] 2026-07-22 - Establish Billing repository documentation

#### Database Changes

- Database update: No.
- Documented the repository-owned migration and seed lifecycle without moving persistence behavior across repositories.

#### App Codebase Changes

- Added repository-local Assist discovery, ownership, structure, environment, version, and Git workflow guidance.
- Added standalone version validation, version bump, and `github:now` tooling.
