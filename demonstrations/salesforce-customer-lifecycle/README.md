# Salesforce Customer Lifecycle — GameHub Indonesia

A hands-on Salesforce CRM demonstration focused on customer data, customer lifecycle, customer service, and CRM automation.

> **Project Type:** Self-Directed Demonstration  
> **Platform:** Salesforce Trailhead Playground  
> **Business Context:** Fictional digital gaming and top-up business

GameHub Indonesia is a fictional business created for this demonstration and learning project. It does not represent the actual internal systems, databases, processes, or performance of any previous employer.

---

## Overview

This project explores how Salesforce can be used to manage customer relationships and customer service for a digital gaming and top-up business.

The project started from a simple customer scenario and is being developed step by step in a Salesforce Trailhead Playground.

The main areas covered are:

- CRM data modeling
- Customer and prospect management
- Lead conversion
- Customer lifecycle management
- Customer service and Case management
- CRM automation
- Customer segmentation
- Reporting and dashboards

The goal is not only to learn Salesforce features, but to understand how CRM concepts can be translated into an actual CRM platform.

---

## Business Context

GameHub Indonesia represents a fictional digital gaming and top-up business.

A typical customer journey can look like:

~~~
Customer Discovery
       ↓
Customer Registration / Lead
       ↓
First Purchase
       ↓
Repeat Purchase
       ↓
Customer Support
       ↓
Retention / Re-engagement
~~~

The CRM should help maintain customer information and provide context across these interactions.

---

## Project Objectives

This project is designed to practice and demonstrate:

- Salesforce standard objects
- Custom objects and fields
- CRM data modeling
- Object relationships
- Lead conversion
- Customer lifecycle management
- Customer service workflows
- Case management
- CRM automation
- Customer segmentation
- Reporting and dashboards

---

## Salesforce Objects

The project starts with Salesforce standard objects where they fit the business process.

| Object | Purpose |
|---|---|
| **Lead** | Represents a prospect before conversion |
| **Account** | Represents the account/customer relationship |
| **Contact** | Represents an individual customer |
| **Opportunity** | Represents a potential business deal |
| **Case** | Represents a customer issue or support request |

Custom objects will only be introduced when a business requirement cannot be represented appropriately using the available standard objects.

---

## Initial CRM Flow

The first hands-on exercise used Salesforce's standard Lead conversion flow:

~~~
Lead
  ↓
Convert
  ↓
Account + Contact + Opportunity
~~~

For example:

~~~
Lead
└── Andi Pratama
        ↓
Account
└── Gamehub Indonesia

Contact
└── Andi Pratama

Opportunity
└── First Purchase - Andi Pratama
~~~

This exercise helped demonstrate how Salesforce connects different CRM records during lead conversion.

---

## Customer Service

Customer support is represented using Salesforce's **Case** object.

A Case can contain information such as:

- Customer/contact
- Account
- Subject
- Status
- Priority
- Case owner
- Case history

Example Case created during the hands-on exercise:

~~~
Subject:
Top Up MLBB Belum Diterima

Status:
New

Priority:
Medium

Contact:
Andi Pratama

Account:
Gamehub Indonesia
~~~

The Case will later be used to practice assignment and automation.

---

## Customer Lifecycle

The project uses the following proposed customer lifecycle:

~~~
NEW
 │
 ▼
FIRST PURCHASE
 │
 ▼
ACTIVE CUSTOMER
 │
 ▼
REPEAT CUSTOMER
 │
 ▼
AT RISK
 │
 ▼
RE-ENGAGEMENT
~~~

These lifecycle stages are part of the fictional demonstration and are not claimed to be the exact lifecycle definitions used by any previous employer.

The purpose is to explore how customer data can be used to support different engagement and retention strategies.

---

## Data Model

The project follows Salesforce's object-based data model.

The initial conceptual model is:

~~~
Account
   │
   └── Contact
          │
          ├── Purchase
          ├── Case
          └── Engagement
~~~

The `Purchase` and `Engagement` objects are currently part of the proposed B2C-oriented model.

They will be evaluated and implemented only if they provide a clear business requirement.

See:

- [`data-model.md`](data-model.md)

---

## Case Management and Automation

The next stage of the project focuses on reducing manual work in customer support.

The planned workflow is:

~~~
Case Created
     ↓
Case Classification
     ↓
Assignment Rule
     ↓
Support Queue
     ↓
Customer Response
     ↓
Resolution / Escalation
~~~

The purpose is to understand how Salesforce can automate repetitive Case management tasks instead of requiring every Case to be handled manually.

See:

- [`case-management.md`](case-management.md)
- [`automation.md`](automation.md)

---

## Project Documentation

| Document | Description |
|---|---|
| [`business-requirements.md`](business-requirements.md) | Business context, requirements, and project scope |
| [`data-model.md`](data-model.md) | Objects, fields, and relationships |
| [`customer-lifecycle.md`](customer-lifecycle.md) | Customer lifecycle and segmentation |
| [`case-management.md`](case-management.md) | Customer service and Case workflow |
| [`automation.md`](automation.md) | Salesforce automation and routing |
| [`reports-and-dashboard.md`](reports-and-dashboard.md) | Reporting and dashboard design |

These documents will be updated as the project is implemented and tested in the Salesforce Playground.

---

## Current Progress

### Completed

- [x] Salesforce Trailhead Playground created
- [x] Lead created
- [x] Lead converted into Account, Contact, and Opportunity
- [x] Opportunity configured for a first-purchase scenario
- [x] Customer Case created
- [x] Salesforce data model fundamentals studied
- [x] Standard and custom objects studied
- [x] Custom fields and field data types studied

### In Progress

- [ ] Object relationships
- [ ] Case Assignment Rules
- [ ] Support Queue
- [ ] Case automation
- [ ] Customer lifecycle implementation
- [ ] Custom transaction model
- [ ] Customer engagement model
- [ ] Reports and dashboards

---

## Learning Approach

This project follows a practical learning approach:

~~~
Learn
  ↓
Understand
  ↓
Build in Salesforce
  ↓
Test
  ↓
Document
  ↓
Improve
~~~

Salesforce Trailhead is used as the structured learning source, while the GameHub Indonesia Playground is used to apply the concepts through hands-on exercises.

The project is intentionally developed incrementally rather than trying to build a complete CRM system at once.

---

## Relation to Previous Experience

This project builds on my previous exposure to:

- Customer relationship management
- Customer journey
- Customer engagement
- Customer support
- Complaint handling
- Customer segmentation
- Retention and re-engagement
- Operational workflow improvement

My previous experience gave me exposure to CRM-related business processes, while this project is an opportunity to develop a more structured understanding of CRM platforms and apply those concepts using Salesforce.

The Salesforce implementation itself is a **new self-directed demonstration** and should not be interpreted as professional Salesforce implementation experience.

---

## Portfolio Purpose

This project demonstrates my transition from CRM and customer operations experience toward practical CRM platform implementation.

The project focuses on understanding how business requirements can be translated into:

- CRM data structures
- Customer relationships
- Customer service workflows
- Automation
- Customer lifecycle management
- Reporting

It also documents the reasoning behind the design rather than only showing the final Salesforce configuration.

---

## Status

**In Progress**

The project will continue to evolve as new Salesforce concepts are learned, implemented, tested, and documented.
