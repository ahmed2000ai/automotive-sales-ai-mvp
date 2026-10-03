You are continuing an existing Saudi automotive sales-conversion product project.

This is **Phase 2: implementation, integration, testing, visual polish, and client-demo preparation**.

Phase 1 has already completed the architecture, current GoHighLevel feasibility research, technical spikes, and UI/UX design.

Your job now is to **build the working MVP**, not to reopen the product strategy unless implementation evidence proves that a Phase 1 architectural decision is infeasible.

---

# 1. Read the project state first

The workspace contains the project knowledge base:

- `00-project-context-and-current-status.md`
- `01-initial-research.md`
- `02-competition-sector-and-go-to-market-research.md`
- `03-automotive-market-and-competitor-research.md`
- `04-whatsapp-mystery-shopping-plan.md`
- `05-whatsapp-mystery-shopping-results.md`
- `06-post-enquiry-analysis-and-product-validation.md`
- `07-vip-car-care-response-analysis-and-product-implications.md`
- `08-mvp-definition-and-customer-validation-plan.md`
- `09-client-facing-ui-and-product-experience-strategy.md`

Phase 1 should also have produced:

`10-ghl-mvp-architecture-ui-and-build-specification.md`

Start by reading:

1. `00-project-context-and-current-status.md`
2. `10-ghl-mvp-architecture-ui-and-build-specification.md`

Then read any numbered source files necessary to understand or verify a requirement.

Treat the Markdown files as the project source of truth.

Do not repeat completed market research.

Do not redesign the product merely because you personally prefer another architecture.

If there is a conflict between older project files and the Phase 1 specification, use the most recent explicitly documented decision unless implementation testing proves it cannot work.

---

# 2. Main objective

Build the MVP described in:

`10-ghl-mvp-architecture-ui-and-build-specification.md`

The result must be a **working, visually polished, client-demonstrable product**, not just configuration notes or isolated prototypes.

The final product should demonstrate the core promise:

> **Never let a valuable WhatsApp lead receive an irrelevant answer, wait unnoticed, or disappear without structured follow-up.**

And the management proposition:

> **Make every salesperson perform more consistently like your best salesperson, while AI makes sure nothing gets missed.**

---

# 3. Product identity

Do not present the product to clients as:

- GoHighLevel
- a generic CRM
- a generic chatbot
- a marketing agency service
- a workshop ERP

GoHighLevel is infrastructure.

The client-facing product must feel like:

> **a dedicated automotive sales-conversion platform**

for:

- PPF
- tint
- ceramic coating
- wrapping
- premium detailing

The visual and functional experience should support eventual branding without requiring fundamental redesign.

Use temporary neutral branding if no final commercial brand has been chosen.

Do not block implementation waiting for a product name.

---

# 4. Autonomy

Proceed through the entire implementation without asking me for routine approvals.

You are authorized to make normal technical decisions required to complete the MVP.

Do not stop merely because:

- several implementation approaches are possible
- a UI detail is subjective
- test data needs to be created
- a workflow needs refinement
- a package/library needs to be selected
- a component must be refactored

Choose the best reasonable solution, document important decisions, and continue.

Only stop and ask me if a genuine external blocking action is required, such as:

- authentication/login I must personally complete
- Meta or WhatsApp authorization
- paid plan upgrade
- subscription purchase
- contractual acceptance
- production account access
- irreversible production action
- external credential that you cannot create safely
- a charge that requires my approval

Do not purchase or upgrade anything without approval.

---

# 5. Implementation priority

Build in this order unless `10` establishes a technically superior dependency order.

## A. Core GHL/data foundation

Implement:

- pipeline
- opportunity stages
- custom fields
- tags
- roles where appropriate
- test users / salesperson identities if possible
- test branches if useful
- workflow foundations

---

## B. Context extraction

Implement extraction of structured information from free-form customer enquiries.

At minimum support:

- vehicle make
- vehicle model
- model year
- service
- full / partial
- matte / gloss where present
- location / branch where present
- requested timing where present
- customer questions

Do not hard-code Nissan Patrol logic.

The system must work with different vehicles and services through configuration.

---

## C. Question Completion Check

Implement the Phase 1 proven architecture.

Required behavior:

1. customer sends multiple questions;
2. system records those questions;
3. salesperson responds;
4. system determines:
   - answered
   - partially answered
   - unanswered;
5. salesperson is notified or assisted if important information is missing.

Required demo case:

Customer asks:

- price
- film
- warranty
- installation duration

Salesperson replies with:

- American self-healing film
- 7-year warranty
- 2-day installation

Expected result:

> **Price remains unanswered.**

The client-facing UI must make this obvious.

---

# 6. Meaningful Response SLA

Implement separate tracking for:

### Automated acknowledgement

and

### Meaningful response

