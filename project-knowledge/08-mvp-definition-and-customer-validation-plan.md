# MVP Definition and Customer Validation Plan

**File:** `08-mvp-definition-and-customer-validation-plan.md`  
**Purpose:** Convert the research and mystery-shopping findings into a concrete MVP definition, pilot structure, customer interview process, pricing test, and decision criteria for whether to proceed.

---

## 1. Current Product Definition

The product should be built and tested as:

> **AI-assisted WhatsApp Sales Conversion System for PPF / Tint / Ceramic businesses**

The system should help automotive protection businesses:

- understand inbound WhatsApp enquiries
- avoid asking redundant questions
- ensure all customer questions are answered
- structure opportunities in a sales pipeline
- monitor meaningful response time
- prompt the salesperson when something is missing
- follow quotations consistently
- stop automation when the customer replies
- classify objections / lost reasons
- give management visibility into salesperson and branch performance
- track leads through to booked revenue

The customer should not need to know that GoHighLevel is the underlying infrastructure.

---

## 2. Core Customer Promise

Primary promise:

> **Never let a valuable WhatsApp lead receive an irrelevant answer, wait unnoticed, or disappear without structured follow-up.**

Management-oriented promise:

> **Make every salesperson perform more consistently like your best salesperson, while AI makes sure nothing gets missed.**

Alternative sales-oriented positioning:

> **Turn your Instagram, Snapchat and WhatsApp enquiries into booked cars.**

Arabic-facing positioning:

> **حوّل استفسارات الواتساب إلى حجوزات**

---

## 3. Target Customer

Initial target:

- PPF centers
- ceramic coating centers
- tint shops
- wrapping businesses
- premium detailing businesses

Preferred customer profile:

- established business
- active social media
- meaningful WhatsApp lead volume
- high-ticket services
- at least one salesperson or branch team
- ideally multiple salespeople or branches
- enough lead volume for measurable conversion improvement
- weak or inconsistent sales-process visibility

Avoid as first pilot customers:

- very small operators with almost no lead volume
- large enterprise chains with complex integrations
- general mechanical workshops requiring ERP-style functions

---

## 4. Main Problems Considered Validated

The mystery-shopping experiment has already shown evidence of:

### Context Failure

Automation asks for information already present in the customer's message.

Example pattern:

> Customer already states vehicle and service, but bot asks for both again.

---

### Relevance Failure

Automated responses may be instant but generic.

Example pattern:

> Customer asks about PPF and receives a general service promotion.

---

### Question Completion Failure

Customers frequently ask multiple explicit questions and receive incomplete answers.

Typical missed items:

- price
- installation duration
- film brand
- warranty detail

---

### Meaningful-Response Delay

A business may appear to respond instantly because of automation, while the first useful answer comes hours later.

Therefore the system must distinguish:

- automated acknowledgement time
- meaningful response time

---

### Sales Quality Inconsistency

Different salespeople or businesses show very different levels of:

- qualification
- personalization
- product explanation
- social proof
- follow-up
- closing behavior

---

### Follow-Up Inconsistency

Some salespeople follow up well.

Others may not.

The product should not assume:

> “nobody follows up.”

The stronger thesis is:

> **follow-up discipline is inconsistent and difficult to standardize.**

---

## 5. Positive Benchmark

KMQ is the current strongest sales-process benchmark observed.

Good behaviors included:

- salesperson introduction
- friendly tone
- qualification
- tailored package
- pricing
- financing
- social proof
- follow-up
- invitation to discuss objections

This demonstrates:

> good sales behavior already exists and should be replicated systematically.

---

## 6. MVP Scope

The MVP should be deliberately narrow.

It must demonstrate the complete sales-conversion workflow without becoming a full automotive management platform.

### MVP Capability 1 - Incoming WhatsApp Lead

A realistic enquiry enters the system.

Example:

> عندي نيسان باترول 2025 وأبغى PPF كامل...

---

