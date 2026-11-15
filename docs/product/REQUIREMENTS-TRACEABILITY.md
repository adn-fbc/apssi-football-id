# Requirements Traceability — APSSI Football ID

| Metadata | Value |
|---|---|
| Document ID | `P0-TRACE-001` |
| Version | 0.1-draft |
| Status | `DRAFT — OWNER REVIEW REQUIRED` |
| Source | PRD v0.1, sections 1–47 |
| Baseline date | 2026-11-15 |

## Status legend

- `SOURCE`: directly stated in the supplied PRD.
- `INTERPRETED`: structured interpretation of multiple PRD statements; owner review required.
- `OPEN`: cannot be finalized without owner decision or policy/technical analysis.
- `FUTURE`: explicitly positioned as later-stage or outside the immediate MVP direction.

## Traceability matrix

| Requirement ID | PRD source | Requirement / intent | Domain | Initial priority | Status / note |
|---|---:|---|---|---|---|
| `REQ-VIS-001` | 1–2 | Connect the grassroots/youth football journey through a Football Identity & Data Layer | Product vision | P0 | SOURCE |
| `REQ-PROB-001` | 3 | Reduce fragmentation and repeated registration; preserve player history across organizations and activities | Product problem | P0 | SOURCE |
| `REQ-ID-001` | 4–6 | Provide persistent digital identity for people, organizations, and activities | Identity | P0 | SOURCE |
| `REQ-ID-002` | 5–6 | Player Football ID remains independent of SSB ownership/affiliation | Identity | P0 | SOURCE; core invariant |
| `REQ-ID-003` | 6 | Preserve affiliation history when player changes organization | Identity / affiliation | P0 | SOURCE |
| `REQ-ROLE-001` | 7–8 | Support ecosystem stakeholders across player, family, organizations, professionals, competitions, associations, federation, and commercial participants | Ecosystem | P1 | SOURCE; MVP boundary open |
| `REQ-ROLE-002` | 9–13, 21–22 | Model a person with multiple roles and organization memberships | Identity / access | P0 | SOURCE |
| `REQ-PLY-001` | 9 | Player profile, team, schedule, match, statistics, achievements, development, media, certificates, history | Player | OPEN | Full capability list exceeds MVP; select subset |
| `REQ-PAR-001` | 10 | Parent/guardian access to child profile, registration, payments, schedule, notifications, communication | Parent | OPEN | MVP inclusion and guardian model need owner/policy decision |
| `REQ-ORG-001` | 11 | Organization management for players, rosters, teams, training, competition, finance, development, and staff | Organization | P1 | MVP subset open |
| `REQ-COA-001` | 12 | Coach identity/profile, credentials, teams, training, attendance, assessment, match and development reports | Coach | P1/FUTURE | Detailed coach platform not necessarily MVP |
| `REQ-REF-001` | 13 | Referee profile, credentials, assignments, match reports and events | Officials | FUTURE | PRD ecosystem scope |
| `REQ-CMP-001` | 14 | Create and manage tournaments/competitions, categories, registration, rosters, schedule, venues, officials, results, standings, statistics, certificates | Competition | P0/P1 | Strong strategic wedge; MVP scope requires owner approval |
| `REQ-MAT-001` | 15 | Model match with competition, venue, date, officials, teams, players, score, events, statistics, report | Match | P1 | Detailed lifecycle and correction model open |
| `REQ-DEV-001` | 16–17 | Support periodic multi-dimensional youth development assessment and longitudinal progress | Development | FUTURE/P1 | Must avoid reducing development to goals/assists |
| `REQ-SCT-001` | 18 | Support scout discovery using football criteria while restricting access to consent-authorized player data | Scouting / privacy | FUTURE | No unrestricted child discovery |
| `REQ-CHD-001` | 19 | Treat guardian relationship, consent, access control, audit, revocation, and minimization as foundational | Child safety | P0 | SOURCE; real child data gate |
| `REQ-DAT-001` | 20–22 | Use a relational conceptual data model for people, roles, organizations, teams, activities, finance, credentials, documents, consent, and audit | Data architecture | P0 | Conceptual only; no schema approval |
| `REQ-ARCH-001` | 23 | Separate identity, organization, people, operations, competition, development, opportunity, governance, intelligence layers | Architecture | P0 | Conceptual boundary |
| `REQ-TECH-001` | 24 | Avoid premature microservices complexity; consider mobile, web, API, relational DB, cache, object storage | Technology | OPEN | Suggestions only; stack not selected |
| `REQ-API-001` | 25 | Design API-first interoperability for players, organizations, competitions, matches, and development | Integration | P1/FUTURE | API contract not defined |
| `REQ-MVP-001` | 26 | MVP formulation includes Player + Parent + SSB + Competition and listed core functions | MVP | OPEN | Conflicts/overlaps with strategic wedge formulation |
| `REQ-MET-001` | 27 | Use Verified Active Players as proposed North Star Metric | Measurement | OPEN | Define verified, active, time window, deduplication |
| `REQ-BIZ-001` | 28–30 | Evaluate SSB SaaS, tournament SaaS, payments, premium parent, scouting, enterprise; marketplace later | Business | OPEN/FUTURE | Hypotheses; prices require validation |
| `REQ-NET-001` | 30–31 | Build network effects and longitudinal football graph/history | Ecosystem data | P1/FUTURE | Depends on trusted identity and permission model |
| `REQ-ROAD-001` | 32 | Use a staged three-year discovery/build/pilot/scale roadmap | Growth | OPEN | Targets are planning assumptions |
| `REQ-GOV-001` | 33 | Combine RBAC and ABAC with scoped access for parent, coach, SSB admin, scout, association, federation | Governance | P0 | SOURCE; policy matrix required |
| `REQ-SEC-001` | 34 | Classify identity, football, performance, sensitive, and analytics data with stronger controls for more sensitive data | Privacy / security | P0 | SOURCE; exact classification open |
| `REQ-AI-001` | 35–36 | Consider development, coach, scout, parent AI and national dashboards after sufficient trusted data exists | Intelligence | FUTURE | Not MVP |
| `REQ-GTM-001` | 37–38 | Consider South Sulawesi beachhead and founding SSB / competition partnerships | Go-to-market | OPEN | Owner/business validation |
| `REQ-WEDGE-001` | 39–40 | Prioritize Tournament/Competition as a strategic entry point connecting SSB, players, coaches, referees, venues | MVP strategy | OPEN | Reconcile with MVP formulation |
| `REQ-PORT-001` | 41–42 | Organize product portfolio around Football ID, Football OS, Competition, Network, Intelligence | Product portfolio | OPEN | PRD says four then lists five products |
| `REQ-BRAND-001` | 43–44 | Keep brand/name provisional until validation; use proposed positioning and tagline as working direction | Brand | OPEN | Working repo name is not final public brand |
| `REQ-PRINC-001` | 45–46 | Maintain one connected identity across people, organizations, activities; player-centred journey and permissions | Product principle | P0 | SOURCE |
| `REQ-P0-PLAN-001` | 47 | Complete vision, ecosystem, identity, roles, product, data, UX, business, technology, and growth workstreams before coding | Phase 0 | P0 | SOURCE; Phase 0 completion criteria to formalize |

