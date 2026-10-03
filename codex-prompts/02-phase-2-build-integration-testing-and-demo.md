You are continuing an existing GitHub-backed Codex project for a Saudi automotive sales-conversion platform.

This is:

> **Phase 2 — implementation, integration, testing, visual polish, and client-demo preparation**

The GitHub repository is the **persistent project workspace and source of truth**.

Do not depend on files stored on my local PC.

All code, configuration-as-code where practical, tests, documentation, architecture decisions, demo assets, and project-status updates must remain in this repository.

---

# 1. Git and branch preparation

Before doing implementation work:

1. inspect the repository;
2. inspect the current Git branch and recent commits;
3. confirm that Phase 1 has completed successfully;
4. confirm that the following exists:

`project-knowledge/10-ghl-mvp-architecture-ui-and-build-specification.md`

5. confirm that:

`project-knowledge/00-project-context-and-current-status.md`

contains the Phase 1 architecture and technical-spike results.

Phase 1 should have worked on:

`phase-1-architecture`

For Phase 2, work on:

`phase-2-mvp-build`

If `phase-2-mvp-build` does not exist, create it from the most appropriate commit that contains all completed Phase 1 work.

If Phase 1 has already been merged into the default branch, branch from the updated default branch.

If Phase 1 has not been merged but `phase-1-architecture` clearly contains the approved/latest project state, branch Phase 2 from that completed Phase 1 state.

Do not lose or overwrite Phase 1 work.

Do not merge into the default branch unless explicitly instructed.

Do not rewrite Git history.

---

# 2. Git workflow during Phase 2

Use logical commits throughout implementation.

Avoid one giant final commit.

Reasonable commit boundaries may include:

- project/app scaffolding
- GHL integration layer
- data model and test fixtures
- context extraction
- Question Completion Check
- Meaningful Response SLA
- pipeline/follow-up automation
- manager dashboard
- Sales Copilot
- Attention Center
- analytics
- responsive/RTL polish
- automated tests
- demo data
- deployment configuration
- documentation and final handoff

Keep commit messages clear.

At completion:

- all intended files should be committed;
- temporary/debug files should be removed;
- tests should pass where applicable;
- the working tree should be clean;
- the branch should be ready for review.

---

# 3. Repository structure

Preserve the established project structure.

It should resemble:

