

# Functionality

## Overview

HoloLedger is designed to help Pokémon TCG sellers understand the real profitability of their operations and maintain a structured record of marketplace activity.

The application currently focuses on three core areas:

1. Profitability calculation
2. Operation tracking
3. Dashboard monitoring

---

## Profitability Calculator

The profitability calculator allows users to estimate the actual result of a transaction.

The calculation can consider:

- Purchase price
- Sale price
- Marketplace fees
- Additional expenses
- Final profit
- Profit margin

The application supports marketplace-aware fee presets while still allowing users to manually override fees when necessary.

---

## Operation Tracking

Users can store and review their marketplace operations.

Each operation represents a buying or selling transaction and contributes to the historical activity shown in the dashboard.

Operations are persisted in Supabase rather than being stored only in the browser.

---

## Dashboard

The dashboard provides a high-level view of the user's recorded activity.

Its purpose is to allow sellers to quickly understand their operations without manually maintaining spreadsheets.

The dashboard uses persisted operation data rather than static examples.

---

## Authentication

HoloLedger supports user registration and login through Supabase Auth.

Each authenticated user receives a private session.

Authentication allows the application to associate stored operations with the correct user.

---

## User Data Isolation

Operations belong to individual authenticated users.

Database policies are designed so that users cannot access operations owned by another account.

This is implemented using Supabase Row Level Security.

---

## Marketplace Support

The initial marketplace focus includes:

- Cardmarket
- eBay
- Wallapop

Marketplace-specific fee configurations can be incorporated into profitability calculations.

---

## Currency

The current primary currency is EUR.

---

## Current Limitations

The current version does not include:

- Payment processing
- Automatic marketplace synchronization
- Live card pricing
- Full inventory management

These areas may be considered in future versions.
