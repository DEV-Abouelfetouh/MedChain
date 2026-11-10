# Project Planning — MedChain (Draft v0.1)

## Overview
MedChain is a web platform for managing the medical activity chain
(clinic → doctor → patient → pharmacist) with patient-controlled privacy.

- **Duration:** 10 weeks
- **Scope:** v1 only (no blockchain, no appointments, no inventory)

## Phases

| Phase | Focus | Duration |
|-------|-------|----------|
| 1 | Analysis & Design (ERD, API, Wireframes) | 1–2 weeks |
| 2 | Backend Foundation (Auth, RBAC, Core Modules) | 4 weeks |
| 3 | Frontend (Role-based Dashboards) | 4 weeks (parallel) |
| 4 | Testing & UAT | 1 week |
| 5 | Documentation & Delivery | 1 week |

## Milestones

| # | Milestone | Target |
|---|-----------|--------|
| M0 | Foundation Ready (Repo + ERD + API + Wireframes) | Week 1 |
| M1 | Auth & Access Live | Week 3 |
| M2 | Medical Records Live | Week 5 |
| M3 |  | Week 7 |
| M4 || Week 9 |
| M5 || Week 10 |

## Risks (High Level)

- Scope creep → freeze v1 scope
- Prescription flow delay → prototype early
- RBAC/data leakage → dedicated test matrix
- Delivery pressure → feature freeze by end of Week 9

## Deliverables

BRS · ERD · API Spec · Wireframes · Backend Code · Frontend Code ·
Docker Compose · Seed Data · README · Demo Video · Presentation · UAT Report

> **Note:** This is an initial draft. Details will be refined in later revisions.