### MVP Capability 2 - Context Extraction

The system extracts:

- customer name
- vehicle make
- vehicle model
- year
- service requested
- gloss / matte preference if stated
- location / branch if stated
- requested appointment timing if stated
- questions asked

---

### MVP Capability 3 - Opportunity Creation

Create a CRM opportunity automatically.

Suggested pipeline:

- New Enquiry
- Qualified
- Quote Sent
- Follow-up
- Appointment Booked
- Deposit / Confirmed
- Vehicle Received
- Completed / Won
- Lost

---

### MVP Capability 4 - Question Detection

The system identifies what the customer asked.

Example:

- price
- film
- warranty
- installation time

---

### MVP Capability 5 - Question Completion Check

Monitor replies and mark:

- answered
- partially answered
- unanswered

Example internal status:

- Price: answered
- Film: answered
- Warranty: answered
- Installation time: **unanswered**

---

### MVP Capability 6 - Salesperson Prompt

If something important is missing, prompt the salesperson.

Example:

> **Customer asked about installation duration. Not answered.**

---

### MVP Capability 7 - Meaningful Response Timer

Track:

- auto acknowledgement time
- meaningful response time

Do not treat generic bot messages as a successful response.

---

### MVP Capability 8 - Response SLA

If no meaningful response arrives within a defined time:

- notify salesperson
- optionally notify supervisor
- flag the lead

Example:

> 🔴 High-value PPF lead waiting 35 minutes for meaningful response.

---

### MVP Capability 9 - Follow-Up Workflow

If a quote is sent and the customer goes silent:

- schedule follow-up
- send or propose another follow-up
- optionally send a final follow-up
- stop immediately when customer replies

Timing should be configurable and validated in pilots.

---

### MVP Capability 10 - Salesperson Assistance

The system should suggest:

- next qualification question
- missing answer
- relevant package
- social proof
- financing option
- next best action

The AI should assist, not replace, the human by default.

---

### MVP Capability 11 - Lost Reason

If the lead is lost, classify:

- price
- timing
- competitor
- no response
- location
- warranty
- product
- financing
- no current need

---

### MVP Capability 12 - Manager Dashboard

The owner / manager should see:

- new enquiries
- leads waiting for meaningful response
- average meaningful response time
- open quotes
- open quote value
- leads requiring follow-up
- booked revenue
- lost opportunities
- salesperson conversion
- branch conversion
- lead-source conversion
- lost reasons

---

## 7. Dashboard Example

Example owner view:

### Today

- New enquiries: 18
- Waiting for response: 4
- Quotes sent: SAR 62,400
- Leads needing follow-up: 7
- Potential opportunities going cold: SAR 31,500

### Sales Team

| Salesperson | Leads | Avg. Response | Quotes | Bookings |
|---|---:|---:|---:|---:|
| Mohammed | 18 | 9 min | 11 | 5 |
| Khalid | 14 | 48 min | 6 | 2 |
| Ahmed | 16 | 17 min | 9 | 4 |

The dashboard is strategically important because:

> **owners pay for management visibility and revenue outcomes, not chatbot novelty.**

---

## 8. Lead-Source Revenue Attribution

The system should eventually support:

**campaign / channel -> lead -> quote -> booking -> revenue**

Example:

> Snapchat campaign -> 47 leads -> 11 bookings -> SAR 68,400 revenue

This is likely to be a strong management feature.

It may not need full implementation in the first demo if technically expensive, but the demo should show the concept.

---

## 9. Explicit MVP Exclusions

Do not build these into the first MVP:

- accounting
- ZATCA invoicing
- workshop inventory
- spare parts
- technician job cards
- payroll
- PPF roll inventory
- full workshop operations
- POS replacement
- full warranty-management platform
- native mobile app
- complex customer portal
- generic website builder
- loyalty system as a primary feature

Reason:

> these dilute focus and are not required to validate the sales-conversion problem.

---

## 10. Human vs. AI Responsibilities

