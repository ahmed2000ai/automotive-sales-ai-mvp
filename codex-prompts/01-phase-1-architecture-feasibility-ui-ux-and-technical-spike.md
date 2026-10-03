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

- repository preparation
- GHL capability research
- technical spike implementation
- UI/UX architecture
- final Phase 1 specification
- project-context update

At completion:

- leave the working tree clean;
- ensure all intended outputs are committed;
- summarize the commits made;
- leave the branch ready for human review or merge.

Do not merge into the default branch unless explicitly instructed.

Do not rewrite Git history.

Do not delete existing project history.

---

# 3. Secrets and repository safety

Never commit:

- API keys
- passwords
- access tokens
- HighLevel private credentials
- Meta credentials
- WhatsApp tokens
- database credentials
- session cookies
- personal secrets

Use Codex environment secrets or another secure runtime secret mechanism when credentials are required.

Maintain a safe:

`.env.example`

containing variable names only.

Ensure sensitive local files are excluded through `.gitignore`.

Examples may include:

```text
.env
.env.local
.env.*.local
*.pem
*.key
secrets/
credentials/
```

Never place actual secret values inside Markdown documentation.

---

# 4. Project knowledge

Start by reading:

`project-knowledge/00-project-context-and-current-status.md`

Then read the remaining numbered files as needed to fully understand:

- how the opportunity was formed;
- why premium automotive protection was selected;
- completed competitor research;
- WhatsApp mystery-shopping results;
- validated customer-service and sales problems;
- the current MVP definition;
- the customer-validation plan;
- the client-facing UI/product-experience strategy.

Treat the repository documents as the source of truth for previous project decisions.

Do not repeat market research that is already documented unless fresh information is needed to make a current technical or architectural decision.

Clearly distinguish:

- documented evidence,
- your inference,
- and new external research.

---

# 5. Phase 1 objective

Your job in Phase 1 is **not to build the complete production MVP**.

Your job is to:

1. verify what current GoHighLevel capabilities can actually support;
2. determine the correct technical architecture;
3. determine the correct client-facing UI architecture;
4. prove the feasibility of the most differentiated features;
5. identify where native HighLevel is sufficient;
6. identify where a small external service is genuinely needed;
7. design the complete MVP implementation;
8. produce a build-ready Phase 2 specification.

The main deliverable must be:

`project-knowledge/10-ghl-mvp-architecture-ui-and-build-specification.md`

The specification must be detailed enough that another capable engineering agent can implement Phase 2 without rediscovering the architecture.

---

# 6. Product definition

The product is currently:

> **AI-assisted WhatsApp Sales Conversion System for Saudi PPF / Tint / Ceramic / Premium Automotive Protection businesses**

Do not reposition it as:

- a GoHighLevel reseller;
- a generic CRM;
- a generic chatbot;
- a marketing agency;
- a general workshop-management platform.

The core promise is:

> **Never let a valuable WhatsApp lead receive an irrelevant answer, wait unnoticed, or disappear without structured follow-up.**

The management proposition is:

> **Make every salesperson perform more consistently like your best salesperson, while AI makes sure nothing gets missed.**

A useful sales expression is:

> **Turn your Instagram, Snapchat and WhatsApp enquiries into booked cars.**

---

# 7. Architecture principle

The current preferred direction is hybrid:

> **GoHighLevel as the CRM, messaging, workflow and automation engine**

plus:

> **a polished custom branded frontend for the highest-value client-facing experience**

Do not assume this architecture is automatically correct.

Verify current GHL capabilities first.

Determine:

- what should remain native in GoHighLevel;
- what should be white-labeled;
- what should be hidden from end users;
- what should be implemented in a custom frontend;
- whether the frontend should be embedded inside GHL or run independently;
- how authentication should work;
- how the custom UI should read and update GHL data;
- whether a helper backend is required;
- what should remain GHL's system of record.

Prefer native GHL when it can meet the requirement reliably.

Do not weaken an important differentiating feature merely to keep everything inside GHL.

If an external helper is required, keep it as small and focused as possible.

---

# 8. Research current GoHighLevel capabilities

Use current official HighLevel documentation and actual current product behavior before making architecture decisions.

Verify, where relevant:

