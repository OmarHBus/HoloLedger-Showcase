
# Security Design

## Overview

Security is treated as part of the application design rather than as an additional feature added after development.

HoloLedger handles authenticated users and private operation data, so access control and data isolation are important parts of the architecture.

---

## Authentication

Authentication is implemented using Supabase Auth.

The current authentication flow supports email and password authentication.

User sessions are handled through Supabase rather than through a custom password storage implementation.

---

## Authorization

Authentication alone does not determine whether a user should be able to access a specific record.

HoloLedger therefore combines authenticated sessions with database-level authorization controls.

---

## Row Level Security

Supabase Row Level Security is used to protect operation data.

The objective is:

``text
User A -> User A operations
User B -> User B operations

User A -X-> User B operations

Access policies enforce ownership at the database layer.

This provides an additional security boundary beyond frontend filtering.

Data Ownership

Each stored operation is associated with an authenticated user.

Application logic and database policies use this ownership relationship when reading or modifying data.

Secrets and Configuration

Environment-specific values are stored using environment variables rather than hard-coded directly into application logic.

Examples include Supabase configuration values.

Sensitive credentials should never be committed to the public repository.

Application Security Considerations

Security considerations include:

Authentication
Authorization
Row Level Security
User data isolation
Input validation
Server-side handling of sensitive operations
Environment variable management
Secure database access patterns
Separation of frontend and backend responsibilities
Secure Development Perspective

The project is also used as a practical environment for applying concepts from cybersecurity and secure software development.

Relevant areas include:

Secure SDLC
Access control
Authentication
Authorization
API security
Data exposure risks
Input validation
Least privilege
Secure configuration
Threat Considerations

Examples of threats considered during development include:

Unauthorized access to another user's data
Incorrect authorization checks
Exposure of sensitive configuration
Manipulation of operation data
Invalid or malicious input
Excessive trust in frontend validation
Future Security Improvements

Potential future improvements include:

More extensive server-side validation
Security logging
Session monitoring
Rate limiting
Audit trails
Security headers
Automated dependency scanning
SAST / SCA integration
Additional security testing
