# ChainTrace -- UML Design Documentation

**Project:** ChainTrace -- Supply Chain Disruption Monitoring and
Response Management System\
**Institution:** CVR College of Engineering\
**Laboratory:** Software Engineering Laboratory\
**Domain:** Supply Chain Management and Logistics Operations\
**Documentation baseline:** Phase I Requirements Engineering, Version
1.0; Phase II SRS, Version 1.0

------------------------------------------------------------------------

## 1. Overview

This folder contains the UML design documents prepared for the
ChainTrace project. The diagrams provide visual representations of the
system's actors, conceptual information classes, workflows,
interactions, lifecycle, software components and deployment arrangement.

The UML documentation is divided into two PDF files for convenient
review and submission:

-   **UML Diagrams I** -- core structural and workflow diagrams.
-   **UML Diagrams II** -- interaction, component and deployment
    diagrams.

The diagrams are based on the ChainTrace project requirements and SRS
baseline. They are design representations; they do not establish that
the application has already been implemented or deployed.

## 2. UML PDF Files

  File                               Contents
  ---------------------------------- ----------------
  `ChainTrace_UML_Diagrams_I.pdf`    Diagrams 1--6
  `ChainTrace_UML_Diagrams_II.pdf`   Diagrams 7--12

## 3. Diagram Catalogue

### UML Diagrams I

  ------------------------------------------------------------------------
                           No. Diagram               Purpose
  ---------------------------- --------------------- ---------------------
                             1 Use Case Diagram      Shows the primary
                                                     internal
                                                     actors---Admin,
                                                     Operations Manager
                                                     and Logistics
                                                     Coordinator---and the
                                                     functions they use in
                                                     ChainTrace.

                             2 Class Diagram         Presents the
                                                     conceptual
                                                     information classes
                                                     used by the system,
                                                     including users,
                                                     shipments, tracking
                                                     events, disruptions,
                                                     dependencies, impact
                                                     assessments, response
                                                     actions and audit
                                                     entries.

                             3 Activity Diagram --   Shows the workflow
                               Shipment Tracking     for recording a
                                                     manual tracking
                                                     update or simulated
                                                     event and adding it
                                                     to shipment history.

                             4 Activity Diagram --   Shows rule
                               Disruption and Impact evaluation,
                               Assessment            disruption creation
                                                     or update, dependency
                                                     checking and
                                                     operational review of
                                                     potential impacts.

                             5 Activity Diagram --   Shows response-action
                               Response Action       creation, assignment,
                               Workflow              progress updates and
                                                     controlled
                                                     resolution.

                             6 State Machine Diagram Illustrates the
                               -- Disruption         conceptual
                               Lifecycle             progression from
                                                     detection through
                                                     review and action to
                                                     resolution.
  ------------------------------------------------------------------------

### UML Diagrams II

  ------------------------------------------------------------------------
                           No. Diagram               Purpose
  ---------------------------- --------------------- ---------------------
                             7 Sequence Diagram --   Shows the interaction
                               Record Tracking       between the Logistics
                               Update                Coordinator, web
                                                     interface, tracking
                                                     service, database and
                                                     rule engine when a
                                                     tracking update is
                                                     recorded.

                             8 Sequence Diagram --   Shows rule
                               Disruption Detection  evaluation,
                               and Impact            disruption record
                                                     handling, dependency
                                                     retrieval and
                                                     notification for
                                                     impact review.

                             9 Sequence Diagram --   Shows how the
                               Create and Assign     Operations Manager
                               Response Action       creates and assigns a
                                                     corrective action and
                                                     how the system
                                                     records and notifies
                                                     the assignment.

                            10 Component Diagram     Shows the logical
                                                     application layers
                                                     and the
                                                     responsibilities of
                                                     the user interface,
                                                     application services,
                                                     rules, response
                                                     services and
                                                     persistence.

                            11 Deployment Diagram    Shows a conceptual
                                                     single-organization
                                                     web deployment with
                                                     user devices, an
                                                     application server
                                                     and a database
                                                     server.

                            12 Sequence Diagram --   Shows the
                               Disruption Resolution authorization check,
                                                     required resolution
                                                     note, status update
                                                     and audit recording
                                                     involved in resolving
                                                     a disruption.
  ------------------------------------------------------------------------

## 4. Primary Actors

