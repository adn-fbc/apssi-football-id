# C0-03 — PRD Baseline & Traceability Audit

| Metadata | Value |
|---|---|
| Audit ID | `C0-03` |
| Project | APSSI Football ID |
| Repository | `adn-fbc/apssi-football-id` |
| Branch / baseline commit | `main` / `d3b46b1c0cc577e6eabe511bef61047e345eaaa9` |
| Audit date | 2026-11-15 |
| Audit type | Product/documentation baseline; no implementation |
| Status | `AUDIT COMPLETE — OWNER REVIEW REQUIRED` |

## 1. Objective

Convert the supplied PRD into a structured product baseline, trace requirements to source sections, identify ambiguity and decisions, and prepare documentation suitable for review as the project's initial product baseline.

## 2. Evidence examined

### 2.1 New repository checkpoint

Local PowerShell output supplied by the owner established:

- Repository root: `D:/APSSI/PLATFORM APSSI/apssi-football-id`
- Branch: `main`
- HEAD and `origin/main`: `d3b46b1c0cc577e6eabe511bef61047e345eaaa9`
- Commit summary: `Initial commit`
- Working tree status: empty output from `git status --short`
- Remote: `https://github.com/adn-fbc/apssi-football-id.git`
- Tracked files: `.gitattributes`, `.gitignore`, `README.md`
- Root listing: `.git`, `.gitattributes`, `.gitignore`, `README.md`

This establishes a minimal initial repository snapshot. It does not establish push permission, build readiness, runtime readiness, provider setup, or security posture.

### 2.2 Product source

Read the complete 1,623-line `prd.txt`:

- Title: `BLUEPRINT — YOUTH FOOTBALL ECOSYSTEM PLATFORM`
- Version: `0.1 — Indonesia`
- Sections: 1–47
- File size reported by Library: 22,967 bytes

### 2.3 Related production readiness gap analysis

Also read `PRODUCTION_READINESS_GAP_ANALYSIS(1).md` (317 lines). Its audit target is the separate repository `adn-fbc/football-journey-identity-hub`, commit `271c4612440e4e4932f181bd045cbe9c4981d0f9`.

**Scope restriction:** that gap analysis is not evidence about the new `apssi-football-id` repository. It is not used to transfer old code findings, framework choices, provider assumptions, or repository defects into this new project. It is useful only as a cautionary reference for risk categories such as persistence, trusted authorization, child safety, tenant isolation, release evidence, backup/restore, and secret hygiene.

## 3. Audit findings

### Finding C03-F01 — PRD is a broad ecosystem vision, not a fully testable MVP specification

The PRD contains product vision, stakeholder groups, role capabilities, domain concepts, product hierarchy, business hypotheses, growth targets, and technical suggestions. Many statements require decomposition into workflows, permissions, data rules, and acceptance criteria before implementation.

**Disposition:** create a baseline and traceability matrix; do not treat the full PRD as an implementation backlog.

### Finding C03-F02 — MVP boundary ambiguity

PRD §26 defines MVP 1 as Player + Parent + SSB + Competition. PRD §39–40 argues for Tournament as a strategic wedge and then states MVP priority as Football Identity + Competition + SSB.

These can be reconciled as delivery sequencing vs user-surface scope, but the PRD does not explicitly make that distinction.

**Disposition:** `OD-001` remains OPEN. Do not silently select one formulation.

### Finding C03-F03 — Child-safety requirements are foundational but policy details are absent

PRD §19, §18, §33, and §34 establish guardian relationships, consent, access control, audit, revocation, minimization, and conditional scout access. The PRD does not fully specify guardian verification standards, consent wording/legal basis, disputes, age transitions, retention, evidence handling, or safeguarding escalation.

**Disposition:** preserve as P0 design constraints; require owner/policy decisions and qualified review before real child data is processed.

### Finding C03-F04 — Identity and affiliation principles need formal invariants

PRD §5–6 and §21–22 describe stable Football ID, one person/multiple roles, and time-bound organization affiliation. Identifier format, duplicate resolution, identity proofing, account mapping, and correction lifecycle remain undefined.

**Disposition:** record identity invariants in the conceptual architecture baseline; defer schema and issuance design pending OD-008/009.

### Finding C03-F05 — Governance is stated at principle level

PRD §33 proposes RBAC + ABAC with examples for parent, coach, SSB admin, scout, association, and federation. It does not define a complete permission matrix or all resource/purpose/data-category combinations.

**Disposition:** create the permission matrix as a Phase 0 deliverable; no role should be treated as globally privileged by default.

### Finding C03-F06 — Technical architecture is advisory

PRD §24 suggests multiple framework choices and a set of common infrastructure components. It does not provide enough constraints to choose a final stack or provider.

**Disposition:** no technology selection in this audit. Record options for a separate technical decision.

### Finding C03-F07 — Commercial and growth figures are hypotheses

The PRD labels multi-year player targets as planning targets and includes example SaaS prices that require market validation.

**Disposition:** retain as hypotheses; do not treat as commitments, forecasts, approved prices, or acceptance criteria.

