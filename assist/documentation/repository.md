# CODEXSUN Billing Repository Contract

## Nature

Tenant-owned billing and financial-document application with independently owned API and web workspaces.

## Ownership

Billing settings, sales, purchase, export sales, quotations, payments, receipts, dashboard snapshots, Billing permissions, API contracts, and Billing UI.

Excluded ownership: Platform tenancy/authentication, Core master records, Mail delivery internals, and generic UI primitives.

## Current Structure

- `api/src/modules/`
- `api/src/database/billing-database.ts`
- `web/src/modules/`
- `web/src/shared/`

## Migration Contract

Tenant database only. Order: Settings → Sales → Purchase → Export Sales → Quotation → Payment → Receipt → Dashboard. `api/src/database/billing-database.ts` may order and record these migrations but each leaf owns its SQL.

## Seed Contract

Order: Billing permissions → Settings/default company resolution → Sales → Purchase → Export Sales → Quotation → Payment → Receipt → Dashboard. Every seed remains repeatable and in its owner.

## Environment Contract

No repository-local `.env` is required. Runtime values are loaded from the composing `codexsun/.env`: Platform URL, database connection, JWT secret, and server-only GSP credentials.

## Composition Contract

This repository exposes intentional public package contracts. The `codexsun` repository is the executable composition root. It may install, register, order, build, and invoke exported lifecycle functions; it must not copy this repository's business implementation.

`api/src/application.ts` owns Billing's public application-bundle manifest. Super Admin App Operations
may display this metadata and Platform may compose its declared API and Web components.

## Required Checks

- `npm run format:check`
- `npm run lint`
- `npm run typecheck`
- `npm run build`
- `npm run check:versions`
- `npm run github:now -- --dry-run`

Run composed boundary, database, and E2E checks from the sibling `codexsun` repository when the change affects runtime integration.
