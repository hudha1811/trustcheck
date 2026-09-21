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