### Human Salesperson

Should continue to handle:

- trust
- negotiation
- judgment
- objections
- comparisons
- relationship
- closing

### AI / System

Should handle:

- extraction
- context
- completeness
- reminders
- follow-up
- classification
- measurement
- pipeline updates
- SLA monitoring
- reporting

---

## 11. Demo Scenarios

The demo should be built around real failure patterns discovered in research.

### Scenario A - Redundant Automation

Customer already says:

> Nissan Patrol 2025 + full PPF

Bad system:

> What is your vehicle and what service do you need?

MVP:

> extracts both automatically

---

### Scenario B - Missing Answer

Customer asks:

- price
- film
- warranty
- installation time

Salesperson answers three.

MVP:

> **Warning: installation duration still unanswered**

---

### Scenario C - Fake Instant Response

Bot responds immediately with generic text.

Human takes more than five hours to help.

MVP dashboard:

> Auto acknowledgement: 3 sec  
> Meaningful response: 5h 26m

---

### Scenario D - Best Salesperson

KMQ-style process:

- qualify
- recommend
- value stack
- financing
- proof
- follow-up

MVP goal:

> help every salesperson execute this discipline more consistently.

---

## 12. Customer Validation Objective

The mystery-shopping phase already indicates real sales-process gaps.

The next question is:

> **Will real Saudi automotive-protection businesses pay for this solution?**

This is now more important than collecting many more competitor examples.

---

## 13. Number of Customer Interviews

Start with:

> **5 serious business conversations**

Prefer:

- owner
- branch manager
- sales manager

Avoid using only junior reception staff for validation.

Prefer businesses not already mystery-shopped for the first interview round.

---

## 14. Interview Questions

Ask these before showing the demo.

### Lead Volume

> How many WhatsApp enquiries do you receive approximately per day?

---

### Sales Team

> How many people answer those enquiries?

---

### Follow-Up

> How do you know whether a salesperson followed up after sending a quotation?

---

### Lost Leads

> If someone asks about PPF today and does not book, what normally happens?

---

### Attribution

> Can you tell how many enquiries from Instagram / Snapchat actually became paying customers?

---

### Management Visibility

> Can management see salesperson response times and conversion rates?

---

### Current Software

> Do you use a CRM today? Which one?

---

### Biggest Pain

> What is the biggest problem in handling WhatsApp enquiries?

---

## 15. Interview Principle

Do not explain the solution too early.

The purpose is to hear the customer's own language.

If the customer says:

> “salespeople forget to follow up”

show:

> structured follow-up

If they say:

> “I do not know what staff are doing”

show:

> manager dashboard

If they say:

> “we get too many repetitive enquiries”

show:

> context extraction + salesperson assistance

---

## 16. Willingness-to-Pay Validation

Do not end with:

> “What do you think?”

That produces weak validation.

Ask directly:

> If we connected this to your WhatsApp, configured the workflows and gave management these reports, would around SAR 1,000-1,500 per month make sense for a center like yours?

Then ask:

> If we prepare a pilot version for you, would you be willing to test it for one month?

---

## 17. Current Pricing Test

Initial validation range:

> **SAR 1,000-1,500/month**

This is not final pricing.

The purpose is to test:

- whether the value is material
- whether monthly subscription is acceptable
- whether setup should be separate
- whether AI / WhatsApp usage should be rebilled

Earlier concepts included higher package tiers.

Do not optimize pricing until customers react to a working demo.

---

## 18. Pilot Structure

Suggested first pilot:

- one branch
- one WhatsApp number
- limited number of salespeople
- PPF / tint / ceramic leads only
- 30-day test
- simple baseline vs. pilot comparison

Track:

- lead volume
- meaningful response time
- unanswered-question rate
- quote-to-booking conversion
- follow-up completion
- lost reasons
- booked revenue

---

## 19. Pilot Offer

The pilot should not become an unlimited free consulting project.

Possible structure:

