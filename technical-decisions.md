
# Technical Decisions

## Overview

This document describes some of the main technology and architecture decisions behind HoloLedger.

---

## Why Next.js?

Next.js was selected because it provides a modern React-based application framework while also supporting server-side functionality.

It allows the project to keep frontend and server-side application logic within the same codebase.

Benefits include:

- React ecosystem
- File-based routing
- Server-side capabilities
- API integration
- Good TypeScript support
- Straightforward deployment

---

## Why TypeScript?

HoloLedger contains business logic related to operations, fees and profitability.

TypeScript helps define clear data structures for this logic.

It is used to improve:

- Type safety
- Maintainability
- Developer experience
- Refactoring
- Data consistency

Typed models are especially useful for operation and profitability flows.

---

## Why Supabase?

Supabase provides several services required by HoloLedger within one platform:

- PostgreSQL
- Authentication
- Session management
- Row Level Security
- JavaScript / TypeScript integration

This reduces the need to build a complete custom backend while still providing a relational database and database-level security controls.

---

## Why PostgreSQL?

Marketplace operations are structured and relational.

A relational database is therefore a natural fit for storing:

- Users
- Operations
- Financial values
- Marketplace information
- Future inventory relationships

PostgreSQL also provides a strong foundation for future analytics and reporting.

---

## Why Row Level Security?

Frontend authorization alone is not sufficient for protecting user-owned data.

Row Level Security moves part of the authorization logic into the database itself.

This provides defense in depth and reduces the risk of accidentally exposing another user's operations.

---

## Why Separate Business Logic?

Profit calculations and operation processing should not depend directly on UI components.

Separating business logic makes the application:

- Easier to test
- Easier to maintain
- Easier to reuse
- Easier to modify

This is particularly important for financial calculations where consistency matters.

---

## Why Keep the Source Private?

The complete project is maintained in a private repository.

The public showcase is intended to demonstrate:

- Architecture
- Technical decisions
- Security awareness
- Product functionality
- Development experience

without publishing the complete implementation.

This provides recruiters and technical reviewers with enough information to evaluate the project while keeping the source code private.
