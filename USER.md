# USER.md - User Model

## Directives

<!-- observed: 2026-09-02 | status: active -->

- Always deliver client-facing websites to a premium, custom-agency standard: mobile-first, conversion-focused, visually specific to the business, and free of generic AI design patterns.

<!-- observed: 2026-09-02 | status: active -->

- Always include privacy, terms, cookie-consent requirements where applicable, and ADA/WCAG accessibility verification in website delivery; identify items requiring qualified legal review rather than presenting legal templates as legal advice.

<!-- observed: 2026-09-03 | status: active -->

- Never send "all quiet / nothing to report" heartbeat updates. Only speak on scheduled heartbeats when there is a concrete issue, opportunity, or actionable finding that warrants attention. Silence is the default.

<!-- observed: 2026-09-05 | status: active -->

- Always default future apps and scrapers to a GitHub + Supabase foundation, with Vercel as the default hosting and env layer for any project that has a web UI or app-facing automation endpoints.

<!-- observed: 2026-09-06..07 | status: superseded -->

- (History) Three prose model-routing policies (2026-09-06..07) superseded 2026-09-11 by the config-authoritative directive below; prose restatements kept drifting from the configured route.

<!-- observed: 2026-09-11 | status: active -->

- Treat the model route configured in `~/.openclaw/openclaw.json` as the single source of truth (see AGENTS.md → Model Continuity). Do not restate or override it in prose. Task-fit preferences within that route: Claude Sonnet 5 for coding, UI/UX, and premium client work; the configured OpenAI subscription models for general reasoning and copy; Gemini 3.1 Pro for very large-context research. No local Ollama models: removed 2026-09-11 (binary, model store, provider config, and all fallback entries); background jobs use the configured subscription models. Never default to OpenRouter or API-billed keys unless explicitly requested; the subscriptions and console token are the paid routes.

<!-- observed: 2026-09-07 | status: active -->

- Task Observer Policy: Whenever the user corrects a mistake, expresses frustration with a workflow, or provides a better methodology, immediately invoke the `task-observer` skill. The skill must capture the correction to prevent future repetition. Never modify Model Routing, Billing, or Authentication policies during observations; only append workflow or formatting corrections.

<!-- observed: 2026-09-07 | status: active -->

- Treat OpenClaw as a trusted local personal-assistant system operated by Donna through WebChat and the configured Discord allowlist. Prefer practical access controls, secret handling, backups, and channel restrictions over heavy multi-tenant hardening, sandboxing, or approval friction unless additional untrusted users, public exposure, or client/tenant separation is introduced.

<!-- observed: 2026-09-07 | status: active -->

- Prefer low-friction Discord/WebChat operation for the local OpenClaw system. Do not add, tighten, or overemphasize `allowlist`, `allowFrom`, mandatory mentions, or similar channel restrictions unless Donna explicitly asks for tighter access control or a real exposure risk appears.

<!-- observed: 2026-09-23 | status: active -->

- Installed means visible. Any skill, plugin, or MCP that gets installed is added to the per-agent `skills` list in the same pass — never left on disk pending a separate decision. The install is not finished until `openclaw skills list --agent <id> --json` reports `blockedByAgentFilter: false` for every agent that needs it. Default breadth is every agent unless Donna names a narrower set; narrowing is her call, not a reason to defer.
