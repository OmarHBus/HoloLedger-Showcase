# Architecture

## Overview

HoloLedger follows a modern web application architecture based on Next.js, TypeScript and Supabase.

The application separates presentation, business logic and persistence responsibilities while keeping the overall architecture simple enough for a small SaaS-style product.

---

## High-Level Architecture

``text
User
 |
 v
Next.js Application
 |
 +-- Authentication
 |
 +-- Dashboard
 |
 +-- Profitability Calculator
 |
 +-- Operation Management
 |
 +-- Business Logic
 |
 v
Supabase
 |
 +-- Authentication
 +-- PostgreSQL
 +-- Row Level Security
Frontend Layer

The frontend is built with:

Next.js
React
TypeScript
Tailwind CSS

The frontend is responsible for:

User interaction
Dashboard presentation
Profitability calculations
Operation management
Authentication flows
Form validation
Navigation

TypeScript is used throughout the application to improve maintainability and reduce type-related runtime errors.

Application Logic

Business logic is separated from presentation components where possible.

Examples include:

Profit calculations
Marketplace fee handling
Operation processing
Dashboard aggregation
Data validation

This approach makes the application easier to test, maintain and extend.

Data Layer

Supabase provides:

PostgreSQL database
User authentication
Session management
Row Level Security

Operations are persisted in the database and associated with authenticated users.

The application is designed so that users only access data that belongs to their own account.

Authentication Flow

At a high level:

User
 |
 v
Sign In / Sign Up
 |
 v
Supabase Auth
 |
 v
Authenticated Session
 |
 v
Application
 |
 v
User-owned operations

Authentication is currently based on email and password.

Main Application Routes

The current application includes:

/
    Dashboard

/calculator
    Profitability calculator

/operations
    Operation tracking

/settings
    Project and user settings

/sign-in
    Authentication

/sign-up
    Registration
Scalability Considerations

The current architecture is intentionally simple, but it can be extended with:

Inventory management
Marketplace integrations
Historical analytics
External pricing APIs
Reporting services
Background jobs
Notifications
Advanced role management

The separation between UI, business logic and persistence makes these future additions easier to introduce.