ChainTrace defines three authenticated internal user roles:

-   **Admin:** Manages internal user accounts, roles, system
    configuration, disruption rules and escalation settings.
-   **Operations Manager:** Monitors operations, reviews disruptions and
    potential impacts, assigns corrective actions, handles escalations
    and monitors resolution.
-   **Logistics Coordinator:** Maintains supplier and shipment
    information, records tracking updates, creates simulated events
    where permitted and updates assigned tasks.

Suppliers, carriers, warehouse personnel, production departments and
senior management are indirect stakeholders. They do not receive direct
accounts in the initial project scope.

## 5. Important Modelling Rules

The diagrams should be interpreted using the following project rules:

1.  A shipment delay is not automatically a confirmed operational
    impact.
2.  A disruption is identified only when an active predefined rule
    condition is satisfied.
3.  Downstream consequences identified from configured dependencies are
    **potential impacts** until reviewed by an authorized person.
4.  Missing dependency information means impact analysis is incomplete;
    it must not be treated as proof that no impact exists.
5.  Severity classification and escalation follow
    administrator-configured criteria.
6.  Manual tracking updates and simulated tracking events must be
    distinguishable.
7.  Only an authorized Operations Manager may resolve a disruption, and
    a resolution action and note are required.
8.  Important user and system activities must be represented in the
    audit history.

## 6. Scope Boundaries Reflected in the Diagrams

The initial ChainTrace release is a centralized web application for one
organization and its internal users. The diagrams do not assume:

-   Real-time GPS tracking.
-   Direct carrier or third-party logistics integrations.
-   Live weather or traffic integrations.
-   Automated route optimization.
-   Financial transactions or freight-payment processing.
-   Machine-learning-based disruption prediction.
-   Supplier, carrier or customer self-service accounts.
-   External SMS, email or third-party messaging notifications.
-   Multi-company or multi-tenant operation.

The application stack, database product, hosting platform and final
browser-version policy remain implementation decisions unless separately
approved.

## 7. Relationship to Requirements Documents

The UML diagrams are intended to be read alongside:

-   `ChainTrace_Phase_1_Requirements_Engineering.pdf`
-   `ChainTrace_Phase_2_SRS.pdf`

Phase I establishes the project problem, objectives, scope,
stakeholders, constraints and high-level workflow. Phase II specifies
the functional and non-functional requirements, business rules,
conceptual data requirements and acceptance criteria. The UML diagrams
provide visual design views of those requirements.

When a requirement changes, the related diagrams and implementation
tests should be reviewed. Requirement IDs and use-case references should
be retained during implementation and testing to preserve traceability.

## 8. Modelling Notes and Limitations

-   The class diagram is conceptual and is not a finalized physical
    database schema.
-   The deployment diagram is conceptual; it does not prescribe specific
    hardware, hosting, network protocol details or database technology.
-   Exact status values, severity names, rule-expression syntax and
    escalation thresholds should not be assumed unless confirmed in an
    approved design.
-   The disruption lifecycle is an illustrative model. The final state
    values and permitted transitions should be confirmed during detailed
    design.
-   These PDFs document the proposed design. They do not prove that
    implementation, integration, testing or deployment is complete.

## 9. Suggested Project Folder Structure

``` text
ChainTrace/
│
├── README.md
│
├── requirements/
│   ├── ChainTrace_Phase_1_Requirements_Engineering.pdf
│   └── ChainTrace_Phase_2_SRS.pdf
│
├── uml-diagrams/
│   ├── README.md
│   ├── ChainTrace_UML_Diagrams_I.pdf
│   └── ChainTrace_UML_Diagrams_II.pdf
│
└── src/
    └── (application source code, when implemented)
```

## 10. Project Status

This folder contains the UML design documentation for the ChainTrace
project. It does not, by itself, establish that the application has been
implemented, tested or deployed.

Update the project status as work progresses:

-   Requirements review: Pending / Completed
-   UML design review: Pending / Completed
-   Application implementation: Not started / In progress / Completed
-   Testing against acceptance criteria: Pending / In progress /
    Completed
-   Deployment: Not started / In progress / Completed

------------------------------------------------------------------------

**ChainTrace -- Supply Chain Disruption Monitoring and Response
Management System**\
**Software Engineering Laboratory \| CVR College of Engineering**