```text
automotive-sales-ai-mvp/
├── project-knowledge/
│   ├── 00-project-context-and-current-status.md
│   ├── 01-initial-research.md
│   ├── ...
│   ├── 09-client-facing-ui-and-product-experience-strategy.md
│   └── 10-ghl-mvp-architecture-ui-and-build-specification.md
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

You may add directories that are genuinely required.

Do not move or rename the numbered `project-knowledge/` files unless there is a strong technical reason.

Preserve project chronology.

---

# 4. Secrets and repository safety

Never commit:

- API keys;
- passwords;
- GHL access tokens;
- private integration tokens;
- Meta credentials;
- WhatsApp tokens;
- database passwords;
- OAuth secrets;
- browser cookies;
- private certificates;
- customer credentials.

Use Codex Cloud/environment secrets or another secure runtime secret mechanism.

Maintain:

`.env.example`

with variable names and safe example values only.

Keep sensitive files excluded in `.gitignore`.

At minimum review exclusions such as:

```text
.env
.env.local
.env.*.local
*.pem
*.key
secrets/
credentials/
```

Do not place secrets in Markdown files.

---

# 5. Read the project state before building

Start by reading:

1. `project-knowledge/00-project-context-and-current-status.md`
2. `project-knowledge/10-ghl-mvp-architecture-ui-and-build-specification.md`

Then read any earlier project-knowledge files required to understand a feature or validation scenario.

Relevant historical files include:

- `05-whatsapp-mystery-shopping-results.md`
- `06-post-enquiry-analysis-and-product-validation.md`
- `08-mvp-definition-and-customer-validation-plan.md`
- `09-client-facing-ui-and-product-experience-strategy.md`

Do not repeat completed market research.

Do not reopen product strategy merely because another implementation seems interesting.

Treat `10` as the primary technical implementation specification unless actual testing proves that a documented assumption is incorrect.

When implementation reality conflicts with Phase 1:

1. verify the issue;
2. choose the smallest sensible correction;
3. document the deviation;
4. continue.

Do not stop for routine approval.

---

# 6. Main objective

Build the MVP defined in:

`project-knowledge/10-ghl-mvp-architecture-ui-and-build-specification.md`

The final result must be:

> **a working, visually polished, client-demonstrable product**

not merely:

- configuration notes;
- mockups;
- isolated proofs of concept;
- unfinished frontend screens;
- or undocumented GHL workflows.

The core product promise remains:

> **Never let a valuable WhatsApp lead receive an irrelevant answer, wait unnoticed, or disappear without structured follow-up.**

The management proposition remains:

> **Make every salesperson perform more consistently like your best salesperson, while AI makes sure nothing gets missed.**

---

# 7. Product positioning

Do not present the product as:

- GoHighLevel;
- a GHL reseller account;
- a generic CRM;
- a generic chatbot;
- a marketing agency;
- a workshop ERP.

GoHighLevel is infrastructure.

The client should experience:

> **a dedicated automotive sales-conversion product**

initially optimized for:

- PPF;
- tint;
- ceramic coating;
- wrapping;
- premium detailing.

Use neutral temporary branding if no final product name exists.

Do not stop implementation waiting for branding decisions.

---

# 8. Autonomy

Proceed through the implementation without asking me for ordinary engineering decisions.

You are authorized to:

- choose appropriate libraries;
- create project structure;
- refactor code;
- create tests;
- create realistic demo data;
- make normal UI decisions;
- fix bugs;
- adjust small technical details;
- create migrations/configuration;
- improve accessibility;
- improve responsive behavior;
- optimize code where appropriate.

Only stop and ask me if a genuine external blocker requires my action, such as:

- login/authentication I must perform;
- MFA;
- Meta authorization;
- WhatsApp authorization;
- paid plan upgrade;
- subscription purchase;
- contractual acceptance;
- production account access;
- irreversible production action;
- a charge;
- a credential only I can obtain.

If one feature is blocked by such an action:

> continue completing all independent work first.

Do not leave the entire phase unfinished because one integration is blocked.

---

# 9. Implementation priority

Follow the dependency order in `10`.

Unless Phase 1 specifies otherwise, prioritize:

1. project/runtime scaffolding
2. GHL integration foundation
3. data structures
4. realistic demo/test fixtures
5. context extraction
6. Question Completion Check
7. Meaningful Response SLA
8. opportunity/pipeline behavior
9. salesperson assistance
10. follow-up logic
11. lost-reason classification
12. lead-source attribution
13. Executive Dashboard
14. Sales Copilot
15. Attention Center
16. Opportunities
17. Sales Team
18. Analytics
19. RTL/responsive/accessibility polish
20. end-to-end testing
21. reusable customer deployment method
22. demo preparation
23. final project documentation

Prioritize differentiated value over feature count.

---

# 10. GoHighLevel implementation

Implement the native HighLevel components specified in `10`.

These may include:

- contacts;
- opportunities;
- pipelines;
- custom fields;
- tags;
- custom values;
- workflows;
- workflow triggers;
- AI actions;
- webhooks;
- API integrations;
- salesperson assignment;
- follow-up logic;
- stop-on-reply behavior;
- lost reasons;
- SLA-related fields;
- snapshot-ready configuration.

Use the actual Phase 1 architecture rather than assumptions from this prompt.

Where safe automation or API configuration is possible, use it.

Where HighLevel requires browser interaction, use the available environment if appropriate.

Where my manual authentication is genuinely required, document the exact step.

---

# 11. Context extraction

Implement the proven Phase 1 design for converting free-form Arabic/English enquiries into structured sales context.

At minimum support:

- customer name when known;
- vehicle make;
- vehicle model;
- model year;
- service;
- full / partial service;
- matte / gloss where present;
- branch/location where present;
- requested timing where present;
- customer questions.

Required test example:

> عندي نيسان باترول 2025 وأفكر أركب حماية PPF كاملة للسيارة. ممكن أعرف كم السعر عندكم حالياً، ونوع الفيلم المستخدم ومدة الضمان؟ وكم يحتاج التركيب تقريباً؟

Expected structured interpretation includes:

- Nissan;
- Patrol;
- 2025;
- Full PPF;
- price question;
- film question;
- warranty question;
- installation-duration question.

Do not hard-code this vehicle.

Test additional vehicles/services.

---

# 12. Redundant-question prevention

The system should use information the customer already supplied.

Example:

If the customer already states:

> Nissan Patrol 2025 + Full PPF

the automation/copilot should not unnecessarily respond with:

> What car do you have?  
> What service are you interested in?

Implement this behavior where supported by the Phase 1 architecture.

Include it in tests and demo data.

---

# 13. Question Completion Check

Implement the Phase 1 proven architecture.

Required behavior:

1. identify individual customer questions;
2. retain them in structured state;
3. inspect subsequent salesperson responses;
4. classify each question as:
   - answered;
   - partially answered;
   - unanswered;
5. surface missing information to the salesperson.

Required scenario:

Customer asks:

- price;
- film;
- warranty;
- installation duration.

Salesperson answers:

- American self-healing film;
- 7-year warranty;
- 2-day installation.

Expected:

- film: answered;
- warranty: answered;
- installation duration: answered;
- price: **unanswered**.

Expected UI:

> **1 question still needs an answer**

and:

> **Customer is still waiting for the price.**

This capability must be visible in the client-facing product, not hidden only in logs.

---

# 14. Meaningful Response SLA

Implement separate timing for:

### Automated acknowledgement

and:

### Meaningful response

A generic immediate autoresponder must not automatically satisfy the meaningful-response SLA.

Required test scenario:

Customer sends a PPF enquiry.

System sends an immediate generic message.

No relevant answer is provided.

Expected:

> **Awaiting meaningful response**

and the SLA timer continues.

When an appropriate human response later arrives, meaningful-response timing should stop.

Track/display where architecturally appropriate:

- enquiry time;
- acknowledgement time;
- meaningful response time;
- elapsed time;
- warning state;
- breach state.

Support configurable warning/breach thresholds.

---

# 15. Salesperson Copilot

Implement the Sales Copilot specified in `10`.

It should assist with:

- customer context;
- vehicle/service information;
- missing questions;
- suggested next action;
- useful qualification question;
- potential objection;
- follow-up timing;
- relevant package or evidence where supported.

Do not attempt to replace human judgment.

Humans retain responsibility for:

- trust;
- negotiation;
- product explanation;
- objections;
- pricing discretion;
- closing.

---

# 16. Pipeline implementation

Implement the pipeline defined in Phase 1.

Likely stages may include:

- New Enquiry
- Qualified
- Quote Sent
- Follow-up
- Appointment Booked
- Deposit / Confirmed
- Vehicle Received
- Completed / Won
- Lost

Use the actual finalized stages from `10`.

Implement appropriate:

- required data;
- transitions;
- automation;
- reporting;
- ownership;
- next-action behavior.

---

# 17. Follow-up automation

Implement follow-up behavior from `10`.

Required behavior:

- quote sent;
- customer remains silent;
- follow-up becomes due;
- salesperson/system is prompted or acts as designed;
- customer replies;
- future inappropriate automated follow-up stops.

Support:

- configurable timing;
- manual override;
- owner/salesperson assignment;
- safe stop-on-reply behavior.

Avoid spammy sequences.

---

# 18. Lost-reason classification

Implement the approved model.

Likely reasons include:

- price;
- competitor;
- timing;
- location;
- no response;
- product concern;
- warranty preference;
- financing;
- no immediate need;
- other.

Use AI where Phase 1 recommends it.

Allow human correction where appropriate.

Make lost reasons reportable.

---

# 19. Lead-source attribution

Implement the most practical MVP attribution architecture.

Support sources such as:

- Instagram;
- Snapchat;
- Google;
- Direct WhatsApp;
- Website;
- Referral.

Where practical show:

> Source → Leads → Quotes → Bookings → Revenue

If some live advertising-platform integration is outside MVP scope:

- preserve correct data structures;
- use credible seeded/demo data;
- clearly document the production integration required later.

Do not falsely represent mocked attribution as a live integration.

---

# 20. Custom frontend

Implement the client-facing frontend specified in:

- `09-client-facing-ui-and-product-experience-strategy.md`
- `10-ghl-mvp-architecture-ui-and-build-specification.md`

The frontend should feel like:

> **our own premium automotive sales platform**

not a default admin template.

If Phase 1 selected Next.js/React or another stack, follow that decision unless implementation proves it unsuitable.

The frontend should consume real integration data where practical and use clearly identified seeded/demo data where live integration is not yet available.

---

# 21. Executive Dashboard

Build a polished owner/manager dashboard.

Prioritize business outcomes.

Show metrics such as:

- New Leads
- Avg. Meaningful Response
- Open Quotations
- Booked Revenue
- Conversion
- Quotes Needing Follow-Up
- SLA Breaches

Include:

## Needs Attention

Examples:

- leads awaiting meaningful response;
- quotations needing follow-up;
- customers with unanswered questions.

## Team Performance

Meaningful comparison between salespeople.

## Lead Sources

Leads/bookings/revenue by source where available.

The first screen should immediately demonstrate commercial value.

---

# 22. Lead / Sales Copilot screen

This should be a hero screen.

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

Also show relevant:

- conversation history;
- source;
- SLA;
- next action;
- follow-up;
- package;
- notes;
- timeline.

The differentiated intelligence must be obvious without explanation.

---

# 23. Attention Center

Build a dedicated action-oriented interface.

Example:

> 🔴 Nissan Patrol 2025  
> No meaningful response for 47 minutes

> 🟠 BMW X5  
> SAR 7,500 quotation  
> No customer response for 26 hours

> 🟡 Range Rover  
> Customer asked 4 questions  
> 1 unanswered

For each attention item consider:

- severity;
- reason;
- salesperson;
- opportunity value;
- elapsed time;
- recommended next action.

Make it operationally useful, not merely decorative.

---

# 24. Opportunities

Build a polished opportunity/pipeline experience.

Use the architecture in `10`.

Cards should expose useful context such as:

- customer/vehicle;
- service;
- value;
- salesperson;
- age;
- attention/SLA state.

Avoid excessive information.

Use clear visual hierarchy.

---

# 25. Sales Team

Build a manager-oriented team-performance view.

Include metrics such as:

- assigned leads;
- average meaningful-response time;
- quotes;
- bookings;
- booked revenue;
- conversion rate;
- SLA breaches.

Make comparisons easy to understand.

---

# 26. Analytics

Build useful analytics around:

- lead sources;
- enquiries;
- quotations;
- bookings;
- booked revenue;
- conversion;
- lost reasons;
- trends.

Use restrained, readable visualizations.

Do not overload the page with charts merely for appearance.

---

# 27. Visual-quality acceptance criterion

This is mandatory.

The MVP is **not finished simply because the workflows work**.

It must also be:

> **visually polished enough to show to a paying Saudi automotive business owner without exposing unfinished/developer-quality UI.**

The design should feel:

- premium;
- modern;
- professional;
- clean;
- confident;
- restrained;
- automotive-relevant.

Avoid:

- generic admin-template appearance;
- excessive gradients;
- gaming visuals;
- random colors;
- clutter;
- broken spacing;
- placeholder icons;
- obvious debug controls;
- inconsistent typography.

---

# 28. Design system

Implement the design direction specified in `10`.

Use consistent:

- typography;
- spacing;
- containers;
- cards;
- buttons;
- tables;
- navigation;
- badges;
- icons;
- charts;
- Kanban treatment;
- AI/copilot elements;
- attention states.

Do not allow each screen to look like a different product.

---

# 29. Arabic, English and RTL

Implement the Phase 1 language strategy.

At minimum:

- Arabic customer content must render correctly;
- RTL text must display correctly;
- Arabic strings must not break layouts;
- English management UI must remain polished;
- SAR formatting must be correct;
- dates/times should be appropriate for Saudi usage;
- RTL components must be structurally sound.

If full localization is not part of MVP, do not pretend it is complete.

Preserve an architecture that allows it later.

---

# 30. Responsive behavior

Desktop/laptop presentation quality is especially important for client demonstrations.

Also ensure reasonable behavior on:

- tablet;
- mobile.

Salesperson-oriented screens should be particularly usable on mobile.

Do not sacrifice desktop dashboard quality for extreme small-screen optimization.

---

# 31. Loading, empty and error states

Implement polished states for:

- loading;
- zero leads;
- no attention items;
- no quotes;
- empty analytics;
- unavailable GHL connection;
- API error;
- missing conversation;
- missing optional data.

No client-facing screen should appear broken when data is unavailable.

---

# 32. Demo dataset

Create and commit safe demo/test data or seed scripts as appropriate.

Do not use private real customer data.

Use realistic examples such as:

### Vehicles

- Nissan Patrol 2025
- Toyota Land Cruiser
- BMW X5
- Range Rover
- Mercedes G-Class

### Services

- Full PPF
- Front PPF
- Matte PPF
- Tint
- Ceramic Coating
- Premium Detailing

Use realistic SAR values.

Include scenarios showing:

- strong salesperson performance;
- unanswered question;
- SLA breach;
- follow-up required;
- booked opportunity;
- lost opportunity;
- strong conversion;
- weak response performance.

The dashboard should feel populated and credible.

---

# 33. Mystery-shopping test fixtures

Use patterns from:

`project-knowledge/05-whatsapp-mystery-shopping-results.md`

Create anonymized demo/test scenarios inspired by:

- context-blind automation;
- generic acknowledgement followed by delayed meaningful response;
- incomplete multi-question response;
- template-heavy response;
- strong salesperson qualification and follow-up.

Do not expose competitor names in the client-facing demo unless there is a legitimate internal reason.

---

# 34. Testing

Implement automated testing where practical.

Test at minimum:

- data parsing;
- context extraction;
- question classification;
- question-completion logic;
- meaningful-response classification;
- SLA calculation;
- follow-up state;
- stop-on-reply;
- lost-reason classification;
- data mappings;
- API integration wrappers;
- important frontend components/states.

Also perform manual/end-to-end validation.

Do not claim tests passed unless they actually did.

---

# 35. Mandatory end-to-end scenarios

Validate these scenarios.

## A — Context Extraction

Arabic PPF enquiry produces correct vehicle/year/service/questions.

## B — Redundant Question Prevention

Known vehicle/service is not unnecessarily requested again.

## C — Question Completion

Customer asks four questions.

Salesperson answers three.

System identifies the missing question.

## D — Generic Auto Reply

Generic acknowledgment occurs immediately.

Meaningful-response SLA continues.

## E — Meaningful Response

Useful salesperson response stops meaningful-response timer appropriately.

## F — Quote Follow-Up

Quote sent.

Customer silent.

Follow-up becomes due.

## G — Stop on Reply

Customer replies.

Future inappropriate automatic follow-up is suppressed.

## H — Manager Attention

SLA breach/unanswered question appears in Attention Center.

## I — Revenue Visibility

Manager can see:

- open quote value;
- booked revenue;
- salesperson performance.

## J — Mobile/RTL

Representative Arabic customer content remains usable in responsive layouts.

---

# 36. External helper service

If Phase 1 concluded that a helper service is needed:

implement it exactly as narrowly as possible.

Include:

- clear responsibilities;
- APIs/interfaces;
- configuration;
- tests;
- error handling;
- logging;
- `.env.example`;
- local run instructions;
- deployment instructions.

Do not accidentally create a second CRM.

HighLevel remains the main system of record unless `10` explicitly states otherwise.

---

# 37. Database

Only use an external database if Phase 1 determined it is required.

If used:

- create schema/migrations;
- document ownership of data;
- avoid duplication of GHL data without reason;
- use seed data safely;
- keep credentials out of Git;
- document backup/retention considerations.

Do not add infrastructure without justification.

---

# 38. Deployment

Implement a simple deployment path for the demo environment.

Use the hosting architecture from `10`.

Prefer low-complexity deployment.

If deployment requires me to authorize an external account:

- prepare everything possible first;
- document the exact required step;
- ask only when necessary.

Do not purchase hosting without approval.

Where possible provide:

- build instructions;
- deployment configuration;
- environment-variable list;
- health-check guidance.

---

# 39. Reusable deployment / GHL snapshot

Prepare the system for repeated deployment to pilot customers.

If Phase 1 selected GHL Snapshots:

- ensure the source sub-account is clean;
- create the snapshot where permissions allow;
- document snapshot contents;
- document post-import setup;
- document customer-specific values that must not be copied.

Examples may include:

- WhatsApp number;
- staff users;
- branch names;
- business name;
- business hours;
- package/pricing values;
- Meta credentials.

Goal:

> deploy the next automotive customer with minimal setup effort.

---

# 40. Demo environment

Prepare a demo that can be shown without developer tooling.

The customer should not need to see:

- terminal windows;
- source code;
- database consoles;
- raw API tools;
- debug logs.

The visible experience should be the polished product.

If a manual setup step is unavoidable before a demo, document it clearly.

---

# 41. Client demo flow

Prepare a roughly 10–15 minute story.

Recommended sequence:

### 1. Incoming Enquiry

Show an Arabic PPF enquiry.

### 2. Automatic Understanding

Show extraction of:

- vehicle;
- year;
- service;
- questions.

### 3. Sales Copilot

Show unanswered-question intelligence.

### 4. Meaningful Response SLA

Show why an irrelevant generic response does not hide a slow sales team.

### 5. Attention Center

Show what requires action right now.

### 6. Opportunities

Show open quotation value and pipeline.

### 7. Follow-Up

Show how quotes are prevented from disappearing.

### 8. Dashboard

Show:

- revenue;
- response quality;
- team performance;
- source attribution.

End the demo on:

> **business value and recovered revenue**

rather than technical architecture.

---

# 42. Client demo guide

Create:

`project-knowledge/12-client-demo-script.md`

Include:

- exact demo sequence;
- screens to open;
- key talking points;
- what each feature proves;
- business-value statement;
- likely owner/manager questions;
- concise suggested answers;
- features not to overclaim.

Keep it operational enough that another person could deliver the demo.

---

# 43. Build and test report

Create:

`project-knowledge/11-ghl-mvp-build-and-test-report.md`

This report must state:

1. what was actually built;
2. GHL configuration implemented;
3. frontend implemented;
4. helper service implemented, if any;
5. integrations implemented;
6. environment requirements;
7. automated tests;
8. manual/end-to-end tests;
9. test results;
10. screenshots or evidence where practical;
11. limitations;
12. mocked/demo-only functions;
13. live-ready functions;
14. costs and usage dependencies;
15. required HighLevel plan;
16. remaining manual configuration;
17. security/privacy considerations;
18. pilot-readiness assessment;
19. unresolved blockers;
20. exact actions required from me;
21. recommended first-client pilot approach.

Do not describe unbuilt features as complete.

---

# 44. Update the main project context

At completion update:

`project-knowledge/00-project-context-and-current-status.md`

Record:

- what is actually implemented;
- final architecture;
- deviations from Phase 1;
- test results;
- UI status;
- deployment status;
- demo readiness;
- pilot readiness;
- remaining blockers;
- external services in use;
- recurring costs;
- new files;
- recommended next step.

Preserve earlier history and chronology.

Do not erase how decisions were reached.

---

# 45. README

Update `README.md` so that another engineer or future Codex session can quickly understand:

- what the product is;
- repository structure;
- how to run the app;
- how to run tests;
- how environment variables work;
- how GHL integration works at a high level;
- where project knowledge lives;
- how to launch the demo;
- current project status.

Keep sensitive details out of README.

---

# 46. Documentation inside the codebase

Document only what is useful.

Prefer:

- clear names;
- small modules;
- README/setup docs;
- comments where reasoning is non-obvious.

Avoid excessive generated documentation that creates maintenance noise.

---

# 47. Security review

Before completion, perform a repository safety check.

Verify:

- no secrets are committed;
- no real customer data is committed;
- `.gitignore` is appropriate;
- `.env.example` contains no credentials;
- sensitive logs are absent;
- API error output does not leak secrets;
- production-only actions are protected;
- demo mode is clearly distinguishable where relevant.

If a secret was accidentally created in an uncommitted file, remove it safely.

If a secret has already entered Git history, flag this clearly instead of assuming deletion of the current file is sufficient.

---

# 48. UI quality review

Perform a deliberate visual QA pass.

Review all primary screens for:

- alignment;
- spacing;
- typography;
- visual hierarchy;
- responsiveness;
- truncation;
- long Arabic text;
- empty states;
- tables;
- charts;
- cards;
- mobile behavior;
- RTL behavior;
- loading behavior;
- error behavior.

Fix obvious visual issues before declaring completion.

The demo must not feel like a first-pass prototype.

---

# 49. Phase 2 completion criteria

Phase 2 is complete only when the following are true.

## Core functionality

- context extraction works;
- redundant-question prevention works at the designed level;
- pipeline works;
- Question Completion Check works;
- Meaningful Response SLA works;
- attention logic works;
- follow-up logic works;
- stop-on-reply works;
- lost-reason handling works;
- manager metrics work at the designed MVP level.

## UI

- Executive Dashboard is polished;
- Lead / Sales Copilot is polished;
- Attention Center is polished;
- Opportunities view is polished;
- Sales Team view is polished;
- Analytics view is polished;
- Arabic customer content renders correctly;
- responsive behavior is acceptable;
- loading/empty/error states are present.

## Testing

- mandatory scenarios are executed;
- important tests pass;
- failures/limitations are honestly documented.

## Demo

- realistic seeded data exists;
- product can be demonstrated without exposing developer tooling;
- demo sequence is documented;
- visual quality is client-ready.

## Reusability

- deployment to the first pilot is reasonably repeatable;
- GHL configuration is snapshot-ready or otherwise documented for replication.

## Documentation

The following are complete:

- `project-knowledge/11-ghl-mvp-build-and-test-report.md`
- `project-knowledge/12-client-demo-script.md`
- updated `project-knowledge/00-project-context-and-current-status.md`
- updated `README.md`

## Git

- changes are committed;
- branch is `phase-2-mvp-build`;
- working tree is clean;
- commits are logically organized;
- no secrets are present.

---

# 50. Final operating principle

Do not optimize for:

> maximum features.

Optimize for:

> **a small set of differentiated capabilities that work reliably, clearly demonstrate recovered sales opportunity, and look impressive in front of a real business owner.**

The completed MVP should allow an automotive-protection business owner to understand very quickly:

1. which leads are being neglected;
2. which customer questions salespeople missed;
3. how long customers really waited for useful answers;
4. which quotes need follow-up;
5. which salespeople perform best;
6. which lead sources generate revenue;
7. how the system helps convert more enquiries into booked cars.

---

# 51. Final handoff

At completion provide a concise handoff containing:

- current branch;
- important commits;
- major files created;
- major files modified;
- product URL if deployed;
- test status;
- demo status;
- GHL status;
- integrations completed;
- mocked/demo-only portions;
- outstanding blockers;
- actions I need to take;
- expected monthly infrastructure cost;
- whether the MVP is ready for a customer demonstration;
- whether it is ready for a live pilot;
- recommended next step.

Do not merely say:

> Done.

Leave the repository in a state from which the next phase—real customer validation/pilot—can begin without rediscovering the project.

Proceed autonomously until completion or until a genuine external blocking action requires me.
