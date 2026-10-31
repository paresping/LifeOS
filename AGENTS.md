# AGENTS.md — Instructions for AI Coding Agents

This repository currently contains **planning documentation only**. Do not assume an application exists.

## Mission

Develop LifeOS as a privacy-conscious, user-directed personal-growth tool that helps people reflect on their priorities and choose small, realistic actions. Do not design it as clinical treatment, autonomous life decision-making, or a replacement for human support.

## Sources of truth

Read these files before substantial changes:
1. `README.md` — current project overview.
2. `docs/PRODUCT_VISION.md` — purpose and principles.
3. `docs/MVP_SCOPE.md` — first milestone and non-goals.
4. `docs/ARCHITECTURE.md` — **proposed** structure, not fixed implementation.

If documents conflict, flag the discrepancy and suggest an explicit decision rather than silently adding features.

## Working practices

- Prefer the smallest change that completes an agreed MVP milestone.
- Keep domain rules, storage, HTTP transport, and LLM integrations clearly separated.
- Use typed interfaces, input validation, descriptive names, and readable modules.
- Write tests for new behavior; use mocked model responses for repeatable tests.
- Document trade-offs and update relevant docs when architectural choices change.
- Avoid unnecessary dependencies, microservices, agent frameworks, and speculative abstractions.
- Do not claim successful tests without running them; report exactly what was checked.
- Before sweeping refactors, explain impact, alternatives, and migration needs.

## User agency and safety

- Users choose their priorities and can correct or decline AI suggestions.
- Do not make diagnoses, assert clinical outcomes, or give the AI decision authority over users.
- Build understandable fallback behavior for unsafe, ambiguous, or unavailable AI outputs.
- Keep coaching language nonjudgmental; avoid manipulative engagement mechanics.
- Do not treat subjective ratings as validated psychological measurements.

## BYOK and cost safeguards

- Preserve a useful non-AI pathway for Life Compass, goals, actions and reviews.
- Use a provider-neutral AI adapter and simulated responses in automated tests.
- Do not assume a consumer AI subscription includes access to its provider's paid API.
- Do not implement live credential onboarding before secure per-user key handling is reviewed.
- Never put API keys in client code, browser storage, URLs, repositories, or logs.
- Explain provider billing and data processing before connecting real accounts.
- Require enforced rate limits, quotas and a hard stop for any centrally billed AI requests.
- Treat sponsored inference and local AI as future options, not guaranteed capabilities.

## Data security and privacy

- Default to **synthetic personas and fictional development data**.
- Never commit credentials, `.env` files, raw conversation exports, private financial or health records, or production data.
- Never expose an API key in frontend code.
- Minimize prompts and logging. Treat external AI providers and evaluation services as separate data recipients.
- Ask for a clear product decision before adding telemetry, persistent personal memory, or third-party data integrations.
- Do not deploy a real-user service until privacy, access control, retention, and deletion requirements are documented and tested.

## Alignerr / development-session boundary

This repository may be used in an external AI-assisted development program. **Do not assume approval, billable hours, or permission to upload private data.** Review program terms before sharing development transcripts or exposing proprietary material. Keep examples synthetic and development logs free of secrets.

The [24-task Development Roadmap](docs/DEVELOPMENT_ROADMAP.md) defines proposed, testable increments. Do not treat planned tasks as implemented or paid. Never load real-user reflections, private documents, or credentials into an externally shared evaluation session; use synthetic test data only.

## Initial implementation order (only when development is authorized)

1. Clarify the MVP flow and acceptance tests.
2. Establish a minimal project scaffold with tests and configuration examples.
3. Implement Life Compass, user-selected priority, and optional next-step guidance.
4. Add review/refinement and failure handling.
5. Reassess storage, authentication, and privacy requirements before real-user testing.

## Response expectations

When reporting work, summarize changed files, choices made, tests executed/results, unresolved risks, and suggested next step. Be explicit when work is documentation-only.
