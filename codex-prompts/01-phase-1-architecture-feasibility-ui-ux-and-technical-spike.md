You are taking over an existing product-validation project for a Saudi automotive sales-conversion platform.

## 1. Project knowledge

The project workspace contains the following Markdown files:

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

Start by reading `00-project-context-and-current-status.md`.

Then read all other files needed to fully understand:

- how the business idea was formed,
- why premium automotive protection was selected,
- what competitor research has already been completed,
- the live WhatsApp mystery-shopping findings,
- the validated problems,
- the current MVP definition,
- the customer-validation plan,
- and the current client-facing UI / product-experience strategy.

Treat these Markdown files as the project source of truth.

Do not repeat market research that is already documented unless fresh research is required to make a current technical or architectural decision.

---

# 2. Your objective in this phase

Your job in Phase 1 is **not to build the complete production MVP yet**.

Your job is to:

1. verify what current GoHighLevel capabilities can actually support;
2. determine the correct technical architecture;
3. determine the correct client-facing UI architecture;
4. perform technical feasibility spikes on the most differentiated features;
5. design the complete MVP implementation;
6. produce a build-ready specification for Phase 2.

The main deliverable must be:

`10-ghl-mvp-architecture-ui-and-build-specification.md`

Do not finish this phase with a vague plan.

The specification must be detailed enough that another capable engineering agent can implement it without having to rediscover the architecture.

---

# 3. Product definition

The product is currently defined as:

> **AI-assisted WhatsApp Sales Conversion System for Saudi PPF / Tint / Ceramic / Premium Automotive Protection businesses**

The customer-facing business should **not** be positioned as:

- a GoHighLevel reseller,
- a generic CRM,
- a generic chatbot,
- a marketing agency,
- or a general workshop-management system.

The product's core promise is:

> **Never let a valuable WhatsApp lead receive an irrelevant answer, wait unnoticed, or disappear without structured follow-up.**

The management proposition is:

> **Make every salesperson perform more consistently like your best salesperson, while AI makes sure nothing gets missed.**

A useful marketing expression is:

> **Turn your Instagram, Snapchat and WhatsApp enquiries into booked cars.**

---

# 4. Architecture principle

The likely architecture is hybrid.

Use:

> **GoHighLevel as the CRM, messaging, workflow and automation engine**

and:

> **a polished custom branded frontend for the highest-value client-facing experience**

Do not assume this is definitely the right implementation until you verify current HighLevel capabilities.

Your task is to decide:

- what should remain native in GoHighLevel,
- what should be hidden from end users,
- what should be white-labeled,
- what should be implemented as a custom web UI,
- whether the custom UI should be embedded inside HighLevel or live independently,
- how authentication should work,
- how the custom UI should retrieve/update GHL data,
- and what architecture creates the best balance of speed, polish and maintainability.

Prefer native HighLevel functionality when it can meet the requirement reliably.

Do not force a critical requirement into native GHL if that materially weakens the product.

If a small external helper service is genuinely required, design the smallest maintainable component possible.

---

# 5. Research current GoHighLevel capabilities

Use current official HighLevel documentation and current product behavior before making architecture decisions.

Verify, in particular:

- WhatsApp integration
- WhatsApp Coexistence
- Conversation AI
- AI Extract Data
- workflow triggers
- workflow actions
- user / salesperson reply triggers
- opportunity / pipeline automation
- custom fields
- tags
- custom values
- webhooks
- APIs
- custom objects if applicable
- custom menu links
- embedded custom applications
- dashboards / reporting
- SaaS white-label options
- custom CSS / JavaScript
- roles / permissions
- snapshots
- calendars
- stop-on-reply behavior
- premium workflow actions
- any relevant usage costs
- API limitations
- conversation-history access
- webhook/event limitations
- authentication options for an external frontend

Use official documentation as the primary source.

Clearly distinguish:

- confirmed native capability,
- possible workaround,
- uncertain behavior requiring testing,
- and functionality that requires an external component.

---

# 6. Critical technical spike 1: Context extraction

Prove whether the system can receive a free-form Arabic enquiry such as:

> عندي نيسان باترول 2025 وأفكر أركب حماية PPF كاملة للسيارة. ممكن أعرف كم السعر عندكم حالياً، ونوع الفيلم المستخدم ومدة الضمان؟ وكم يحتاج التركيب تقريباً؟

and reliably extract structured fields such as:

- customer name if known
- vehicle make
- vehicle model
- model year
- requested service
- full vs partial PPF
- matte vs gloss if present
- branch / location if present
- requested appointment timing if present
- individual questions asked by the customer

Expected extracted questions in this example:

- price
- film type / brand
- warranty
- installation duration

Do not hard-code the solution specifically for Nissan Patrol.

It must be configurable for:

- different vehicles,
- different years,
- different services,
- different packages,
- different automotive-protection businesses.

Document accuracy considerations and fallback handling.

---

# 7. Critical technical spike 2: Question Completion Check

This is currently one of the most differentiated product features.

Prove whether the system can:

1. identify the customer's individual questions;
2. observe the salesperson's later response;
3. determine whether each question is:
   - answered,
   - partially answered,
   - unanswered;
4. alert or assist the salesperson when something important remains unanswered.

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

Expected system result:

- Film type: answered
- Warranty: answered
- Installation duration: answered
- Price: **unanswered**

The system should be able to generate an internal prompt such as:

> Customer is still waiting for the price.

Determine whether this can be implemented reliably with:

- native HighLevel AI / workflows,
- workflow triggers for salesperson responses,
- API / webhook support,
- or an external helper.

Do not weaken this requirement merely to stay native to HighLevel.

---

# 8. Critical technical spike 3: Meaningful Response SLA

We observed a real case where:

- an automated response arrived instantly,
- but the first useful human response arrived about 5.5 hours later.

The product must distinguish:

> **Automated acknowledgement time**

from:

> **Meaningful response time**

Prove how we can detect whether a response is actually meaningful.

A generic message such as:

> خدماتنا: عازل، نانو، PPF...

must not necessarily stop the meaningful-response timer if it does not address the customer's enquiry.

Design the logic for:

- start time
- generic acknowledgement detection
- meaningful response detection
- salesperson escalation
- supervisor escalation
- SLA thresholds
- reporting

Example dashboard outcome:

> Automated acknowledgement: 3 sec  
> Meaningful response: 5h 26m

Determine whether AI classification is needed and where it should run.

---

# 9. Salesperson copilot design

Design a Sales Copilot that helps the human salesperson rather than trying to replace them.

The system should assist with:

- understanding customer context,
- extracting vehicle/service data,
- identifying unanswered questions,
- suggesting the next best question,
- suggesting the relevant package,
- suggesting social proof,
- suggesting financing options,
- identifying likely objections,
- recommending next actions,
- prompting follow-up.

Humans should remain responsible for:

- trust,
- negotiation,
- judgment,
- product comparison,
- objection handling,
- closing.

The architecture should support both:

- human-first assisted sales,
- and potentially greater automation later.

---

# 10. Pipeline architecture

Design the initial opportunity pipeline.

Current proposed stages are:

- New Enquiry
- Qualified
- Quote Sent
- Follow-up
- Appointment Booked
- Deposit / Confirmed
- Vehicle Received
- Completed / Won
- Lost

Review these stages and refine only if necessary.

Define:

- stage transition rules,
- automation triggers,
- salesperson actions,
- required fields,
- exit conditions,
- lost-reason handling.

---

# 11. Custom fields and data model

Define the exact MVP data model.

At minimum consider:

## Contact

- customer name
- phone
- preferred language
- city
- consent / opt-out status

## Vehicle

- make
- model
- year
- trim if needed

## Enquiry

- service requested
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

## AI / QA metadata

- unanswered questions
- answer completeness score or state
- meaningful-response status
- SLA state
- objection category

Decide whether each field should be:

- contact field,
- opportunity field,
- custom object,
- tag,
- calculated/external field,
- or another structure.

---

# 12. Follow-up workflow architecture

Design configurable follow-up behavior.

The system should support:

- follow-up after quotation,
- follow-up after no customer response,
- automatic cancellation when the customer replies,
- salesperson/manual override,
- escalation where appropriate.

Do not lock the system to one exact interval.

Provide sensible demo defaults.

Follow-up should be personalized where possible.

Avoid spammy behavior.

---

# 13. Lost-reason and objection classification

Design categories such as:

- price
- competitor
- timing
- location
- no response
- product concern
- film / warranty preference
- financing
- no immediate need
- other

Determine:

- whether AI can classify this from conversations,
- when human confirmation is required,
- how it should appear in reports.

---

# 14. Manager dashboard requirements

The client-facing manager dashboard is one of the most important parts of the product.

It should focus on business outcomes.

Design cards / metrics for:

