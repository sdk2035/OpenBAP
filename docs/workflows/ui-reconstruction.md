# UI Reconstruction Workflow

## Objective

Recover user-interface intent from legacy transactions and screens, then generate maintainable OpenXava views from the validated OpenBAP semantic model.

## Workflow

```mermaid
flowchart LR
    A[Transactions / Screens / UI Metadata] --> B[Extract Fields & Actions]
    B --> C[Bind to Canonical Domain Model]
    C --> D[Recover Navigation & Validation Intent]
    D --> E[AI-Assisted OpenXava Proposal]
    E --> F[JPA / OpenXava Metadata]
    F --> G[Role & Workflow Validation]
    G --> H[UI Acceptance Tests]
```

## Inputs

- transaction codes and screen flows;
- field labels, domains, required-state rules, and value helps;
- action/menu definitions;
- authorization context;
- reports and list/detail patterns;
- user stories and operational procedures where available.

## Generation Rules

The UI generator should derive presentation from the canonical semantic model rather than duplicate business logic in the view layer. Generated assets may include:

- JPA entities and relations;
- OpenXava `@View`, `@Tab`, validation, and action metadata;
- list/detail screens;
- role-oriented field visibility;
- navigation links and workflow actions;
- localized labels and validation messages.

AI proposals should be constrained by domain metadata and source traceability. Ambiguous layouts should be surfaced for review rather than guessed silently.

## Validation

UI acceptance should verify:

1. required fields and validations;
2. role/authorization visibility;
3. navigation and action sequences;
4. value helps and reference data;
5. error and confirmation behavior;
6. accessibility and responsive layout expectations;
7. consistency with the reconstructed domain model.

## Deliverable

The output is a generated OpenXava application projection linked back to the same canonical entities, rules, and source artifacts used by the runtime and migration workflows.
