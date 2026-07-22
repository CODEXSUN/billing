# CODEXSUN Billing Agent Guide

## Purpose

Tenant-owned billing and financial-document application with independently owned API and web workspaces.

## Required Reading

Before changing code, read this guide, `assist/governance/rules.md`, `assist/documentation/repository.md`, and the complete owning module. When the sibling workspace exists, consult `../codexsun/assist` for product-wide architecture, database, UI, deployment, and API guidance.

## Ownership

Owns: Billing settings, sales, purchase, export sales, quotations, payments, receipts, dashboard snapshots, Billing permissions, API contracts, and Billing UI.

Does not own: Platform tenancy/authentication, Core master records, Mail delivery internals, and generic UI primitives.

## Working Rules

- Use npm from this repository root.
- Keep dependency installation, lockfiles, and generated output repository-local; never create nested workspace `node_modules`.
- Preserve unrelated working-tree changes.
- Put business behavior in its owning leaf module. Composition roots may register, order, and invoke public lifecycle contracts only.
- Never import a sibling repository's private source path. Consume only declared package exports, fixed HTTP contracts, or approved events.
- Update `assist/documentation/repository.md` when ownership, structure, migration, seed, or environment behavior changes.
- Preserve historical changelog entries. Use `npm run version:bump` only when a version bump is explicitly requested.

## Verification

Run the repository's applicable format, lint, typecheck, build, test, version, and dependency checks. Database/E2E checks belong to the composed `codexsun` runtime when this repository has database behavior.

Use `npm run github:now -- --dry-run` to review the repository-local commit subject and changed files. The accepted subject format is `#00 - message`.
