# APSSI Football ID — Product Requirements Baseline

| Metadata | Value |
|---|---|
| Document ID | `P0-PROD-BASELINE-001` |
| Version | 0.1-draft |
| Status | `DRAFT — OWNER REVIEW REQUIRED` |
| Source | `prd.txt`, “BLUEPRINT — YOUTH FOOTBALL ECOSYSTEM PLATFORM”, Version 0.1 — Indonesia |
| Baseline date | 2026-11-15 |
| Project | APSSI Football ID |
| Repository | `adn-fbc/apssi-football-id` |

## 1. Purpose and authority

This document structures the product intent and requirements contained in the supplied PRD. It is a baseline for review and traceability, not an implementation authorization.

**Source rule:** requirements below are derived from the supplied PRD. Interpretations and proposed clarifications are explicitly labelled. Where the PRD contains alternative or conflicting priorities, this document preserves the ambiguity and routes it to the Owner Decision Register.

## 2. Product vision

Build digital infrastructure connecting the football journey of children and grassroots players, from early participation through development and future opportunities. The platform is intended to connect people, organizations, activities, competitions, and football history through a Football Identity & Data Layer.

The product is broader than an SSB administration application. Its intended ecosystem includes players, parents/guardians, SSBs, clubs, academies, coaches, referees, competition organizers, scouts, associations, federations, and commercial participants.

## 3. Positioning

The PRD proposes:

- Category: Youth Football Ecosystem Platform.
- Positioning: “The Digital Infrastructure for Grassroots Football”.
- Indonesia-facing proposition: one digital ecosystem to build, manage, develop, and connect grassroots football.
- Player-facing line: “Every Player Has a Football Journey.”

Brand/name remains unfinalized in the source PRD. “APSSI Football ID” is used here as the project/repository working name, not as proof of final public brand approval.

## 4. Problem statement

The PRD describes fragmented player and football activity information across parent messaging, spreadsheets, coach notes, tournament forms, certificates, personal videos, and match administration records. This fragmentation can cause repeated registration, loss of history when changing organizations, limited player information during selection, and difficulty connecting activity records across the ecosystem.

## 5. Core product proposition

The platform is intended to provide connected identity records for people and organizations, and connected records for football activities such as training, matches, tournaments, leagues, trials, selections, and certifications.

The core product concept is a persistent Football Identity & Data Layer, with products and workflows built around it.

## 6. Foundational product principles

### 6.1 Player-centred identity

The PRD states: **“The player owns the journey.”** The platform is intended to act as trusted infrastructure for identity, permissions, history, and connectivity.

### 6.2 Identity is distinct from affiliation

A player identity must not be owned by an SSB or other organization. An organization has a relationship/affiliation with a player over a period; changing organization must not erase the player's identity or prior history.

### 6.3 One person, multiple roles

One person may hold multiple roles (for example, parent, coach, scout) and should not need separate person identities solely because they hold multiple roles.

### 6.4 Child safety and privacy are foundational

The PRD identifies guardian relationships, consent, access control, audit trail, revocation, and data minimization as foundational controls because the platform concerns minors. Scout access is not unrestricted; the PRD explicitly conditions player visibility on consent.

### 6.5 Scoped access and governance

The PRD proposes RBAC and ABAC together. Access depends not only on role but also on relationship, organization/team/region scope, and applicable consent or data sensitivity.

### 6.6 API-first interoperability

The platform is intended to support future integration with football organizations and external systems. The PRD illustrates API resources for players, organizations, competitions, matches, and player development. The actual API contract remains to be designed.

### 6.7 Start with a focused release

The PRD advises against launching all roles and ecosystem modules simultaneously. The exact first-release boundary remains an owner decision because the PRD gives more than one priority formulation.

## 7. Stakeholder ecosystem

The PRD identifies the following stakeholder groups:

1. Footballers: youth, amateur, and other players.
2. Family: parents and guardians.
3. Football organizations: SSB, clubs, academies, school football programs.
4. Football professionals: coaches, assistant coaches, specialist coaches, scouts, referees, match officials.
5. Competition ecosystem: tournament/league organizers, venues, match commissioners.
6. Associations: APSSI and regional/local football organizations.
7. Federation: PSSI, Asprov, Askab, Askot.
8. Commercial ecosystem: sponsors, brands, sports stores, insurance, equipment, and training providers.

The presence of a stakeholder in the ecosystem map does not automatically make its dedicated product workflow part of MVP.

## 8. Product roles and capability domains

### 8.1 Player
Football ID, profile, team, schedule, match history, statistics, achievements, development, video, certificates, and football history. Trial, academy, scholarship, scouting, and marketplace opportunities are described as future capabilities.

### 8.2 Parent / guardian
Child profiles, registration, payment, schedule, notifications, invoices/payment history, and communication with coaches, SSBs, teams, and competitions.

### 8.3 SSB / club / academy
Organization profile, player registration/roster/affiliation, teams, training schedule and attendance, competition registration, finance, player assessment, reports, and staff management.

### 8.4 Coach
Coach profile and identity, licenses/certifications/experience, teams, training, attendance, player assessment, match reports, and development reports. The PRD recommends integration or verification of external licensing data rather than careless duplication.

### 8.5 Referee / match official
Referee profile and identity, license, level, region, experience, assignment, and match report including score, cards, incidents, substitutions, and match status.

### 8.6 Tournament / competition organizer
Competition creation, categories, registration, payment, team rosters, groups/draw, schedule, venue, referee assignment, match, results, standings, statistics, and certificates.

### 8.7 Scout
Player discovery by criteria such as age, region, position, preferred foot, and experience. Access to player information is subject to the privacy and consent layer.

### 8.8 Association / federation
Regional or national governance and dashboards, with scope-limited access. Aggregate/national data access must remain subject to authorization.

### 8.9 Commercial ecosystem
Marketplace and commercial services are described as later-stage capabilities, not MVP priority.

## 9. Core domain concepts

The PRD suggests the following conceptual entities:

- Identity: users, persons, players, parents, guardians, Football IDs.
- Organization: organizations, organization memberships, SSBs, clubs, academies, tournament organizers, associations, federations.
- Team: teams, team membership, player affiliations, coaches and staff.
- Competition: competitions, categories, registered teams, matches, venues, officials.
- Activity: training sessions, attendance, match events, trials, selections, certifications.
- Development: player assessments and development history.
- Finance: registrations, payments, invoices.
- Governance: licenses, certifications, documents, consents, notifications, audit logs.

This is a conceptual inventory, not an approved relational schema or ERD.

## 10. MVP statements found in the PRD

### 10.1 Explicit “MVP 1” formulation (PRD section 26)

The PRD states a focus of **Player + Parent + SSB + Competition**, with the following capabilities:

- Player: Football ID, profile, team, schedule, match history.
- Parent: child profile, registration, payment, schedule, notifications.
- SSB: organization, player management, team, attendance, training, payment.
- Competition: tournament, registration, roster, schedule, match result, standings.

### 10.2 Strategic wedge formulation (PRD sections 39–40)

The PRD later argues that Tournament/Competition is a strong strategic wedge because one event connects SSBs, players, coaches, referees, and venues. It then states that MVP priority should be **Football Identity + Competition + SSB**, rather than an SSB management application.

### 10.3 Baseline treatment

These formulations are related but not identical. This baseline does not silently choose one. The MVP boundary, role entry points, and whether Parent is a first-class MVP workflow or a supporting access surface require explicit owner disposition. See `docs/decisions/OWNER-DECISION-REGISTER.md`.

## 11. Product success and business hypotheses

### 11.1 North Star Metric

The PRD proposes **Verified Active Players**, illustrated as one player with one Football ID, a verified guardian, and active football activity.