- WhatsApp integration
- WhatsApp Coexistence
- Conversation AI
- AI Extract Data
- workflow triggers
- workflow actions
- salesperson/user reply triggers
- contacts
- opportunities
- pipelines
- custom fields
- tags
- custom values
- custom objects
- webhooks
- API access
- conversation-history access
- message events
- custom menu links
- embedded custom applications
- dashboards
- reporting
- SaaS white-label options
- custom CSS / JavaScript
- roles and permissions
- snapshots
- calendars
- stop-on-reply behavior
- premium workflow actions
- AI usage costs
- API limits
- authentication options
- webhook limitations
- data access limitations

Prefer official HighLevel sources.

For every important capability classify it as one of:

### Confirmed native capability

### Possible but requires testing

### Workaround available

### Requires external component

### Not suitable for MVP

Document evidence and current limitations.

---

# 9. Technical spike environment

Use only:

- test contacts;
- simulated inbound messages;
- mock/test WhatsApp interactions;
- a dedicated HighLevel test environment/sub-account if available;
- non-production data.

Do not connect production customer numbers.

Do not send real campaigns.

Do not modify real customer records.

Do not purchase subscriptions or upgrades.

Do not accept contractual or Meta terms on my behalf.

If HighLevel login, MFA, Meta authorization, or another user-controlled step blocks you, stop only at that specific point and clearly state the exact action I need to perform.

Continue all other work that does not depend on that blocked action.

---

# 10. Critical technical spike 1 — Context Extraction

Prove whether the system can receive a free-form Arabic enquiry such as:

> عندي نيسان باترول 2025 وأفكر أركب حماية PPF كاملة للسيارة. ممكن أعرف كم السعر عندكم حالياً، ونوع الفيلم المستخدم ومدة الضمان؟ وكم يحتاج التركيب تقريباً؟

and extract structured information including:

- customer name if known
- vehicle make
- vehicle model
- model year
- requested service
- full / partial
- matte / gloss if present
- branch / location if present
- desired timing if present
- individual customer questions

Expected questions in the example:

- price
- film type / brand
- warranty
- installation duration

Do not hard-code Nissan Patrol.

Design it to support:

- multiple vehicles;
- multiple years;
- different services;
- different packages;
- different businesses.

Document:

- extraction method;
- expected accuracy;
- uncertainty handling;
- fallback behavior;
- storage design.

---

# 11. Critical technical spike 2 — Question Completion Check

This is one of the core differentiating features.

Prove whether the system can:

1. identify the customer's individual questions;
2. retain those questions as structured state;
3. observe the salesperson's later response;
4. determine for each question whether it is:
   - answered,
   - partially answered,
   - unanswered;
5. prompt or alert the salesperson when something important remains unanswered.

Example:

Customer asks:

- price
- film type
- warranty
- installation duration

Salesperson replies with:

- American self-healing film
- 7-year warranty
- installation takes 2 days

Expected result:

- Film type: answered
- Warranty: answered
- Installation duration: answered
- Price: **unanswered**

Expected assistance:

> Customer is still waiting for the price.

Determine whether this is best implemented using:

- native GHL AI;
- workflows;
- salesperson reply triggers;
- webhooks/API;
- or an external helper service.

Do not weaken this feature simply to remain inside GHL.

Prove the implementation path with a minimal working spike.

---

# 12. Critical technical spike 3 — Meaningful Response SLA

The project has observed a real case where:

- an automated acknowledgement arrived immediately;
- the first useful human response arrived approximately 5.5 hours later.

The product must distinguish:

> **Automated acknowledgement time**

from:

> **Meaningful response time**

A generic message must not stop the meaningful-response timer merely because something was sent.

Design and prove logic for:

- SLA start time;
- automated acknowledgement detection;
- meaningful-response classification;
- salesperson warning;
- supervisor escalation;
- configurable thresholds;
- SLA breach;
- reporting.

Example dashboard result:

> Automated acknowledgement: 3 sec  
> Meaningful response: 5h 26m

Determine:

- whether AI classification is required;
- where classification should run;
- how reliable it is;
- what fallback exists.

---

# 13. Salesperson Copilot architecture

Design a Sales Copilot that assists the salesperson rather than trying to replace them.

The system may assist with:

