
# HoloLedger

> A seller-first web application for Pokémon TCG card sellers to calculate profitability, track sales and manage marketplace operations.

HoloLedger is a personal software project designed for Pokémon Trading Card Game sellers operating across marketplaces such as Cardmarket, eBay and Wallapop.

The goal is to provide a simple workspace where sellers can understand the real profitability of each transaction, keep track of their operations and monitor their activity from a single dashboard.

> **Note:** This repository is a public technical showcase.  
> The full application source code is maintained in a private repository.

---

## Overview

Selling collectible cards across different marketplaces involves more than simply comparing buying and selling prices.

Marketplace fees, shipping costs, acquisition prices and other expenses can significantly affect the actual profit of a transaction.

HoloLedger was created to simplify that process by providing tools for:

- Profitability calculations
- Sales and operation tracking
- Marketplace fee management
- Historical transaction data
- User-specific dashboards
- Secure private accounts
- Performance and profitability monitoring

The primary market is currently focused on European Pokémon TCG sellers.

---

## Main Features

### Profitability Calculator

Users can estimate the actual profitability of a card sale by considering:

- Purchase price
- Sale price
- Marketplace fees
- Shipping costs
- Additional expenses
- Net profit
- Profit margin

Marketplace-aware fee presets are supported while still allowing manual fee overrides.

---

### Operation Tracking

Users can store and manage their buying and selling operations.

Each operation can include information such as:

- Marketplace
- Purchase cost
- Sale price
- Fees
- Additional expenses
- Final profit
- Transaction status

Operations are persisted and associated with the authenticated user.

---

### Dashboard

The dashboard provides an overview of stored operations and profitability data.

It is designed to give sellers a quick view of their activity without requiring spreadsheets or manual calculations.

The dashboard is powered by persisted operation data rather than static examples.

---

### Authentication & Private Data

HoloLedger uses Supabase authentication with email and password.

Each user has a private session and can only access their own operation data.

Database access is protected through Row Level Security policies.

---

## Tech Stack

### Frontend

- Next.js
- React
- TypeScript
- Tailwind CSS

### Backend / Data

- Supabase
- PostgreSQL
- Supabase Auth
- Row Level Security

### Development

- Git
- GitHub
- Typed business logic
- Server-side application logic
- Environment-based configuration

---

## Architecture

HoloLedger follows a modern web application architecture:

```text
User
  |
  v
Next.js Application
  |
  +-- Authentication
  |
  +-- Profitability Logic
  |
  +-- Operations Management
  |
  +-- Dashboard
  |
  v
Supabase
  |
  +-- PostgreSQL
  +-- Authentication
  +-- Row Level Security
