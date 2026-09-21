# TrustCheck

> An evidence-based trust and verification platform for evaluating companies and internship opportunities.

## Overview

TrustCheck is a web-based verification platform designed to help students assess the credibility of companies and internship opportunities.

The platform brings together company information, submitted evidence, reports, entity resolution, and trust scoring into a single interface.

Instead of relying on a single indicator, TrustCheck combines multiple pieces of available evidence to produce a structured verification status.

---

## Key Features

### Company Verification

TrustCheck maintains company records containing information such as:

- Company name
- Domain
- Address
- Related company records
- Verification status
- Trust tier

Users can search for companies and view their available verification information.

### Entity Resolution

Different records may refer to the same organization even when their names are slightly different.

TrustCheck uses entity-resolution techniques including:

- Name similarity
- Domain matching
- Address similarity
- Fuzzy matching
- Levenshtein distance
- Confidence-based matching

Potential matches are classified into:

- Match
- Review
- No Match

Ambiguous records can be sent for human review rather than being automatically merged.

### Evidence-Based Scoring

TrustCheck evaluates reports and supporting evidence to calculate a verification tier.

The prototype currently supports:

```text
Tier 0 — Insufficient evidence
Tier 1 — Initial verification
Tier 2 — Requires attention
Tier 3 — Higher-risk classification
The scoring system considers factors such as evidence quantity, verification status, independent reports, duplicate evidence, and reporting time windows.

###Evidence Management

Evidence associated with reports can be viewed and analyzed based on its type and verification status.

Report Moderation

Submitted reports can be reviewed through the moderation interface.

The prototype supports actions such as:

Reviewing reports
Verifying reports
Rejecting reports
Reviewing company disputes
Analytics Dashboard

The analysis dashboard provides an overview of:

Company trust tiers
Evidence distribution
Platform-level risk indicators
Number of canonical companies
User Authentication

The prototype includes:

User registration
Login
Password hashing
Token-based authentication
User profile information
Optional profile avatar
System Architecture
                    ┌─────────────────────┐
                    │      Student        │
                    │      / Reviewer     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   TrustCheck UI     │
                    │ HTML / CSS / JS     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Express Server    │
                    │      REST API       │
                    └──────────┬──────────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
              ▼                ▼                ▼
        ┌──────────┐     ┌────────────┐   ┌───────────┐
        │ Company  │     │   Reports  │   │ Evidence  │
        │  Routes  │     │   Routes   │   │  Routes   │
        └────┬─────┘     └─────┬──────┘   └─────┬─────┘
             │                 │                │
             └─────────────────┼────────────────┘
                               ▼
                    ┌─────────────────────┐
                    │   Processing Layer  │
                    │                     │
                    │ Entity Resolution   │
                    │ Trust Scoring       │
                    │ Authentication      │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │    JSON Storage     │
                    │                     │
                    │ companies.json      │
                    │ reports.json        │
                    │ users.json          │
                    └─────────────────────┘
Technology Stack
Frontend
HTML5
CSS3
JavaScript
Tabler Icons
Responsive web interface
Browser Local Storage
Web Camera API for profile avatar capture
Backend
Node.js
Express.js
REST APIs
CORS
Data Storage

The current prototype uses JSON files for persistence:

data/companies.json
data/reports.json
data/users.json

The user database is intentionally excluded from the public repository.

Algorithms

The project includes:

Levenshtein distance
Fuzzy string matching
Domain comparison
Address similarity
Entity resolution
Evidence-based scoring
Duplicate detection
Trust-tier calculation