- customer-context extraction;
- vehicle/service extraction;
- unanswered questions;
- qualification prompts;
- next best question;
- package suggestions;
- social proof suggestions;
- financing prompts;
- objection recognition;
- next actions;
- follow-up reminders.

Humans remain responsible for:

- trust;
- negotiation;
- judgment;
- product comparison;
- objection handling;
- closing.

Design the architecture to allow stronger automation later without requiring a rebuild.

---

# 14. Pipeline architecture

Review and finalize the MVP opportunity stages.

Current proposal:

- New Enquiry
- Qualified
- Quote Sent
- Follow-up
- Appointment Booked
- Deposit / Confirmed
- Vehicle Received
- Completed / Won
- Lost

Refine only where justified.

Define for every stage:

- entry conditions;
- exit conditions;
- required fields;
- automated actions;
- human actions;
- SLA implications;
- reporting implications.

---

# 15. Data model

Define the exact MVP data model.

At minimum consider:

## Contact

- customer name
- phone
- language
- city
- consent
- opt-out status

## Vehicle

- make
- model
- year
- trim if useful

## Enquiry

- requested service
- full / partial
- finish
- film preference
- branch
- desired date
- lead source
- campaign
- questions asked

## Opportunity

- salesperson
- branch
- stage
- quote value
- quote date
- last meaningful response
- next follow-up
- lost reason
- booked revenue

## AI / Quality metadata

- unanswered questions
- question-completion status
- meaningful-response status
- SLA status
- objection category
- AI confidence where useful

For each field decide whether it belongs in:

- contact fields;
- opportunity fields;
- custom objects;
- tags;
- calculated/external data;
- another structure.

---

# 16. Follow-up architecture

Design configurable quote-follow-up behavior.

Support:

- follow-up after quotation;
- follow-up after customer silence;
- cancellation/suppression after customer reply;
- manual override;
- salesperson ownership;
- escalation if appropriate.

Do not hard-code one universal timing sequence.

Provide sensible demo defaults.

Avoid spammy behavior.

---

# 17. Lost-reason classification

Design categories such as:

- price
- competitor
- timing
- location
- no response
- product concern
- warranty preference
- financing
- no immediate need
- other

Determine:

- whether AI can infer the reason;
- when human confirmation is required;
- how correction works;
- how data becomes reportable.

---

# 18. Manager dashboard architecture

The manager dashboard is a major client-facing sales tool.

Design KPI cards and views for:

- new enquiries
- enquiries awaiting meaningful response
- average meaningful response time
- open quote value
- quotes needing follow-up
- booked revenue
- lost opportunity value
- conversion rate
- salesperson conversion
- branch conversion
- lead-source conversion
- lost reasons
- SLA breaches

Example:

### Today

- New Leads: 23
- Avg. Meaningful Response: 7 min
- Open Quotations: SAR 84,600
- Booked Today: SAR 21,400

### Needs Attention

- 3 leads awaiting meaningful response
- 6 quotations need follow-up
- 2 customers have unanswered questions

### Sales Team

| Salesperson | Leads | Avg Response | Quotes | Booked |
|---|---:|---:|---:|---:|
| Mohammed | 21 | 6m | 14 | SAR 28,500 |
| Khalid | 18 | 23m | 10 | SAR 16,900 |
| Faisal | 12 | 9m | 8 | SAR 14,200 |

### Lead Sources

- Instagram
- Snapchat
- Google
- Direct WhatsApp

with leads, bookings and revenue.

---

# 19. Client-facing UI/UX architecture

The MVP must be visually strong enough to impress paying business owners.

The client experience should feel like:

> **our automotive sales platform**

not:

> **a standard GoHighLevel account with different branding**

Design the information architecture and technical implementation for these screens.

---

## Screen 1 — Executive Dashboard

Purpose:

> give the owner an immediate understanding of revenue performance and sales quality.

Emphasize:

- revenue;
- open opportunities;
- response performance;
- urgent attention;
- team performance.

---

## Screen 2 — Lead / Sales Copilot

This should likely be the hero product screen.

Example:

### Ahmed

Nissan Patrol 2025

**Service:** Full PPF  
**Finish:** Matte  
**Potential Value:** SAR 5,996  
**Stage:** Quote Sent  
**Salesperson:** Mohammed

### Customer Asked