- new enquiries
- enquiries awaiting meaningful response
- average meaningful response time
- open quote value
- quotes requiring follow-up
- booked revenue
- lost opportunity value
- conversion rate
- salesperson conversion
- branch conversion
- lead source conversion
- lost reasons
- SLA breaches

Possible demo layout:

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

# 15. Client-facing UI / UX architecture

The MVP must be visually attractive enough to impress paying business owners.

Do not treat UI as an afterthought.

The client-facing interface should feel like:

> **our own automotive sales platform**

not:

> **a standard GoHighLevel account with a different logo**

Design the information architecture and visual hierarchy for the following screens.

---

## Screen 1: Executive Dashboard

Purpose:

> impress the owner immediately and summarize sales performance.

Must emphasize:

- revenue,
- open opportunities,
- response quality,
- attention items,
- team performance.

---

## Screen 2: Lead / Sales Copilot

This should likely be the **hero product screen**.

Example content:

### Ahmed
Nissan Patrol 2025

**Service:** Full PPF  
**Finish:** Matte  
**Potential value:** SAR 5,996  
**Stage:** Quote Sent  
**Salesperson:** Mohammed

### Customer asked

- ✓ Price
- ✓ Film type
- ✓ Warranty
- ⚠ Installation duration

### AI Suggestion

> Ahmed is still waiting for installation duration. Consider answering this before the opportunity goes idle.

Also include:

- conversation history,
- next action,
- follow-up timing,
- lead source,
- relevant package,
- internal notes.

---

## Screen 3: Attention Center

Example cards:

> 🔴 Nissan Patrol 2025  
> No meaningful response for 47 minutes

> 🟠 BMW X5  
> SAR 7,500 quotation  
> No customer response for 26 hours

> 🟡 Range Rover  
> Customer asked 4 questions  
> 1 unanswered

This screen should be immediately useful to both managers and salespeople.

---

## Screen 4: Opportunities

Design a polished Kanban:

- New
- Qualified
- Quote
- Considering
- Booked
- Won / Lost

Cards should include useful automotive context:

- vehicle
- service
- value
- age
- salesperson
- SLA state

---

## Screen 5: Sales Team

Show:

- salesperson
- assigned leads
- response time
- quotes
- bookings
- booked revenue
- conversion rate
- SLA breaches

---

## Screen 6: Analytics

Show:

- lead source
- lead count
- quotes
- bookings
- revenue
- conversion
- lost reasons
- trend over time

---

# 16. Native GHL vs. custom UI decision

For each function, decide whether it should be:

### A. Native HighLevel
### B. White-labeled / restyled HighLevel
### C. Embedded custom UI
### D. Separate custom application

Do not rebuild native administrative screens unless that adds clear value.

It is acceptable to keep these native if suitable:

- workflow editor
- automation configuration
- calendars
- advanced CRM admin
- template management
- system configuration

Spend custom UI effort on:

- everyday sales use,
- manager visibility,
- Sales Copilot,
- Attention Center,
- analytics,
- high-value customer experience.

---

# 17. UI technical requirements

The specification must define:

- frontend stack recommendation
- likely Next.js / React approach if appropriate
- component structure
- data-fetching strategy
- authentication
- GHL integration
- caching / state strategy
- error handling
- loading states
- empty states
- responsive design
- desktop-first but usable on tablet/mobile
- Arabic / English handling
- RTL support
- date/time formatting
- SAR formatting
- role-based visibility

Do not over-engineer.

The goal is:

> fast, polished, maintainable MVP.

---

# 18. Visual design direction

Define a coherent visual direction suitable for:

- premium automotive businesses,
- Saudi business owners,
- modern SaaS presentation.

The design should feel:

- premium,
- professional,
- clean,
- confident,
- modern,
- not flashy,
- not generic-admin-template-like.

Avoid:

- excessive gradients,
- gaming-style visuals,
- clutter,
- default Bootstrap/admin aesthetics.

Define:

- typography hierarchy
- spacing system
- dashboard card treatment
- icon approach
- charts
- tables
- Kanban styling
- attention states
- empty states
- AI/copilot visual treatment
- bilingual / RTL behavior

The visual design should remain feasible for Phase 2 to implement quickly.

---

# 19. Demo data

Design realistic seeded demo data so Phase 2 can create an impressive demonstration without using live customer information.

Use realistic examples such as:

- Nissan Patrol 2025
- Toyota Land Cruiser
- BMW X5
- Range Rover
- Mercedes G-Class

Services:

- full PPF
- front PPF
- matte PPF
- tint
- ceramic coating
- detailing

