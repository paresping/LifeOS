# LifeOS — Proposed Development Roadmap

> **Status:** Planning only. Tasks are not implemented, approved, assigned, or guaranteed to be billable by Alignerr.

## Working assumptions

Build a mobile-first responsive web MVP that demonstrates the Life Compass -> user-selected priority -> optional next action -> review journey. Preserve a usable non-AI flow and a provider-neutral model adapter. Test with **synthetic personas only**. No real user accounts, private information or real API credentials are permitted in development/evaluation traces.

Each task below is intentionally small enough to be tackled and reviewed in an AI-assisted development session. Task IDs are planning references, not GitHub issues.

## Suggested backlog

| ID | Task | Deliverable | Acceptance criterion |
|---|---|---|---|
| 01 | Define core user journey | Document screens, states and the Compass-to-review flow | A single flow describes all steps and failure states. |
| 02 | Create fictional test personas | Prepare diverse non-identifying synthetic scenarios | Every example is visibly fictional and contains no personal data. |
| 03 | Establish monorepo scaffold | Set up minimal frontend/backend/test directories | Local setup commands run without live provider credentials. |
| 04 | Set up quality tooling | Add formatters, linters and test commands | Documented checks run locally and in CI where practical. |
| 05 | Build mobile-first shell | Create navigation and responsive layout | Main views work at narrow mobile and desktop widths. |
| 06 | Create onboarding and boundaries | Explain purpose, limits, and data use | A test user sees the notice before starting. |
| 07 | Create Life Compass form | Capture domain reflections and optional subjective ratings | Inputs validate and support keyboard/touch. |
| 08 | Create reflection summary | Summarize responses using deterministic logic first | User can edit/correct the summary. |
| 09 | Build priority selection | Allow a user to choose an area of focus | Nothing is selected automatically as an instruction. |
| 10 | Define domain schemas | Create typed models for reflections, goals, actions and reviews | Validation tests cover valid and invalid cases. |
| 11 | Implement Compass API | Validate and return synthetic reflection data | API contract and tests are documented. |
| 12 | Implement priorities API | Record and retrieve a selected priority in test storage | Isolation and error tests pass in prototype context. |
| 13 | Build provider-neutral AI interface | Provide model adapter plus mock implementation | Tests run without network/model calls. |
| 14 | Design safe coaching prompts | Draft prompts and bounded structured outputs | Prompts avoid diagnoses and unsupported claims. |
| 15 | Create action suggestion flow | Offer a small next step with explanation | User can edit or reject the suggestion. |
| 16 | Implement no-AI fallback | Provide usable prompts/templates without paid model calls | Full journey works with AI disabled. |
| 17 | Implement basic action review | Allow tried/skipped/revised statuses and reflections | Changes are visible in the user flow. |
| 18 | Handle error and loading states | Cover unavailable AI, empty input and service errors | Clear recovery path is shown for each state. |
| 19 | Audit accessibility and responsiveness | Check contrast, labels, focus and viewport layouts | Manual checklist and relevant automated tests pass. |
| 20 | Review privacy and data flows | Document storage, retention and external processors | No real users are invited until privacy gate clears. |
| 21 | Specify BYOK security design | Review safe provider credentials, account isolation and costs | Threat model is documented; no real keys onboarded. |
| 22 | Run end-to-end synthetic scenarios | Test complete Compass-to-review journey | Representative scenarios pass and results are recorded. |
| 23 | Prepare reproducible demo | Create setup guide and synthetic walkthrough | Another developer can run demo without secrets. |
| 24 | Review scope and next milestones | Compare delivered MVP with requirements | Open limitations and future PWA work documented. |

## Suggested sequence

- **Discovery and tooling:** 01–04
- **Core UI and domain:** 05–12
- **AI guidance and no-AI alternative:** 13–18
- **Quality, privacy and demonstration:** 19–24

## Review standard for each task

Record what changed, why it changed, tests actually executed, any model limitations, and unresolved risks. Keep human review of AI-generated code. Do not represent a proposed requirement as completed functionality.

## Alignerr suitability gate

Before work under an external evaluation program, confirm in writing whether this project and its **future intended use involving users' personal reflections** are eligible, even if all development/evaluation data is synthetic. Confirm code ownership, rights to share development transcripts, required use of Claude Code, payment rules and approval of hours. Do not infer approval from receiving an invitation or submitting a survey.

## Scope boundaries

Do not add real-user onboarding, cloud synchronization, third-party personal-data integrations, payment processing, live BYOK key storage or native apps within the initial prototype. The relevant privacy/security reviews must precede any expansion to real users.

## Estimate

The previously discussed ~200 hours is a rough project planning number, not a sum of per-task commitments or a forecast of compensated hours.