- ✓ Price
- ✓ Film type
- ✓ Warranty
- ⚠ Installation duration

### AI Suggestion

> Ahmed is still waiting for installation duration. Consider answering this before the opportunity goes idle.

Also consider:

- conversation history;
- next action;
- follow-up;
- source;
- package;
- internal notes;
- SLA state.

---

## Screen 3 — Attention Center

Example:

> 🔴 Nissan Patrol 2025  
> No meaningful response for 47 minutes

> 🟠 BMW X5  
> SAR 7,500 quotation  
> No customer response for 26 hours

> 🟡 Range Rover  
> Customer asked 4 questions  
> 1 unanswered

Design:

- priority;
- reason;
- salesperson;
- opportunity value;
- elapsed time;
- recommended action.

---

## Screen 4 — Opportunities

Design a polished Kanban or equivalent pipeline view.

Cards should display useful automotive context:

- vehicle;
- service;
- value;
- age;
- salesperson;
- SLA/attention state.

---

## Screen 5 — Sales Team

Show:

- salesperson;
- assigned leads;
- response time;
- quotes;
- bookings;
- booked revenue;
- conversion;
- SLA breaches.

---

## Screen 6 — Analytics

Show:

- source;
- lead count;
- quotes;
- bookings;
- revenue;
- conversion;
- lost reasons;
- useful trends.

---

# 20. Native GHL versus custom frontend

For every major function classify it as:

### A. Native HighLevel

### B. White-labeled/restyled HighLevel

### C. Embedded custom UI

### D. Separate custom application

Avoid rebuilding administrative functionality when native GHL is sufficient.

It is acceptable to leave the following native where appropriate:

- workflow configuration;
- automation editor;
- calendars;
- advanced CRM administration;
- template management;
- system configuration.

Spend custom development effort on:

- daily salesperson experience;
- manager visibility;
- Sales Copilot;
- Attention Center;
- executive dashboard;
- analytics.

---

# 21. UI technical architecture

Define:

- frontend stack;
- framework;
- component architecture;
- routing;
- data-fetching strategy;
- authentication;
- GHL API integration;
- caching;
- state management;
- error handling;
- loading states;
- empty states;
- responsive behavior;
- Arabic/English support;
- RTL support;
- date/time formatting;
- SAR currency formatting;
- role-based visibility.

Prefer a fast, maintainable MVP.

Avoid over-engineering.

---

# 22. Visual design direction

Define a coherent visual system appropriate for:

- premium automotive businesses;
- Saudi business owners;
- modern B2B SaaS.

The visual style should feel:

- premium;
- professional;
- clean;
- modern;
- confident;
- restrained.

Avoid:

- excessive gradients;
- gaming aesthetics;
- default Bootstrap/admin appearance;
- clutter;
- inconsistent spacing.

Define:

- typography hierarchy;
- spacing;
- cards;
- iconography;
- charts;
- tables;
- Kanban;
- attention states;
- AI/copilot treatment;
- empty states;
- RTL behavior.

Keep it realistic for Phase 2 to implement quickly.

---

# 23. Demo data design

Design a realistic seeded demo dataset using vehicles such as:

- Nissan Patrol 2025
- Toyota Land Cruiser
- BMW X5
- Range Rover
- Mercedes G-Class

Services such as:

- Full PPF
- Front PPF
- Matte PPF
- Tint
- Ceramic Coating
- Premium Detailing

Use realistic SAR values.

Include examples of:

- good lead handling;
- SLA breach;
- unanswered question;
- follow-up required;
- booked opportunity;
- lost opportunity.

Base scenarios on actual patterns documented in:

`project-knowledge/05-whatsapp-mystery-shopping-results.md`

without exposing competitor identities unnecessarily in the final demo.

---

# 24. Acceptance criteria

Define explicit acceptance criteria for all major capabilities.

At minimum include:

## Context Extraction

A realistic Arabic enquiry correctly produces:

- vehicle;
- year;
- service;
- questions.

## Redundant Question Prevention

If the customer already supplied vehicle and service, the system should not unnecessarily ask for them again.

## Question Completion

If the customer asks four questions and the salesperson answers three, the missing question is correctly identified.

## Meaningful Response

A generic autoresponder does not incorrectly satisfy the meaningful-response SLA.