## Cross-cutting acceptance constraints

These are interpretations needed to make the source requirements testable; they are not detailed implementation specifications yet.

| Constraint ID | Derived from | Acceptance intent |
|---|---|---|
| `AC-ID-001` | REQ-ID-002/003 | Organization changes do not replace a player's canonical identity or erase historical affiliations |
| `AC-ROLE-001` | REQ-ROLE-002 | One person can hold multiple roles without duplicate person identity |
| `AC-CHD-001` | REQ-CHD-001 / REQ-SCT-001 | No scout or other external role receives child/player access merely by role; applicable guardian/consent and scope checks are required |
| `AC-GOV-001` | REQ-GOV-001 | Role alone is insufficient where organization, team, region, purpose, or consent scope is required |
| `AC-DATA-001` | REQ-SEC-001 | Sensitive data is not exposed through broad role-based access or aggregate endpoints without appropriate controls |
| `AC-MVP-001` | REQ-MVP-001 / REQ-WEDGE-001 | MVP features cannot be finalized until the owner resolves the scope decision |
| `AC-TECH-001` | REQ-TECH-001 | No technology/provider/schema is treated as selected solely because it appears as a suggestion in the PRD |

## Traceability maintenance rules

1. Keep requirement IDs stable once approved.
2. Every implementation story must reference one or more requirement IDs.
3. A requirement must not be marked `DONE` because a screen or mock exists; acceptance evidence must be linked.
4. Changes to requirement meaning require a decision record and traceability update.
5. Future requirements remain visible but must not leak into MVP implementation scope.
