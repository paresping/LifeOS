# LifeOS — MVP Scope

## Goal

Validate one central experience: **a person who feels uncertain about their direction can reflect on their current situation, choose a priority, and leave with one small, user-approved next action.**

This document describes proposed work, not implemented functionality.

**Delivery decision:** The first release is a **mobile-first responsive website** usable on phone and desktop. A home-screen-installable Progressive Web App (PWA) is a subsequent enhancement; separate iOS and Android native apps are outside the MVP.

## In scope — first release

1. **Simple onboarding and boundaries**
   - Explain what LifeOS does and does not do.
   - Make the prototype's data handling transparent.
2. **Life Compass reflection**
   - Let users reflect on a few life domains and describe what matters to them.
   - Avoid presenting subjective ratings as a clinical assessment.
3. **Priority selection**
   - Let users choose an area they want to explore; do not select one automatically.
4. **AI-guided conversation**
   - Ask thoughtful questions, summarize the user's stated aims, and propose optional steps.
   - Allow the user to edit or reject the AI's interpretations.
5. **Action plan**
   - Produce one concrete next step with a description and an optional target date.
6. **Basic review**
   - Let the user mark an action as tried, skipped, or revised and record a short reflection.
7. **Mobile-first responsive interface**
   - Complete the core journey comfortably on a narrow phone screen and on desktop.
   - Support touch, keyboard navigation, readable text, and basic accessibility.
8. **AI funding boundary and graceful fallback**
   - Support the complete basic reflection, priorities, action and review journey without paid AI calls, using deterministic guidance or templates where necessary.
   - Define a provider-neutral model interface, with mocked responses for development.
   - Demonstrate an optional BYOK configuration flow with fictional credentials only; live credential onboarding is deferred until security review.
   - Explain that consumer subscriptions may not provide API credit, and that users may incur provider charges.
9. **Foundational safeguards**
   - Clear AI limitations, basic prompt-injection precautions, input validation, and no secrets in source control.

## Out of scope for this MVP

- Clinical assessment, diagnosis, therapy, crisis counseling, or automated mental-health risk prediction.
- Payment processing, subscriptions, or enterprise features.
- Live third-party API key storage, sponsored credits and production billing infrastructure in the initial local MVP.
- Complex multi-agent orchestration or autonomous actions in third-party services.
- Comprehensive calendar, wearable, banking, or medical-record integrations.
- Public community features or social matching.
- Native iOS or Android apps, app-store publication, and guaranteed push notifications.
- Cross-device account synchronization until authentication and privacy controls are implemented.
- A claim that the system improves mental health or life outcomes without evidence.

## Proposed user journey

1. User reads the purpose and privacy notice.
2. User answers a short set of reflective questions.
3. LifeOS displays a summary that the user can correct.
4. User selects a priority area.
5. AI helps turn it into one realistic, user-approved next action.
6. User can return to review the outcome and revise the plan.

## Candidate technical architecture

- **Frontend:** Mobile-first responsive React / TypeScript (one codebase for browser use on phone and desktop); optional PWA capabilities in a later phase.
- **Backend:** Python / FastAPI
- **Storage:** PostgreSQL in a later iteration; local or minimal development storage may be sufficient for an initial prototype.
- **AI layer:** An interchangeable LLM adapter with explicit prompts, safety checks, and test fixtures.
- **Testing:** Unit tests for business logic, API tests, and scripted end-to-end user-journey tests.

All decisions remain provisional and should be recorded as they are made.

## Acceptance criteria

- A tester can complete the full journey without manual intervention.
- The journey is usable on narrow mobile and standard desktop screens, including keyboard and touch interaction.
- No real personal data is needed for a demonstration.
- The user can review and change the AI-generated priority summary and proposed action.
- Failure states (missing input, unavailable AI response) produce understandable feedback.
- The core journey works without any paid model invocation, and AI suggestions are identified as optional.
- No real API keys appear in source code, browser bundles, test fixtures, or shared logs.
- The assistant avoids medical claims and clearly communicates its limitations.
- Key user interactions are covered by automated tests.
- A README explains setup, constraints, and current project status once software exists.

## Privacy implementation gate

Before inviting real users, document consent, data retention, deletion/export mechanisms, access controls, storage security, logging policy, and applicable regulatory obligations. Use synthetic profiles for demos and any externally shared development traces until these are reviewed.

## Proposed milestones

1. Product requirements and conversation examples.
2. Mobile-first clickable flow and responsive web interface.
3. Backend and model integration.
4. Action planning and review loop.
5. Testing, privacy review, and documentation.
6. Secure BYOK integration and per-user cost notices only after a key-handling security review; sponsored capacity and local models can follow if justified.
7. Optional PWA installability and opt-in reminders after the basic experience is validated; assess cross-device synchronization separately.

## Open questions

- What forms of session history or memory are essential, and what should remain ephemeral?
- What information, if any, may an external development or evaluation provider receive?
- How can users verify, correct, and delete stored context?
- How should the product be evaluated without making unsupported wellbeing claims?
- Which secure BYOK authorization/key storage model is feasible for a hosted web app, and which AI providers permit it?
- How will paid requests be capped, and what functionality remains available without AI?

*Estimate discussed for the broader project: ~200 hours; this is a planning estimate, not a commitment or funded allocation.*