Use realistic SAR values.

Include examples representing:

- good lead handling,
- SLA breach,
- unanswered question,
- follow-up required,
- booked opportunity,
- lost opportunity.

---

# 20. Acceptance criteria

Define explicit acceptance criteria for every major MVP capability.

Examples:

### Context Extraction

Given a realistic Arabic enquiry, the system extracts vehicle, year, service and customer questions correctly.

### Question Completion

Given a salesperson response missing price, the system flags price as unanswered.

### Meaningful Response

A generic autoresponder does not incorrectly satisfy the meaningful-response SLA.

### Follow-Up

A quote with no reply enters follow-up automatically.

### Stop on Reply

Customer response cancels future automatic follow-up.

### Dashboard

Manager can identify:
- leads requiring attention,
- quote value,
- meaningful-response performance,
- conversion.

### UI

The client-facing demo must be polished enough to show to a paying Saudi automotive business owner without exposing an unfinished developer interface.

---

# 21. Cost / dependency analysis

Document all expected costs and dependencies.

Include:

- required HighLevel plan
- WhatsApp cost
- AI usage
- premium workflow actions
- external AI/API cost if any
- hosting for custom frontend
- hosting for helper service if any
- database if needed
- domain
- authentication
- likely pilot operating cost

Clearly distinguish:

- required
- optional
- later-stage

Avoid unnecessary paid components.

---

# 22. Security and privacy

Design the MVP with:

- secrets outside source control
- environment variables
- least privilege
- role-based access
- no production credentials in Markdown
- consent / opt-out fields
- Do Not WhatsApp handling
- Saudi PDPL considerations
- auditability where practical

Do not connect production customers during Phase 1.

---

# 23. Technical spike environment

Use:

- simulated test messages,
- test contacts,
- test opportunities,
- mock / test WhatsApp interactions where necessary.

Do not:

- send real campaigns,
- connect live customer numbers,
- modify production systems,
- purchase subscriptions,
- upgrade plans,
- accept paid services,
- accept contractual / Meta terms on my behalf.

Stop and ask me only if a genuine blocking dependency requires:

- login,
- authentication,
- subscription purchase,
- plan upgrade,
- contractual acceptance,
- production access,
- or another irreversible action.

For normal architecture decisions:

> make the best decision, document it, and continue.

---

# 24. Output requirements

Your primary output must be:

`10-ghl-mvp-architecture-ui-and-build-specification.md`

This document must include:

1. executive architecture summary
2. validated product requirements
3. native GHL capability matrix
4. GHL vs custom frontend architecture
5. external helper requirements if any
6. data model
7. pipelines
8. custom fields
9. tags
10. workflows
11. workflow triggers
12. AI extraction design
13. Question Completion Check design
14. Meaningful Response SLA design
15. follow-up logic
16. lost-reason logic
17. dashboard specification
18. Sales Copilot specification
19. Attention Center specification
20. Opportunities UI specification
21. Sales Team UI specification
22. Analytics UI specification
23. API / integration plan
24. authentication plan
25. Arabic / English / RTL strategy
26. visual design system
27. demo dataset
28. technical spike results
29. limitations
30. cost dependencies
31. security / privacy considerations
32. complete Phase 2 implementation sequence
33. acceptance criteria
34. blocking dependencies requiring my action

---

# 25. Update project context

At the end of Phase 1:

Update:

`00-project-context-and-current-status.md`

to record:

- architecture decisions,
- confirmed HighLevel capabilities,
- technical-spike results,
- whether external components are required,
- UI architecture,
- new risks,
- and the Phase 2 build plan.

Do not erase project history.

Update the current-status sections while preserving prior decisions and chronology.

---

# 26. Phase 1 completion condition

Phase 1 is complete only when:

- the critical technical feasibility has been tested,
- the Question Completion Check has a proven implementation path,
- Meaningful Response SLA has a proven implementation path,
- the GHL/native/custom boundary is decided,
- the client-facing UI architecture is decided,
- the data model and workflows are fully specified,
- demo screens are specified,
- costs and limitations are documented,
- acceptance criteria exist,
- and `10-ghl-mvp-architecture-ui-and-build-specification.md` is detailed enough for Phase 2 implementation without rediscovering the design.

Do not proceed into full production implementation during this phase unless a very small prototype is necessary to prove feasibility.

Prioritize correctness of architecture and critical technical proof over routine implementation.

For ordinary decisions, do not stop for approval.

Proceed autonomously until one of the explicitly defined blocking conditions occurs.