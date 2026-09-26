# Phase 3 – Project Design

## 1. System Design

The system is designed using the ServiceNow platform.

The Service Catalog provides the interface for submitting procurement
requests.

Flow Designer automates the processing of the submitted request.

## 2. System Architecture

User
  ↓
ServiceNow Service Catalog
  ↓
Procurement Request
  ↓
Flow Designer
  ↓
Approval
  ↓
Automated Task Creation
  ↓
IT/Procurement Team
  ↓
Request Completion

## 3. Process Flow

1. User opens the IT procurement catalog item.
2. User enters the required information.
3. User submits the request.
4. ServiceNow triggers the flow.
5. The request is sent for approval.
6. The approval decision is processed.
7. If approved, procurement tasks are created.
8. The responsible team processes the task.
9. The request is updated.
10. The request is completed.

## 4. Main Components

### Service Catalog

Used for submitting IT procurement requests.

### Flow Designer

Used to automate the procurement workflow.

### Approval

Used to obtain authorization for the request.

### Task

Used to assign procurement activities to the responsible team.

### Notification

Used to communicate important status changes.

## 5. Design Goal

The design aims to minimize manual intervention and provide an
automated and trackable procurement process.