### Finding C03-F08 — Product portfolio taxonomy needs clarification

PRD §41 says four products then lists Product A through Product E, adding Football Intelligence.

**Disposition:** `OD-013` remains OPEN. This is a taxonomy clarification, not a blocker to understanding the core identity/competition direction.

### Finding C03-F09 — Naming remains provisional

PRD §43–44 says the final name should not be locked before brand validation. The repository name is `apssi-football-id`.

**Disposition:** treat repository/project name as a working identifier only; `OD-014` remains OPEN for public brand.

## 4. Source-to-baseline mapping

| Source section | Captured in |
|---|---|
| 1–3 Vision, positioning, problem | `docs/product/PRD-BASELINE.md` §§2–4 |
| 4–6 Identity layer and Football ID principles | Product baseline §§5–6; architecture baseline §§2–4 |
| 7–8 Stakeholders and ecosystem | Product baseline §7 |
| 9–18 Role capabilities and development/scouting | Product baseline §8; traceability matrix |
| 19 Guardian/consent | Product baseline §6.4; architecture §5; ODR OD-003/004 |
| 20–22 Data, relational concepts, person/organization model | Product baseline §9; architecture §§2–3 |
| 23–25 Product/technical/API architecture | Product baseline §§12/14; architecture §§2/4/6 |
| 26 MVP | Product baseline §10; ODR OD-001 |
| 27–32 Metrics, business, roadmap | Product baseline §11; ODR OD-015/016 |
| 33–34 Governance and data classification | Product baseline §§6.5/15; architecture §5 |
| 35–36 AI and national dashboard | Product baseline §13; traceability FUTURE items |
| 37–40 GTM and strategic wedge | Product baseline §11.4; ODR OD-001/002/016 |
| 41–44 Product hierarchy, company, naming, positioning | Product baseline §§3/12; ODR OD-013/014 |
| 45–47 North Star architecture, principle, next workstreams | Product baseline §§6/17; architecture §§2/4 |

Detailed requirement IDs are in `docs/product/REQUIREMENTS-TRACEABILITY.md`.

## 5. Baseline document package produced

1. `docs/product/PRD-BASELINE.md`
2. `docs/product/REQUIREMENTS-TRACEABILITY.md`
3. `docs/architecture/DOMAIN-AND-PLATFORM-BASELINE.md`
4. `docs/decisions/OWNER-DECISION-REGISTER.md`
5. `docs/audit/C0-03-PRD-BASELINE-AND-TRACEABILITY-AUDIT.md`

## 6. Audit conclusion

<status>Audit complete, owner approval pending.</status>

The PRD is sufficiently structured to create an initial product baseline and traceability map. It is **not yet sufficiently resolved to authorize implementation** because the MVP boundary, child-data launch posture, initial pilot, and several governance/technology decisions remain open.

The correct outcome is a controlled documentation baseline with explicit unresolved decisions, not a prematurely finalized architecture or implementation backlog.

## 7. C0-03 acceptance checklist

| Acceptance criterion | Result | Evidence / note |
|---|---|---|
| Full PRD reviewed | PASS | 1,623 lines, sections 1–47 read |
| Product vision and problem captured | PASS | Product baseline §§2–4 |
| Stakeholders and roles mapped | PASS | Product baseline §§7–8 |
| Football ID and affiliation principles captured | PASS | Product baseline §6; architecture baseline |
| MVP statements compared | PASS | PRD §26 vs §§39–40 documented |
| Child safety and consent constraints captured | PASS | Product baseline, architecture, decision register |
| Data and governance concepts mapped | PASS | Traceability and architecture baseline |
| Technical suggestions separated from decisions | PASS | Product baseline §14; architecture §6 |
| Requirement traceability created | PASS | Requirement IDs REQ-* |
| Unresolved owner decisions recorded | PASS | OD-001 through OD-018 |
| No unsupported technology selection | PASS | No stack/provider selected |
| No code/repository changes made by this audit | PASS | Audit was documentation analysis only |
| Owner approval of baseline | PENDING | Explicit owner review required |
| Phase 0 completion | NOT YET ESTABLISHED | Additional Phase 0 workstreams and approval remain |

## 8. Explicit non-authorization

This audit and document package do not authorize:

- Phase 1 or feature implementation.
- Creating application source code or installing dependencies.
- Selecting or connecting a backend/provider.
- Creating or applying database migrations/schema.
- Importing real player or child data.
- Enabling guardian, consent, scouting, document, or sensitive-data workflows in production.
- Deploying or publishing a production application.

## 9. Next controlled actions

1. Owner reviews the baseline package.
2. Owner explicitly resolves or accepts as pending the decision IDs in the Owner Decision Register.
3. Complete remaining Phase 0 workstreams: actor map, permission matrix, business rules, data ownership, conceptual ERD, workflow map, UX scope, technical options assessment, and measurable acceptance criteria.
4. Produce a Phase 0 completion audit with evidence.
5. Request a separate explicit owner authorization before Phase 1.

## 10. Change log

| Version | Date | Change |
|---|---|---|
| 0.1 | 2026-11-15 | Initial PRD baseline and traceability audit package |