This is a proposed metric definition, not an operationally finalized metric. “Verified”, “active”, measurement window, deduplication, and guardian-verification evidence require definition before reporting.

### 11.2 Planning targets

The PRD gives targets of 10,000 verified players in Year 1, 100,000 in Year 2, and 500,000+ in Year 3. It explicitly frames these as planning targets, not market forecasts.

### 11.3 Business model hypotheses

The PRD describes six possible revenue streams: SSB SaaS, tournament SaaS, payment transaction fees, premium parent, scouting subscriptions, and enterprise/federation contracts. Example price points require market validation and are not approved prices.

### 11.4 Growth hypothesis

The PRD proposes a geographic beachhead in South Sulawesi, with Makassar, Gowa, and Maros as an initial sequence before broader regional/national expansion. This remains a go-to-market proposal pending owner confirmation.

## 12. Product hierarchy

The PRD describes:

- Product A — Football ID: identity and football passport.
- Product B — Football OS: SSB/club/academy management.
- Product C — Football Competition: tournament and league infrastructure.
- Product D — Football Network: scouting, development, opportunities.
- Product E — Football Intelligence: analytics and AI.

The PRD earlier refers to a four-product hierarchy and then adds Product E. This is a naming/portfolio presentation difference, not necessarily a functional conflict; final product taxonomy should be confirmed before external publication.

## 13. Future capabilities explicitly not prioritized for MVP

The PRD places marketplace in a later phase and describes scouting, academy opportunities, scholarship, AI, national dashboards, federation integrations, broad API ecosystem, and advanced intelligence as later-stage capabilities. These should not be treated as MVP commitments merely because they appear in the vision.

## 14. Technical direction in source PRD — not an approved stack

The PRD suggests:
- Mobile: Flutter or React Native.
- Web: Next.js or React.
- Backend: REST API.
- Relational system of record: PostgreSQL.
- Supporting components: Redis and object storage.
- Authentication: phone/email, OTP, OAuth.
- Authorization: role-based access.

It also advises against starting with overly complex microservices.

These are candidate directions only. They do not select a framework, cloud provider, database host, authentication vendor, deployment platform, package manager, or architecture implementation. Those decisions require separate technical evaluation and owner approval.

## 15. Data classification proposed by PRD

| Level | Example content | Baseline handling |
|---|---|---|
| Identity | Name, date of birth, ID | Personal data; access must be scoped |
| Football | Position, team, organization | Relationship and purpose scoped |
| Performance | Match, training, assessment | Treat as player-related data; define visibility |
| Sensitive | Documents, medical-related information, guardian data | Strongest restrictions; purpose-limited access |
| Analytics | Aggregate/anonymous data | Verify that aggregation does not expose identifiable records |

The PRD's five levels are conceptual. Exact field classification, retention, lawful basis, access purpose, and deletion/correction rules need policy design and owner/legal review.

## 16. Explicit exclusions from this baseline

This document does not:
- Approve any specific MVP feature or release scope.
- Select a technology stack or provider.
- Approve database schema, ERD, migrations, or storage configuration.
- Approve real child-data collection or production guardian verification.
- Approve consent wording, legal basis, retention periods, or safeguarding policy.
- Approve prices, revenue model, market targets, or final brand.
- Authorize coding, deployment, production launch, or Phase 1.

## 17. Baseline acceptance conditions

This product baseline may be approved when the owner has:
1. Reviewed the product vision and principles.
2. Disposed the MVP scope ambiguity.
3. Confirmed the initial stakeholder/role boundary.
4. Confirmed which future modules are excluded from MVP.
5. Reviewed the child-safety and privacy requirements as mandatory design constraints.
6. Confirmed whether the proposed success metric and South Sulawesi beachhead are accepted planning assumptions.
7. Explicitly approved a version of this baseline.

Approval of this document alone does not authorize implementation. Implementation requires a separate phase authorization.
