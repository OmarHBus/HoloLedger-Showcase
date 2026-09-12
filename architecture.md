
# Architecture

## Overview

HoloLedger follows a modern web application architecture based on Next.js, TypeScript and Supabase.

The application separates presentation, business logic and persistence responsibilities while keeping the overall architecture simple enough for a small SaaS-style product.

---

## High-Level Architecture

```text
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
