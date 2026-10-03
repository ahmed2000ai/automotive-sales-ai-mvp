You are working inside a GitHub-backed Codex project for an existing Saudi automotive sales-conversion product.

This repository is the **persistent project workspace and source of truth**.

Do not depend on files stored on my local PC.

All important project knowledge, architecture decisions, code, tests, and outputs must remain inside this repository.

---

# 1. Repository operating model

The repository should contain or evolve toward a structure similar to:

```text
automotive-sales-ai-mvp/
├── project-knowledge/
│   ├── 00-project-context-and-current-status.md
│   ├── 01-initial-research.md
│   ├── 02-competition-sector-and-go-to-market-research.md
│   ├── 03-automotive-market-and-competitor-research.md
│   ├── 04-whatsapp-mystery-shopping-plan.md
│   ├── 05-whatsapp-mystery-shopping-results.md
│   ├── 06-post-enquiry-analysis-and-product-validation.md
│   ├── 07-vip-car-care-response-analysis-and-product-implications.md
│   ├── 08-mvp-definition-and-customer-validation-plan.md
│   └── 09-client-facing-ui-and-product-experience-strategy.md
│
├── codex-prompts/
│   ├── 01-phase-1-architecture-feasibility-ui-ux-and-technical-spike.md
│   └── 02-phase-2-build-integration-testing-and-demo.md
│
├── app/
├── services/
├── docs/
├── tests/
├── .env.example
├── .gitignore
└── README.md
```

Do not reorganize or rename the existing `project-knowledge/` files without a strong technical reason.

Preserve the numbered project chronology.

The existing project knowledge documents are historical/source documents and should normally remain unchanged unless a genuine correction is needed.

The file most likely to be updated during this phase is:

`project-knowledge/00-project-context-and-current-status.md`

---

# 2. Git workflow

Work on a dedicated branch:

`phase-1-architecture`

If this branch does not exist and you have permission to create it, create it.

Use Git deliberately.

Make logical commits during the phase rather than one giant final commit.

Examples of reasonable commit boundaries:

- repository