A generic auto-response must not automatically satisfy the meaningful-response SLA.

Required demo case:

Customer asks about full PPF.

System sends a generic immediate acknowledgement.

No relevant human response occurs.

The dashboard must still show the lead as:

> **Awaiting meaningful response**

and the SLA timer must continue.

Implement:

- warning threshold
- breach threshold
- salesperson alert
- manager escalation where specified in `10`

Use configurable thresholds rather than deeply hard-coded values.

---

# 7. Opportunity/pipeline automation

Implement the agreed pipeline.

Likely stages include:

- New Enquiry
- Qualified
- Quote Sent
- Follow-up
- Appointment Booked
- Deposit / Confirmed
- Vehicle Received
- Completed / Won
- Lost

Implement the transition logic from `10`.

Make sure important actions update:

- stage
- next action
- salesperson
- quote value
- meaningful response status
- follow-up status
- lost reason

---

# 8. Salesperson Copilot

Implement the client-facing Sales Copilot experience.

This should be one of the product's strongest screens.

For a lead, show information such as:

### Customer

Ahmed

### Vehicle

Nissan Patrol 2025

### Service

Full PPF

### Finish

Matte

### Potential / quote value

SAR 5,996

### Pipeline status

Quote Sent

### Salesperson

Mohammed

### Customer Questions

- ✓ Price
- ✓ Film type
- ✓ Warranty
- ⚠ Installation duration

### AI Suggestion

Example:

> Ahmed is still waiting for installation duration. Answer this before the opportunity goes idle.

Also expose, as appropriate:

- conversation context
- next action
- follow-up timing
- lead source
- package
- internal notes
- SLA state
- objection/lost reason when relevant

The screen should immediately communicate why this product is different from a normal WhatsApp inbox.

---

# 9. Follow-up automation

Implement follow-up logic according to `10`.

The MVP should demonstrate:

- quotation sent
- customer becomes silent
- follow-up becomes due
- salesperson/system follows the configured workflow
- customer reply stops future follow-up automation

Do not create spammy or excessive sequences.

Use demo defaults but keep timing configurable.

Include manual override.

---

# 10. Lost-reason classification

Implement the agreed categories.

Likely categories:

- price
- timing
- competitor
- location
- no response
- product concern
- warranty preference
- financing
- no current need
- other

Use AI classification where appropriate.

Allow human correction if required by the architecture.

Make the data reportable.

---

# 11. Lead-source attribution

Implement the maximum practical MVP attribution supported by the architecture.

Track sources such as:

- Instagram
- Snapchat
- Google
- Direct WhatsApp
- Website
- Referral

Where practical show:

> source -> leads -> quotations -> bookings -> revenue

If full production-grade attribution requires integrations not suitable for the MVP, create a credible demo implementation with correctly designed data structures and document what will be needed for a live pilot.

Do not fake architectural capability.

---

# 12. Custom client-facing UI

Implement the polished frontend defined in `09` and `10`.

The client-facing interface must **not look like an unfinished developer dashboard or default admin template**.

Use the frontend architecture selected in Phase 1.

If that is a custom Next.js / React application, implement it fully enough for the client demo.

If Phase 1 chose an embedded approach inside HighLevel, implement that architecture.

Do not casually abandon the Phase 1 UI decision.

---

# 13. Required client-facing screens

At minimum implement these screens.

## 13.1 Executive Dashboard

This is the owner's first impression.

Show polished KPI cards such as:

- New Leads
- Avg. Meaningful Response
- Open Quotations
- Booked Revenue

Also show:

### Needs Attention

Examples:

- leads awaiting meaningful response
- quotations requiring follow-up
- unanswered customer questions
- SLA breaches

### Sales Performance

Show meaningful team comparison.

### Lead Sources

Show source performance and revenue where supported.

The dashboard must prioritize:

> business outcomes

not technical CRM activity.

---

## 13.2 Lead / Sales Copilot

This is a hero screen.

Implement the detailed lead context and Question Completion interface.

The difference between this product and a generic CRM should be immediately obvious here.

---

## 13.3 Attention Center

Implement prioritized action cards.

Example:

> 🔴 Nissan Patrol 2025  
> No meaningful response for 47 minutes

Example:

> 🟠 BMW X5  
> SAR 7,500 quotation  
> No customer response for 26 hours

Example:

> 🟡 Range Rover  
> Customer asked 4 questions  
> 1 unanswered

Support:

- priority
- reason
- salesperson
- opportunity value
- elapsed time
- next recommended action

---

## 13.4 Opportunities

Implement a polished Kanban or equivalent opportunity view.

Suggested stages:

- New
- Qualified
- Quote
- Considering / Follow-up
- Booked
- Won
- Lost

Cards should show useful context such as:

- vehicle
- service
- value
- salesperson
- lead age
- SLA / attention state

