# APSSI Football ID — Domain & Platform Baseline

| Metadata | Value |
|---|---|
| Document ID | `P0-ARCH-BASELINE-001` |
| Version | 0.1-draft |
| Status | `CONCEPTUAL — OWNER / TECHNICAL REVIEW REQUIRED` |
| Source | PRD v0.1, sections 4–6, 20–25, 33–34, 45–47 |
| Date | 2026-11-15 |

## 1. Purpose

Record the conceptual boundaries and invariants needed to guide later architecture work. This document deliberately does not select a technology stack, provider, deployment topology, or database schema.

## 2. Conceptual domains

| Domain | Responsibility | Key concepts | Dependency / constraint |
|---|---|---|---|
| Identity | Stable identity of a person/player and identity references | Person, Player, Football ID, role | Identity must not be owned by an organization |
| Organization | Represent football entities and their hierarchy | SSB, club, academy, organizer, association, federation | Membership and authority must be scoped |
| Affiliation & Team | Represent time-bound player/team/organization relationships | Affiliation, roster, team membership | Preserve history across transfers |
| Guardian & Consent | Represent guardian relationship and permission decisions | Guardian link, verification, consent, revocation | Foundational before real child data |
| Competition | Manage tournament/league lifecycle | Competition, category, registration, roster, draw, schedule | Strategic wedge candidate; MVP scope open |
| Match & Officials | Represent match operations and officiating | Match, venue, referee, events, score, report | Match records need provenance and correction controls |
| Training & Attendance | Represent organized development activity | Session, attendance, plan | MVP inclusion to be decided |
| Player Development | Record longitudinal assessments | Assessment, dimensions, reports | Youth development is broader than goals/assists |
| Finance | Represent fees, invoices, and payment records | Registration fee, invoice, payment | Payment provider and financial controls undecided |
| Governance & Audit | Enforce authority, scope, accountability | RBAC, ABAC, audit event, data classification | Must be server/trusted-data enforced in implementation |
| Integration & API | Support external interoperability | API resources, credentials, integration contracts | API-first direction; no contract selected |
| Intelligence | Aggregate data and future AI capabilities | Analytics, dashboard, AI | Depends on quality, permissions, and sufficient trusted data |

## 3. Core conceptual relationships

```text
PERSON
  ├── has one canonical person identity
  ├── may hold multiple ROLES
  ├── may have a GUARDIAN relationship to a PLAYER
  └── may have scoped ORGANIZATION MEMBERSHIPS

PLAYER
  ├── has a stable FOOTBALL ID
  ├── has time-bound ORGANIZATION / TEAM AFFILIATIONS
  ├── participates in TRAINING and COMPETITIONS
  ├── appears in MATCH and DEVELOPMENT HISTORY
  └── has privacy / consent constraints where applicable

ORGANIZATION
  ├── has MEMBERS
  ├── manages TEAMS and ROSTERS
  ├── may be affiliated with PLAYERS for a period
  └── may participate in COMPETITIONS

COMPETITION
  ├── has CATEGORIES and REGISTRATIONS
  ├── has TEAMS / ROSTERS
  ├── schedules MATCHES at VENUES
  └── assigns OFFICIALS

ACCESS DECISION
  ├── actor identity
  ├── trusted role / membership
  ├── resource and relationship
  ├── organization / team / region scope
  ├── purpose and consent where applicable
  └── decision + audit evidence
```

This is a conceptual relationship map only. It is not an ERD, physical schema, or approved cardinality specification.

## 4. Architecture principles

1. **Player-centred identity:** canonical player identity persists independently from SSB, team, competition, or academy membership.
2. **Relationship history:** affiliations are explicit, time-aware relationships; avoid destructive replacement of history.
3. **Person-role separation:** person identity and role assignments are separate concepts.
4. **Organization-scoped authority:** organization membership and role assignment do not grant global access.
5. **Child-safety by design:** guardian verification, consent, revocation, minimization, audit, and restricted sharing are foundational.
6. **RBAC + ABAC:** access decisions consider role and contextual attributes such as relationship, resource, scope, purpose, and consent.
7. **Data classification:** identity, football, performance, sensitive, and analytics data require differentiated access.
8. **API interoperability:** design stable contracts at domain boundaries when integration is in scope.
9. **Avoid premature distributed complexity:** the PRD recommends avoiding premature microservices.
10. **Evidence before production claims:** a model, UI, mock, or documentation entry is not proof of secure persistence or production readiness.

## 5. Security and privacy design constraints

- Client-supplied role, organization ID, team ID, or player ID must not be treated as proof of authority.
- A parent/guardian must only access a child through a verified and active relationship and the approved policy.
- A coach's access must be limited to assigned teams/players and permitted data categories.
- An SSB administrator's access must be limited to the organization's legitimate scope.
- Scout access must be conditional on applicable consent and data-sharing scope.
- Association/federation access must respect geographic/organizational authority and aggregation policy.
- Sensitive documents and medical-related data require stricter purpose-limited controls.
- Consent changes/revocation must be auditable and reflected in downstream access paths.
- Analytics must not re-identify children through supposedly aggregate views.

These are requirements-level constraints. Detailed policy, legal basis, evidence standards, retention, and technical enforcement remain open work.

## 6. Technology decisions deliberately deferred

The PRD names Flutter/React Native, Next.js/React, REST, PostgreSQL, Redis, object storage, phone/email/OTP/OAuth, and RBAC as suggestions. No option is approved by this document.

Before selecting technology, Phase 0 should document:
- client platform and delivery priorities;
- team skills and operating constraints;
- backend and database ownership;
- hosting and regional requirements;
- identity/authentication needs;
- authorization and tenant-isolation model;
- media/document storage needs;
- integration requirements;
- backup, recovery, observability, and cost;
- migration and vendor-exit strategy.

## 7. Architecture decisions requiring owner disposition

See `docs/decisions/OWNER-DECISION-REGISTER.md`, especially MVP boundary, child-data launch posture, platform surfaces, provider ownership, and product identity/brand.
