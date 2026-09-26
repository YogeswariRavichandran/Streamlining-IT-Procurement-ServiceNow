# Phase 1: Problem Statement & Project Scope

## Executive Summary
In traditional IT service management, manual intervention in fulfilling procurement requests often leads to processing delays, human error in routing, and lack of visibility for asset allocation. This project targets the automation of standard laptop procurement requests using ServiceNow Flow Designer.

---

## Business Problem
- **Manual Overhead:** Service desk technicians manually assign tasks to fulfillment teams upon item request approvals.
- **Inconsistent Data:** Task descriptions, priority levels, and assignment fields are manually entered, leading to discrepancies.
- **SLA Delays:** Time lost during task assignment degrades overall SLA compliance for desktop/hardware services.

---

## Objectives & Key Results (OKRs)
* **Objective:** Fully automate task creation and routing upon order approval.
* **Key Result 1:** Eliminate 100% of manual catalog task creation for standard laptop items.
* **Key Result 2:** Route 100% of configuration tasks immediately to the **Hardware** group.
* **Key Result 3:** Standardize short descriptions and initial states across all generated tasks.

---

## Scope of Work
### In-Scope
- Setup and execution of a ServiceNow flow targeting standard catalog items.
- Dynamic creation of catalog tasks (`SCTASK`) linked to requested items (`RITM`).
- Assignment routing to specific groups (Hardware).
- End-to-end testing in lower (Dev/PDI) environments.

### Out-of-Scope
- Third-party vendor integration or API procurement orders.
- Custom notification script creation outside of standard workflow triggers.
- Hardware asset inventory scanning/barcode integrations.
