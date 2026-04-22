# Workspace

## Overview

Craviers Cafe — a full-stack cafe ordering and feedback website. Customers can browse the menu, add items to a cart, place orders, and submit feedback.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite (artifacts/craviers-cafe)
- **API framework**: Express 5 (artifacts/api-server)
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (`zod/v4`), `drizzle-zod`
- **API codegen**: Orval (from OpenAPI spec)
- **Build**: esbuild (CJS bundle)
- **State management**: Zustand (cart state)

## Features

- Home page with hero, popular items, and testimonials
- Full menu with category filtering and AI-generated food images
- Cart management and order placement form
- Customer feedback with star ratings, rating breakdown, and recent reviews

## Database Tables

- `menu_items` — cafe menu items with name, description, price, category, availability, popularity
- `orders` — customer orders with items JSON, total, status, and customer info
- `feedback` — customer feedback with rating (1-5), category, and comment

## Key Commands

- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- `pnpm --filter @workspace/api-server run dev` — run API server locally

See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details.