### Option A - Discounted Paid Pilot

- setup fee reduced
- one-month subscription
- narrow scope

### Option B - Free Pilot with Strong Conditions

Only if needed to secure the first proof point.

Require:

- access to real lead flow
- permission to measure results
- management feedback
- permission to use anonymized case-study metrics if successful

The preferred outcome is:

> **at least one willing-to-pay pilot**

---

## 20. Validation Decision Gate

### Strong Validation

Out of 5 serious business conversations:

- at least 3 clearly identify the problem
- at least 2 want a pilot
- at least 1 is willing to pay

Action:

> **Proceed aggressively.**

---

### Mixed Validation

Businesses like the concept but:

- resist pricing
- only want one feature
- say current processes are “good enough”

Action:

> refine scope, pricing, or value proposition.

---

### Weak Validation

Most say:

- problem is not important
- existing system solves it
- unwilling to pilot
- unwilling to pay

Action:

> do not overbuild; revisit sector or product thesis.

---

## 21. GoHighLevel Build Strategy

Do not build a full SaaS.

Use GoHighLevel to create:

> **a demonstration / pilot MVP**

Focus only on the validated workflow.

Likely components:

- WhatsApp integration
- CRM pipeline
- custom fields
- workflows
- AI extraction / classification
- internal notifications
- follow-up automation
- dashboards / reporting

---

## 22. GHL as Infrastructure

The customer-facing product should not be sold as:

> GoHighLevel

The product identity should remain vertical and outcome-focused.

Possible future path:

### Phase 1

GHL-based pilot / managed deployment

### Phase 2

repeatable automotive snapshot / productized service

### Phase 3

white-label SaaS / custom front-end

### Phase 4

replace GHL components or build proprietary software if scale justifies it

---

## 23. Data / Privacy Requirements

The product should eventually support:

- marketing consent
- source of consent
- opt-out
- Do Not WhatsApp
- data minimization
- role access
- retention logic

Do not treat this as optional.

---

## 24. Current Build Priority

Build only enough to demonstrate:

1. lead arrives
2. context is extracted
3. questions are detected
4. pipeline is created
5. salesperson is notified
6. missing answers are detected
7. meaningful response timer runs
8. quote follow-up is scheduled
9. automation stops when customer replies
10. manager can see status and performance

That is sufficient for the first pilot discussion.

---

## 25. Immediate Next Actions

### Workstream A - Knowledge Base

- finish Markdown conversion
- maintain:
  - `00-project-context-and-current-status.md`

### Workstream B - Demo Build

- create the minimum GoHighLevel implementation

### Workstream C - Customer Validation

- identify 5 target businesses
- interview owner / manager
- demonstrate only relevant pain points
- test willingness to pay
- ask for pilot

### Workstream D - Existing Mystery Shopping

- continue logging replies
- do not wait for the experiment to finish before customer validation

---

## 26. Success Definition

The goal of the next stage is not:

> “build a beautiful SaaS”

The goal is:

> **obtain evidence that real Saudi automotive-protection businesses will pay for the solution.**

The strongest proof would be:

> **a paid pilot.**

---

## 27. Main Decision Question

At the end of this validation stage, answer:

> **Do real Saudi PPF / tint / ceramic businesses see enough value in this sales-conversion system to pay approximately SAR 1,000-1,500/month?**

If yes:

> proceed.

If not:

> refine or stop before investing heavily.

---

## 28. Relationship to Other Files

For the research history, read:

- `01-initial-research.md`
- `02-competition-sector-and-go-to-market-research.md`
- `03-automotive-market-and-competitor-research.md`

For the experiment design and evidence, read:

- `04-whatsapp-mystery-shopping-plan.md`
- `05-whatsapp-mystery-shopping-results.md`
- `06-post-enquiry-analysis-and-product-validation.md`
- `07-vip-car-care-response-analysis-and-product-implications.md`

For the current project summary, always start with:

`00-project-context-and-current-status.md`
