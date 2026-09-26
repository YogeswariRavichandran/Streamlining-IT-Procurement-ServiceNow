# Phase 2: Comprehensive Requirement Analysis

## Executive Overview
The primary objective of this phase is to analyze, capture, and document the functional and non-functional requirements for automating the IT Procurement workflow within ServiceNow. By shifting from legacy manual task creation to automated workflow triggers, the organization aims to reduce request processing overhead, enhance service desk productivity, and establish standard asset configuration protocols.

---

## Stakeholder Identification & Roles

| Stakeholder Role | Primary Interest | Responsibilities |
| :--- | :--- | :--- |
| **End-User / Requester** | Fast procurement & real-time visibility | Submits standard laptop request via Service Catalog |
| **Approver / Manager** | Budget control & governance | Reviews and approves/rejects item requests |
| **Fulfillment Team (Hardware)** | Clear, actionable tasks | Receives automated `SCTASK`, prepares & stages devices |
| **ServiceNow Administrator** | System stability & automation | Configures Flow Designer, catalog items, and routing rules |

---

## Detailed Functional Requirements (FR)

### FR-01: Service Catalog Triggering
- **Trigger Event:** Submission of the *Standard Laptop* Catalog Item (`sc_req_item`) via Service Portal.
- **Trigger Condition:** Executes automatically upon approval of the parent Request/Requested Item (`RITM`).
- **Context Handling:** Captures contextual data including Requester ID, Delivery Location, and Contact Information directly from the parent record.

### FR-02: Automated Catalog Task (`SCTASK`) Generation
- **Action:** Flow Designer automatically instantiates a child Catalog Task record upon trigger execution.
- **Record Relationship:** Task must maintain parent-child linkage with the corresponding `RITM` record.

### FR-03: Mandatory Task Field Mappings
The created Catalog Task (`sc_task`) must automatically populate the following fields:
* **Short Description:** `Laptop need to Configured`
* **Description:** `Laptop need to Configured`
* **Assignment Group:** `Hardware`
* **Approval State:** `Approved`
* **State:** `Open` (Ready for fulfillment assignment)

### FR-04: Task Lifecycle & Routing
- Automatically routes the created task to the **Hardware** group queue without manual service desk intervention.
- Updates the parent `RITM` state to *Work in Progress* once the task is created.

---

## Non-Functional Requirements (NFR)

### NFR-01: Operational Efficiency & SLA Target
- **Task Creation Speed:** Task creation must occur within 5 seconds of request approval.
- **Turn-Around Time (TAT):** Reduces overall request-to-delivery fulfillment cycle by at least 40%.

### NFR-02: System Reliability & Data Accuracy
- **Zero Manual Errors:** 100% elimination of typos and misclassifications in task descriptions and group assignments.
- **Auditability:** Every step of the flow execution must be logged in ServiceNow Flow Execution history for audit tracking.

### NFR-03: Maintainability & Scalability
- **Low-Code Architecture:** Configured strictly using ServiceNow **Flow Designer** without relying on complex background scripts or legacy Workflow Editor.
- **Reusability:** Flow architecture should allow easy extension for other hardware asset catalog items (e.g., Desktop, Monitors) in future releases.

---

## Traceability Matrix

| Requirement ID | Requirement Type | Target ServiceNow Object | Implementation Component |
| :--- | :--- | :--- | :--- |
| **FR-01** | Functional | `sc_req_item` | Service Catalog Trigger |
| **FR-02** | Functional | `sc_task` | Flow Action: Create Catalog Task |
| **FR-03** | Functional | `sc_task` | Data Mapping in Flow Action |
| **FR-04** | Functional | `sys_user_group` | Assignment Group Routing (`Hardware`) |
| **NFR-01** | Non-Functional | System Engine | ServiceNow Flow Designer Engine |
| **NFR-02** | Non-Functional | `sys_flow_context` | ServiceNow Execution Logs |
