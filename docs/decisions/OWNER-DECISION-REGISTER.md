# APSSI Football ID — Owner Decision Register

| Metadata | Value |
|---|---|
| Document ID | `P0-ODR-001` |
| Version | 0.1 |
| Status | `OPEN ITEMS — NO DECISIONS IMPLIED` |
| Date | 2026-11-15 |

## Decision status rules

- `OPEN`: no owner decision recorded.
- `PROPOSED`: an option is suggested but not approved.
- `APPROVED`: owner explicitly approves the exact decision.
- `REJECTED`: owner explicitly rejects the proposal.
- `SUPERSEDED`: replaced by a later recorded decision.

No item below is approved merely because it appears in the PRD or in an assistant recommendation.

## Decision register

| ID | Decision required | Options / question | Recommendation (not approval) | Status |
|---|---|---|---|---|
| `OD-001` | MVP product boundary | A. Player + Parent + SSB + Competition (PRD §26). B. Football Identity + Competition + SSB (PRD §40). C. Another explicitly scoped combination. | Use the strategic wedge to order delivery, but retain parent/guardian safety as a foundational cross-cutting capability. Confirm whether Parent is an MVP user surface or only a supporting access/consent surface. | OPEN |
| `OD-002` | First operational pilot | Competition-led pilot, SSB operations pilot, or another sequence | Validate with actual founding SSBs and tournament organizers before committing. | OPEN |
| `OD-003` | Real child data in first pilot | Real child records vs synthetic-only pilot until child-safety gates pass | Do not use real child data until guardian, consent, authorization, audit, retention, and safeguarding controls are approved and independently verified. | OPEN |
| `OD-004` | Guardian and consent policy owner | Identify policy owner, verification standards, consent scope, revocation, disputes, age transitions, evidence handling | Treat as mandatory design work before child data; obtain qualified legal/safeguarding review. | OPEN |
| `OD-005` | Initial platform surfaces | Mobile app, responsive web, admin web, or staged combination | Determine based on user workflows, delivery capacity, and operational needs; PRD's Flutter/React Native and Next.js/React are suggestions only. | OPEN |
| `OD-006` | Technology stack | Select frontend, backend, database, auth, storage, hosting, CI/CD | Evaluate options against requirements and team capacity; do not inherit a stack from the old repository by default. | OPEN |
| `OD-007` | Provider and environment ownership | Backend/database/storage/auth/hosting owner; dev/staging/prod boundaries; billing and recovery owner | Establish ownership and export/exit plan before provider connection or schema changes. | OPEN |
| `OD-008` | Football ID semantics | Canonical entity, identifier format, uniqueness, issuance, correction, duplicate resolution, privacy | Keep identity independent from organization affiliation; do not finalize identifier format from illustrative examples in PRD. | OPEN |
| `OD-009` | Person/account/role cardinality | One person, multiple roles; account identity mapping and recovery | Preserve one-person/multiple-role principle while specifying account linking and identity proofing. | OPEN |
| `OD-010` | Organization hierarchy and geographic scope | SSB/club/academy/organizer/association/federation relationships and delegated authority | Define explicit hierarchy and authority boundaries before RBAC/ABAC matrix. | OPEN |
| `OD-011` | MVP competition workflow | Categories, registrations, eligibility, payment, roster lock, schedule, results, standings, corrections | Define one end-to-end vertical slice and acceptance evidence after OD-001/002. | OPEN |
| `OD-012` | Finance/payment scope | Record-only invoices vs payment gateway and transaction processing | Start with the minimum verified business workflow; do not assume payment integration is required because PRD lists payment. | OPEN |
| `OD-013` | Product portfolio taxonomy | Four vs five products; PRD §41 lists A–E after describing four main products | Confirm public/internal product taxonomy and names. | OPEN |
| `OD-014` | Brand and naming | APSSI Football ID as project brand vs working repository name vs final public brand | Keep current name as working project identifier until brand validation and owner approval. | OPEN |
| `OD-015` | North Star metric | Definition of Verified Active Player and targets | Define verification, active activity window, deduplication, data quality, and reporting rules before dashboarding. | OPEN |
| `OD-016` | South Sulawesi go-to-market | Makassar, Gowa, Maros and founding partner sequence | Validate with field discovery; treat PRD numbers as planning hypotheses. | OPEN |
| `OD-017` | API and integration priorities | Which external systems/organizations and use cases are first | Prioritize only integrations with confirmed partners, data rights, and technical ownership. | OPEN |
| `OD-018` | Data retention, correction, deletion, and portability | Policy per data category and user lifecycle | Define before production data; include child data, consent evidence, audit records, media, and account closure. | OPEN |

## Decision record template

For every owner decision, append or update a record containing:

- Decision ID:
- Date:
- Decision owner:
- Exact question:
- Options considered:
- Decision:
- Rationale:
- Scope affected:
- Requirements affected:
- Consequences / risks:
- Evidence / references:
- Approval wording:
- Status:
- Supersedes (if applicable):

## Approval rule

An item becomes `APPROVED` only when the owner explicitly identifies the decision ID and the selected option/wording. General agreement with a broad direction does not approve details that were not presented.
