# LifeOS — MVP Scope

## Goal

Validate one central experience: **a person who feels uncertain about their direction can reflect on their current situation, choose a priority, and leave with one small, user-approved next action.**

This document describes proposed work, not implemented functionality.

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
7. **Foundational safeguards**
   - Clear AI limitations, basic prompt-injection precautions, input validation, and no secrets in source control.

## Out of scope for this MVP

- Clinical assessment, diagnosis, therapy, crisis counseling, or automated mental-health risk prediction.
- Payment processing, subscriptions, or enterprise features.
- Complex multi-agent orchestration or autonomous actions in third-party services.
- Comprehensive calendar, wearable, banking, or medical-record integrations.
- Public community features or social matching.
- A claim that the system improves mental health or life outcomes without evidence.

## Proposed user journey

1. User reads the purpose and privacy notice.
2. User answers a short set of reflective questions.
3. LifeOS displays a summary that the user can correct.
4. User selects a priority area.
5. AI helps turn it into one realistic, user-approved next action.
6. User can return to review the outcome and revise the plan.

## Candidate technical architecture

- **Frontend:** React / TypeScript
- **Backend:** Python / FastAPI
- **Storage:** PostgreSQL in a later iteration; local or minimal development storage may be sufficient for an initial prototype.
- **AI layer:** An interchangeable LLM adapter with explicit prompts, safety checks, and test fixtures.
- **Testing:** Unit tests for business logic, API tests, and scripted end-to-end user-journey tests.

All decisions remain provisional and should be recorded as they are made.

## Acceptance criteria

- A tester can complete the full journey without manual intervention.
- No real personal data is needed for a demonstration.
- The user can review and change the AI-generated priority summary and proposed action.
- Failure states (missing input, unavailable AI response) produce understandable feedback.
- The assistant avoids medical claims and clearly communicates its limitations.
- Key user interactions are covered by automated tests.
- A README explains setup, constraints, and current project status once software exists.

## Privacy implementation gate

Before inviting real users, document consent, data retention, deletion/export mechanisms, access controls, storage security, logging policy, and applicable regulatory obligations. Use synthetic profiles for demos and any externally shared development traces until these are reviewed.

## Proposed milestones

1. Product requirements and conversation examples.
2. Clickable flow / basic interface.
3. Backend and model integration.
4. Action planning and review loop.
5. Testing, privacy review, and documentation.

## Open questions

- What forms of session history or memory are essential, and what should remain ephemeral?
- What information, if any, may an external development or evaluation provider receive?
- How can users verify, correct, and delete stored context?
- How should the product be evaluated without making unsupported wellbeing claims?

*Estimate discussed for the broader project: ~200 hours; this is a planning estimate, not a commitment or funded allocation.*
