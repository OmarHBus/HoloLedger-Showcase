
# Data Model

## Overview

HoloLedger currently uses Supabase PostgreSQL for persistence.

The central persisted entity is the operation.

Authentication identities are managed by Supabase Auth.

This document intentionally describes the public logical model rather than exposing the full private database implementation.

---

## Main Entities

### User

Users are managed by Supabase Auth.

A user represents an authenticated HoloLedger account.

Conceptually:

`text
User
- unique identity
- email
- authentication session

Application data is associated with this identity.

Operation

An operation represents a marketplace transaction tracked by the user.

Conceptually, an operation can contain:

Operation
- owner
- marketplace
- purchase information
- sale information
- fees
- additional costs
- profitability result
- status
- timestamps

Exact implementation details are kept in the private source repository.

Relationship

The core relationship is:

User
 |
 | owns
 v
Operation

One user may own multiple operations.

Each operation belongs to a single authenticated user.

Ownership Model

Ownership is a key part of both the data model and the security model.

Conceptually:

users
  1
  |
  |
  N
operations

The authenticated user's identifier is used to enforce access policies.

Row Level Security

Row Level Security policies restrict database operations based on ownership.

The intended rule is:

authenticated_user_id == operation.owner_id

This applies conceptually to:

Reading operations
Creating operations
Updating operations
Deleting operations
Future Data Model

Potential future entities may include:

InventoryItem
Card
Marketplace
Expense
PriceHistory
Collection
Report