Do not overload cards.

---

## 13.5 Sales Team

Show:

- salesperson
- lead count
- average meaningful response
- quotes
- bookings
- booked revenue
- conversion
- SLA breaches

Design this for a manager.

---

## 13.6 Analytics

Show:

- lead sources
- leads
- quotations
- bookings
- revenue
- conversion
- lost reasons
- useful trends

Keep charts readable and restrained.

---

# 14. UI quality requirement

This is a hard acceptance criterion.

The MVP is **not complete merely because the workflows function**.

It is complete only when the client-facing experience is polished enough to show to a paying Saudi automotive business owner.

The visual design should feel:

- premium
- professional
- modern
- clean
- confident
- automotive-relevant
- restrained rather than flashy

Avoid:

- generic admin-template appearance
- excessive gradients
- gaming aesthetics
- cluttered dashboards
- inconsistent spacing
- placeholder icons
- developer/debug UI
- obviously unfinished states

---

# 15. Design system

Implement the Phase 1 design system.

Use consistent:

- typography
- spacing
- card treatment
- tables
- navigation
- icons
- charts
- badges
- states
- buttons
- AI/copilot treatment

If the Phase 1 specification leaves minor design decisions open, make sensible choices and maintain consistency.

Do not stop for branding approval.

Use a polished neutral temporary product identity.

---

# 16. Arabic and English

Implement the bilingual / RTL strategy defined in `10`.

At minimum ensure:

- Arabic customer content renders correctly
- RTL content is visually correct
- English management UI remains clean if that is the initial demo language
- Arabic labels can be supported where designed
- dates, numbers and SAR values display correctly

Do not build a fake bilingual toggle that is incomplete.

If full localization is outside MVP scope, implement the architecture cleanly and make the supported demo behavior explicit.

---

# 17. Responsive behavior

The demo should be strong on desktop.

Also ensure reasonable usability on:

- laptop
- tablet
- mobile

Do not sacrifice desktop dashboard quality merely to optimize the smallest screen.

Salesperson screens should be particularly usable on mobile-sized layouts where practical.

---

# 18. Loading, empty and error states

Implement polished states for:

- loading
- no leads
- no attention items
- no analytics
- API failure
- missing integration
- unavailable conversation

No screen should appear broken if data is absent.

---

# 19. Demo dataset

Seed a realistic dataset.

Include vehicles such as:

- Nissan Patrol 2025
- Toyota Land Cruiser
- BMW X5
- Range Rover
- Mercedes G-Class

Include services such as:

- Full PPF
- Front PPF
- Matte PPF
- Tint
- Ceramic Coating
- Premium Detailing

Use realistic SAR values.

Include examples of:

### Strong sales handling

A KMQ-style journey.

### Context failure prevented

Customer already provided vehicle/service.

### Missing question

Customer asks four questions; salesperson answers three.

### Meaningful response SLA breach

Generic auto-reply but no useful response.

### Follow-up due

Open quotation with silent customer.

### Booked lead

Converted opportunity.

### Lost lead

Classified lost reason.

The demo must make the system feel alive.

---

# 20. Real mystery-shopping scenarios

Use the real observed patterns from:

`05-whatsapp-mystery-shopping-results.md`

as inspiration for test fixtures.

Do not expose competitor names in the customer-facing demo unless explicitly needed internally.

Create anonymized scenarios based on:

- DRIVEN context-blind automation
- Liquidglass generic acknowledgement / delayed meaningful response
- VIP incomplete question answering
- Pro Master template-heavy response
- KMQ strong salesperson behavior

---

# 21. Testing

Implement automated tests where practical.

At minimum test:

- extraction logic
- question-completion classification
- meaningful-response classification
- SLA timing logic
- follow-up stop-on-reply
- lost-reason classification
- data mapping
- API integration
- important frontend states

Also perform manual end-to-end test scenarios.

---

# 22. Required acceptance tests

At minimum demonstrate these scenarios successfully.

## Test A — Context Extraction

Input:

> عندي نيسان باترول 2025 وأفكر أركب حماية PPF كاملة للسيارة...

Expected:

- Nissan
- Patrol
- 2025
- Full PPF

correctly extracted.

---

## Test B — Redundant Question Prevention

Because vehicle/service are already known, the system should not ask for them again unnecessarily.

---

## Test C — Question Completion

Customer asks:

- price
- film
- warranty
- installation duration

Salesperson supplies:

- film
- warranty
- installation duration

Expected:

> Price remains unanswered.

---

## Test D — Meaningful Response

Generic automatic acknowledgment occurs.

Expected:

> meaningful-response SLA continues.

---

## Test E — Relevant Human Response

A response directly addressing the customer should stop meaningful-response timing.

---

## Test F — Follow-Up

Quote sent, customer silent.

Expected:

> follow-up becomes due according