## Follow-Up

A quote with no response enters the configured follow-up process.

## Stop on Reply

Customer reply prevents inappropriate future automated follow-up.

## Dashboard

Manager can identify:

- leads requiring attention;
- open quote value;
- response performance;
- conversion.

## UI

The client-facing demo must look polished enough to show to a paying Saudi automotive-protection business owner without exposing an unfinished developer interface.

---

# 25. Cost and dependency analysis

Document expected costs and dependencies.

Include:

- required HighLevel plan;
- WhatsApp costs;
- AI usage;
- premium workflow actions;
- external AI/API if needed;
- frontend hosting;
- helper-service hosting;
- database if needed;
- domain if needed;
- authentication;
- likely pilot operating cost.

Classify every item as:

### Required now

### Required for live pilot

### Optional later

Avoid unnecessary paid components.

Do not purchase anything.

---

# 26. Security and privacy

Design with:

- secrets outside Git;
- environment variables;
- least privilege;
- role-based access;
- consent fields;
- opt-out;
- Do Not WhatsApp;
- Saudi PDPL considerations;
- auditability where practical.

No production credentials should ever enter the repository.

---

# 27. Phase 1 output file

Create:

`project-knowledge/10-ghl-mvp-architecture-ui-and-build-specification.md`

It must include:

1. executive architecture summary
2. validated product requirements
3. native GHL capability matrix
4. GHL vs custom frontend architecture
5. external helper requirements, if any
6. data model
7. pipeline
8. custom fields
9. tags
10. workflows
11. triggers
12. AI extraction design
13. Question Completion Check design
14. Meaningful Response SLA design
15. follow-up logic
16. lost-reason logic
17. dashboard specification
18. Sales Copilot specification
19. Attention Center specification
20. Opportunities specification
21. Sales Team specification
22. Analytics specification
23. API/integration plan
24. authentication plan
25. Arabic/English/RTL strategy
26. visual design system
27. demo dataset
28. technical spike results
29. limitations
30. cost dependencies
31. security/privacy considerations
32. complete Phase 2 implementation sequence
33. acceptance criteria
34. blocking dependencies requiring my action

Do not leave important Phase 2 decisions implicit.

---

# 28. Update the project context

At the end of Phase 1, update:

`project-knowledge/00-project-context-and-current-status.md`

Record:

- architecture decisions;
- verified HighLevel capabilities;
- technical-spike results;
- whether external services are required;
- UI architecture;
- cost implications;
- risks;
- blockers;
- Phase 2 implementation plan;
- newly created files.

Preserve historical context.

Do not rewrite the project's earlier research as if it never happened.

---

# 29. Repository documentation

Update `README.md` if needed so that a future engineer or agent can quickly understand:

- what the repository contains;
- where project knowledge lives;
- what Phase 1 produced;
- where implementation will go;
- how environment variables are handled;
- how to start Phase 2.

Keep README concise and operational.

---

# 30. Phase 1 completion condition

Phase 1 is complete only when:

- current GHL capabilities have been verified;
- the critical feasibility spikes have been performed;
- Question Completion has a proven implementation path;
- Meaningful Response SLA has a proven implementation path;
- the native GHL/custom frontend boundary is decided;
- the UI architecture is decided;
- the data model is fully specified;
- workflows are fully specified;
- cost implications are known;
- acceptance criteria exist;
- Phase 2 has a clear implementation sequence;
- `project-knowledge/10-ghl-mvp-architecture-ui-and-build-specification.md` exists;
- `project-knowledge/00-project-context-and-current-status.md` is updated;
- all intended changes are committed to `phase-1-architecture`;
- the Git working tree is clean.

Do not continue into the full production build during this phase unless a small prototype is required to prove feasibility.

Prioritize:

> architecture correctness + technical proof + client-facing product quality

over routine implementation.

---

# 31. Final handoff

When finished, provide a concise handoff summary containing:

- branch name;
- important commits;
- files created;
- files modified;
- technical spikes performed;
- what was proven;
- unresolved limitations;
- external actions I must take;
- whether Phase 2 is ready to begin.

Do not simply say "done."

The handoff must make it easy for Phase 2 to continue directly from the repository.

Proceed autonomously until one of the explicitly defined blocking conditions requires my action.
