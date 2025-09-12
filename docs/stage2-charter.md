# Project Charter — Expiry Tracker (MVP)

---

## 0) Project Objectives

**Purpose**  
The *Expiry Tracker* project aims to help individuals avoid the stress, financial loss, and administrative issues caused by forgotten expiration dates (e.g., ID cards, passports, warranties, subscriptions).
It provides a simple, centralized tool to keep all expirations visible and organized.

**SMART Objectives**
- By **November 7, 2025**, deliver an MVP that allows users to **add, view, and delete expiration items** with items automatically sorted by date.
- By **November 7, 2025**, implement a **visual highlight** for items expiring within **30 days**, enabling users to prioritize urgent renewals.
- By **November 7, 2025**, conduct a **usability test with at least 3 users** and collect **≥ 5 actionable insights** for future iterations.

---

## 1) Stakeholders & Roles

**Stakeholders**
- **Internal:** Bagashvili Patricia (Project Manager, Developer, Tester)
- **External:** Instructors (review & guidance), potential end-users (students, professionals, families for testing)

**Roles & Responsibilities**

| Role             | Person               | Responsibilities                                       |
|------------------|----------------------|--------------------------------------------------------|
| Project Manager  | Patricia Bagashvili  | Plan, track progress, maintain charter                 |
| Functional Lead  | Patricia Bagashvili  | Define MVP features, ensure objectives are met         |
| Technical Lead   | Patricia Bagashvili  | Select tools, ensure quality of implementation         |
| Developer        | Patricia Bagashvili  | Implement CRUD features, persistence, UI               |
| QA Tester        | Patricia Bagashvili  | Test core functions, report bugs, validate usability   |

**Communication**
- Repository: GitHub (project code + documentation)
- Progress review: Weekly self-checks every Sunday 

---

## 2) Scope

**In-Scope (MVP)**
- Add an item with name + expiration date
- Display list of items sorted by soonest expiry
- Highlight items expiring in ≤ 30 days
- Delete items from the list
- Store data locally (browser local storage)

**Out-of-Scope**
- User accounts or login system
- Email, SMS, or push notifications
- Calendar or email integration
- Tags, categories, or filters
- Multi-device synchronization

**Constraints**
- Solo project → must remain simple and achievable
- Timeline fixed: Aug 18 – Nov 7, 2025

---

## 3) Risks & Mitigations

| ID  | Risk                      | Likelihood | Impact | Mitigation                          |
|-----|---------------------------|------------|--------|-------------------------------------|
| R1  | Over-scoping the MVP      | Medium     | High   | Freeze scope, weekly reviews        |
| R2  | Time slippage (solo work) | Medium     | High   | Weekly plan, focus blocks (6–8h)    |
| R3  | Low user adoption         | Medium     | Medium | Minimal UI, quick-add feature       |
| R4  | Data persistence bugs     | Low        | Medium | Save/load tests, manual checklist   |
| R5  | Accessibility/UX issues   | Medium     | Medium | Contrast check, labels, a11y review |


---

## 4) High-Level Plan (Timeline & Milestones)

**Stages & Milestones**
- **Stage 1 — Idea Development (Done)**
  *Aug 18 – Aug 29* → Idea selection + Stage 1 report ☑

- **Stage 2 — Project Charter (Current)**
  *Sep 1 – Sep 12* → Draft charter; review & finalize 

- **Stage 3 — Technical Documentation**
  *Sep 15 – Sep 26* → Architecture, data model, acceptance criteria, test plan

- **Stage 4 — MVP Development**
  *Sep 29 – Oct 24* → Iteration 1 (core CRUD) → Iteration 2 (UX polish)

- **Stage 5 — Closure**  
  *Oct 27 – Nov 7* → Final testing, demo, retrospective, next-step backlog

**ASCII Timeline**

Aug 18 |■■■■ Stage 1 ■■■■|
Sep 1  |■■■■ Stage 2 ■■■■|
Sep 15 |■■■■ Stage 3 ■■■■|
Sep 29 |■■■■■■■■ Stage 4 ■■■■■■■■|
Oct 27 |■■■■ Stage 5 ■■■■|
Nov 7  |▶ Delivery


**Definition of Done**
- Charter accepted when: all sections completed, ≤ 2 pages, scope locked.
- MVP accepted when: user can add/list/delete items; items auto-sorted; near-expiry highlight works; smoke tests pass.

---

## 5) Sharing & Review

- **Storage:** GitHub repository (docs + code)
- **Instructor review:** Upon submission of Stage 2
- **Feedback log:** Collect improvements and adjust for Stage 3

---
