# Harmony — Project Code Entry

**Status:** Draft concept / early product thesis  
**Project:** Project Code  
**Working name:** Harmony  
**Type:** Open-source, local-first, budget-aware AI development harness  
**Primary user:** Me first  
**Long-term audience:** solo developers, indie hackers, technical founders, agencies, advanced AI-assisted builders

---

## 1. One-line thesis

**Harmony is an open-source, budget-aware AI development runtime and project constitution system meant to replace fragmented Codex, Claude Code, Cursor, and OpenCode-style workflows.**

It exists to coordinate multiple AI models, coding agents, MCP tools, reusable Skills, permissions, project memory, design assets, review gates, and budget-aware routing inside one governed runtime.

The goal is not to create a shallow clone of Cursor, Codex, Claude Code, or OpenCode.

The goal is to replace the chaotic tool loop around them: repeated prompting, context rebuilding, permission guessing, manual model picking, disconnected reviews, and expensive agent runs that should have been routed or validated differently.

---

## 2. Why this exists

Current AI development harnesses and coding tools are powerful, but they should not be the center of the workflow. They often waste money and time because they lack a persistent, organized project operating system.

Common issues:

- Every AI tool repeatedly reconstructs project context.
- Design decisions drift between sessions.
- Agents forget architectural constraints.
- Models make product decisions they were never explicitly authorized to make.
- Implementation starts before the actual product scope is defined.
- Expensive models are used for tasks that cheaper models could handle.
- Cheap models are used without enough validation.
- Image generation, branding, assets, code, and review are disconnected.
- There is no consistent rule system across agents.
- There is no clear difference between planning, drafting, implementing, reviewing, and shipping.
- AI tools are too agreeable and often reinforce bad ideas instead of challenging them.

Harmony should solve this by making the project itself the center of gravity and making agents/providers interchangeable execution backends.

The project should contain its own memory, rules, artifacts, decisions, assets, task history, model-routing policy, and permissions.

---

## 3. Core product philosophy

### 3.1 Artifacts over chat history

Harmony should not rely on a long, fragile conversation as the main source of truth.

Each stage should produce persistent artifacts:

- project brief
- project constitution
- brand rules
- tech-stack decisions
- cost model
- page map
- component inventory
- asset manifest
- implementation tasks
- review reports
- audit logs

The AI does not “remember” the project.

The project contains its own memory.

---

### 3.2 Stages belong to capabilities, not providers

A stage should not be hardcoded to Claude, GPT, Codex, Kimi, Qwen, GLM, Gemini, or any other provider.

A stage should define the capabilities it needs.

Example:

```txt
Implementation stage requires:
- repo editing
- long context
- code generation
- test execution
- patch generation
- instruction following
- acceptable cost
```

Then Harmony routes that stage to the best available model or agent adapter based on budget, capability, trust level, and validation requirements.

---

### 3.3 Use premium models for judgment, cheaper models for labor

The system should aggressively support strong cost/performance models such as Kimi, Qwen, GLM, MIMO, and similar models.

These models should not be treated as second-class. They can be excellent for execution-heavy stages:

- boilerplate
- first-pass implementation
- refactors
- frontend layouts
- tests
- draft content
- structured transformations

But high-risk judgment should usually be handled by stronger or more trusted reviewers:

- architecture review
- final code review
- security-sensitive changes
- auth/payment/data handling
- legal/compliance-sensitive output
- final pre-release review

A useful default policy:

```txt
Cheap/efficient model does the work.
Different stronger model reviews the work.
Validators decide whether the result is accepted.
Escalate only if needed.
```

---

### 3.4 The model is not the trusted actor

Models can request actions.

Harmony decides whether those actions are allowed.

A model should not directly decide whether it can:

- edit files
- delete files
- run shell commands
- install packages
- read secrets
- call MCP tools
- access GitHub
- query a database
- spend money
- deploy
- commit
- push

The harness must own permissions.

---

### 3.5 Build for me first

The initial target user is not a vague market segment.

The first target user is me.

This matters because the MVP should optimize for actual pain, not investor-friendly feature bloat.

The project can become useful to others by solving the real workflow problem first:

```txt
I need a structured way to use multiple AI models and agents without losing project coherence, wasting money, or re-explaining the same context forever.
```

---

## 4. Name: Harmony

The preferred name is **Harmony**.

The name fits because the core product is about creating coordination between fragmented tools that normally compete or operate in isolation.

Harmony is not about pretending OpenAI, Anthropic, Google, Moonshot, Alibaba, Zhipu, MiniMax, and other labs naturally work together.

Harmony is about creating controlled collaboration despite fragmentation.

Possible positioning:

> **Harmony: a local-first AI development harness for coordinating models, agents, tools, rules, and reviews.**

Alternative tagline:

> **One project brain for every AI agent.**

Another:

> **Build with many models without losing the plot.**

---

## 5. What Harmony is not

Harmony is not:

- a browser-automation wrapper around consumer AI subscriptions
- a clone of Cursor
- a clone of Codex
- a clone of Claude Code
- a generic AI website builder
- a prompt library only
- a chat UI only
- a model marketplace only
- a “use every model” gimmick
- a tool that lets agents blindly modify code

Harmony should use official APIs, SDKs, CLIs, OpenRouter-style routers, local models, MCP servers, and code agents where appropriate.

But those are execution backends, not the user-facing center of gravity.

The real product is the replacement runtime:

- project constitution
- staged pipeline
- model routing
- skills
- MCP tool governance
- permissions
- validation gates
- cost tracking
- review discipline

---

## 6. Core system concept

Harmony can be understood as an **AI development pipeline router**.

For every task, it should answer:

```txt
What needs to happen?
What context is required?
What artifact should be produced?
Which model can do it cheaply enough?
What tools are allowed?
What permissions apply?
How do we validate the result?
When do we escalate?
Who reviews it?
What gets saved back to project memory?
```

---

## 7. Project constitution

The central primitive should be the **Project Constitution**.

This is the canonical source of truth for a project.

It should include:

- what is being built
- why it is being built
- who it is for
- project constraints
- non-goals
- brand identity
- tech-stack decisions
- model-routing policy
- permission policy
- review rules
- cost limits
- stage outputs
- accepted risks
- user overrides

Example shape:

```yaml
project:
  name: Harmony
  purpose: Local-first AI development harness
  primary_user: me
  license_target: Apache-2.0

principles:
  - Planning before coding
  - Artifacts over chat history
  - Provider neutrality
  - Budget-aware routing
  - Local-first by default
  - Review before trust
  - Permissions belong to the harness

routing:
  default_budget_mode: balanced
  separate_writer_and_reviewer: true
  escalate_on_validation_failure: true

permissions:
  default_action: ask
  secrets: deny
  git_push: deny

rules:
  no_unapproved_stack_changes: true
  no_placeholder_content_in_final: true
  require_cost_estimate_for_new_provider: true
```

---

## 8. Suggested project folder

Harmony should probably create a local folder inside each repo.

Working structure:

```txt
.harmony/
  project.yaml
  constitution.md
  memory.md

  rules/
    brand.rules.yaml
    code.rules.yaml
    design.rules.yaml
    stack.rules.yaml
    cost.rules.yaml
    permissions.rules.yaml

  stages/
    00-idea-intake.md
    01-council.md
    02-identity.md
    03-stack.md
    04-structure.md
    05-visual-concept.md
    06-assets.md
    07-implementation.md
    08-review.md
    09-deployment.md

  council/
    idea-brief.md
    verdict.yaml
    validation-plan.md
    transcripts/

  prompts/
    codex.md
    claude.md
    openrouter.md
    image.md

  skills/
    project-local-skills/

  assets/
    asset-manifest.json

  tasks/
    backlog.yaml
    active.yaml
    completed.yaml

  reviews/
    design-review.md
    code-review.md
    security-review.md
    performance-review.md

  audit/
    actions.jsonl
    costs.jsonl
```

The `.harmony/` directory is the project brain.

---

## 9. Pipeline overview

The pipeline should be staged, with each stage producing artifacts and optionally triggering review gates.

Suggested pipeline:

```txt
0. Idea Intake
1. AI Council / Viability Gate
2. Brand Identity
3. Scope, Stack, and Cost Model
4. Structure / Concepting A
5. Visual Concepting / Concepting B
6. Asset Augmentation
7. Synthesis / Implementation
8. Review
9. Deployment
10. Iteration
```

Feature additions should not bypass the pipeline.

A new feature should trigger a smaller version:

```txt
Feature Intake → Scope → UX → Assets if needed → Implementation → Review
```

---

## 10. Stage 0 — Idea Intake

Before branding or coding, Harmony should capture what is actually being built.

Output:

```txt
.harmony/stages/00-idea-intake.md
.harmony/project.yaml
```

Questions:

- What is the idea?
- Is it for personal use, open source, SaaS, client work, or business?
- Who is the user?
- What problem does it solve?
- How often does the problem occur?
- What is out of scope?
- What is the smallest useful version?
- What existing tools already solve part of this?
- What constraints exist?
- What budget limits exist?
- What models/API keys/tools are available?

This stage prevents the system from prematurely designing or coding the wrong thing.

---

## 11. Stage 1 — AI Council / Viability Gate

This is one of the most important additions.

Many AI systems become too agreeable. They validate bad ideas because the user sounds excited.

Harmony should include an adversarial council before major work begins.

The purpose is not gimmicky “AI investors.”

The purpose is to save the user from expensive delusion.

The council should answer:

```txt
Should this be built?
Should it be changed?
Should it be killed?
What is the cheapest next validation step?
```

### Council roles

Useful councilors:

- Skeptic
- Market Analyst
- Technical Architect
- Cost Analyst
- Legal/Risk Analyst
- Distribution Analyst
- UX/Product Analyst
- Competitor Analyst
- Founder Fit Analyst
- Moderator/Judge

### Anti-copium rules

The council should explicitly follow rules like:

```txt
Do not praise the idea unless evidence supports praise.
Identify the fastest reason this idea could fail.
Separate possible from worth building.
Separate technically possible from MVP feasible.
Penalize ideas requiring massive capital, regulation, hardware, or network effects.
Always propose the cheapest validation step before implementation.
If the idea is bad, say so directly.
```

### Example verdict schema

```yaml
verdict: pivot
confidence: 0.84

scores:
  desirability: 4
  feasibility: 2
  viability: 2
  founder_fit: 5
  distribution: 3
  legal_risk: 9
  capital_required: 9

recommended_action: Do not proceed to branding or implementation yet.

cheapest_validation_step: Interview 10 target users before building.

pivot_options:
  - Narrower software-only version
  - Marketplace version
  - Internal tool version

kill_reasons:
  - High liability
  - No realistic MVP path
  - Requires infrastructure outside founder capacity
```

### Gate behavior

The council should be allowed to block the pipeline.

```yaml
viability_gate:
  proceed_threshold: 70
  revise_threshold: 45
  kill_threshold: 25

on_proceed:
  unlock:
    - brand_identity
    - stack_planning

on_revise:
  unlock:
    - idea_refinement
    - validation_plan
  lock:
    - implementation
    - asset_generation

on_kill:
  unlock:
    - pivot_generation
    - postmortem
  lock:
    - brand_identity
    - implementation
```

The user can override the council, but Harmony should record it.

```yaml
override:
  user_overrode_council: true
  reason: I want to build this for myself regardless of market viability.
  acknowledged_risks:
    - unclear monetization
    - narrow audience
    - maintenance burden
```

---

## 12. Stage 2 — Brand Identity

Branding should happen after the idea survives or is explicitly overridden.

This stage is inspired by design-system workflows where the user chooses a brand direction, colors, fonts, tone, components, and visual language.

Output:

```txt
.harmony/rules/brand.rules.yaml
.harmony/stages/02-identity.md
```

The output should be machine-readable, not just descriptive.

Example:

```yaml
brand:
  name: Harmony
  personality:
    - organized
    - technical
    - calm
    - powerful
    - non-gimmicky
  avoid:
    - generic AI gradients
    - fake futuristic dashboards
    - childish branding
    - corporate sludge
  colors:
    primary: TBD
    accent: TBD
    background: TBD
  typography:
    heading: TBD
    body: TBD
  voice:
    direct: true
    low_hype: true
    practical: true
```

The system should offer several brand directions, then lock the selected one.

Once locked, future agents should not randomly change the brand.

---

## 13. Stage 3 — Scope, Stack, and Cost Model

This stage defines what actually needs to be created and how it should be built.

This is one of the most important anti-waste stages.

Output:

```txt
.harmony/stages/03-stack.md
.harmony/rules/stack.rules.yaml
.harmony/rules/cost.rules.yaml
```

It should decide:

- frontend framework
- backend framework
- database
- auth
- hosting
- storage
- email provider
- payments
- analytics
- AI providers
- image/video providers
- deployment target
- expected monthly operating cost
- scaling concerns
- maintenance cost
- legal/data concerns

For Harmony itself, a likely MVP stack:

```txt
Language: TypeScript
Runtime: Node.js
CLI: Commander, oclif, or similar
Validation: Zod
Config: YAML + JSON
Storage: files first, SQLite later if needed
Package manager: pnpm
UI later: Vue + Vite + Tailwind + DaisyUI
Architecture: local-first/hybrid
```

The first version should not start as a heavy hosted SaaS.

The first version should be a local-first CLI/project-folder system.

---

## 14. Stage 4 — Structure / Concepting A

This stage defines the structure before visual generation or coding.

For websites, this means pages, navigation, content, and functionality.

For apps, it means routes, screens, features, entities, workflows, and permissions.

Output:

```txt
.harmony/stages/04-structure.md
.harmony/page-map.md
.harmony/component-inventory.md
.harmony/user-flows.md
```

For a website, pages may include:

- Home
- About
- Services / Products
- Contact
- Privacy Policy
- Terms of Service
- Cookie Policy
- Blog / Resources
- FAQ
- Pricing
- 404

But Harmony should not blindly include pages.

It should decide which pages are actually needed.

The output should explain why each page exists or why it is excluded.

---

## 15. Stage 5 — Visual Concepting / Concepting B

This is where image-generation models can be used to generate visual drafts.

The important rule:

```txt
Image generation should visualize approved structure.
It should not define the product.
```

Output:

```txt
.harmony/stages/05-visual-concept.md
.harmony/visual-concepts/
.harmony/visual-review.md
```

For selected pages, Harmony can generate high-quality previews using available image models.

The previews must be manually and automatically reviewed for:

- brand fit
- layout realism
- buildability
- accessibility
- content relevance
- non-generic visuals
- typography consistency
- impossible UI artifacts
- mobile feasibility

This stage is useful, but dangerous if treated as truth. Image models often create impressive nonsense.

Harmony should act like an art director, not just a prompt sender.

---

## 16. Stage 6 — Asset Augmentation

This stage turns visual direction into real usable assets.

The observation behind this stage is important:

```txt
A high-quality website or product is not made of text, CSS, and divs alone.
Professional work needs strong media and asset direction.
```

Output:

```txt
.harmony/assets/asset-manifest.json
assets/source/
assets/optimized/
assets/webp/
assets/svg/
assets/icons/
assets/og/
```

Possible assets:

- hero images
- product mockups
- UI screenshots
- icons
- diagrams
- background textures
- avatars
- video loops
- case-study images
- Open Graph images
- favicons
- app icons

Example manifest:

```json
{
  "hero-dashboard": {
    "file": "assets/optimized/hero-dashboard.webp",
    "used_on": ["home"],
    "alt": "Dashboard showing Harmony's staged AI pipeline",
    "source_prompt": "Premium technical dashboard showing...",
    "license": "generated",
    "dimensions": [1600, 1000]
  }
}
```

This stage gives coding agents concrete assets to use instead of placeholders.

---

## 17. Stage 7 — Synthesis / Implementation

This is where code agents finally do the bulk of the implementation.

By this point, Harmony should already have:

- project constitution
- brand rules
- tech stack rules
- page map
- component inventory
- asset manifest
- content model
- implementation plan
- permissions
- validators
- model routing policy

Output:

```txt
.harmony/tasks/backlog.yaml
.harmony/stages/07-implementation.md
.harmony/reviews/code-review.md
```

Example task:

```yaml
task: implement-home-hero
stage: implementation
risk: medium
inputs:
  - brand.rules.yaml
  - page-map.md
  - asset-manifest.json
constraints:
  - use existing design tokens
  - no unapproved dependencies
  - no placeholder copy
  - mobile-first
  - run lint/typecheck/build
implementer_role: efficient_coding_model
reviewer_role: premium_review_model
```

A likely flow:

```txt
1. Kimi/Qwen/GLM implements first pass.
2. Local validators run.
3. GPT/Codex/Claude reviews the diff.
4. Implementer patches issues.
5. Escalate only if validation keeps failing.
6. Save decisions and review notes back to project memory.
```

---

## 18. Stage 8 — Review

Review is not optional.

Harmony should have dedicated review gates:

- design review
- code review
- accessibility review
- performance review
- security review
- cost review
- brand consistency review
- genericness/slop review

The reviewer should usually be a different model family from the implementer.

Example:

```txt
Implementation by Kimi → Review by GPT/Codex/Claude
Implementation by Claude → Review by GPT/Kimi/Qwen
Implementation by GPT → Review by Claude/Kimi
```

This reduces shared blind spots.

---

## 19. Stage 9 — Deployment

Deployment should be its own controlled stage.

Deployment-related permissions should be stricter than normal implementation.

Potential outputs:

```txt
.harmony/stages/09-deployment.md
.harmony/deployment-plan.md
.harmony/env-requirements.md
```

Deployment stage should handle:

- environment variables
- hosting provider
- build command
- deploy command
- domains
- analytics
- error monitoring
- rollback plan
- security checklist

No model should be allowed to deploy or push without explicit permission.

---

## 20. Model routing

Harmony should support model routing based on roles, budget, capability, and risk.

The user should be able to choose a budget mode instead of manually choosing a model every time.

Example:

```yaml
budget_modes:
  ultra_cheap:
    architect: qwen
    implementer: kimi
    reviewer: qwen
    final_review: gpt-mini

  balanced:
    architect: claude_or_gpt
    implementer: kimi
    reviewer: gpt_or_codex
    final_review: premium_review_model

  premium:
    architect: premium_reasoning_model
    implementer: codex_or_claude_code
    reviewer: premium_review_model
    final_review: premium_review_model
```

Better abstraction:

```yaml
roles:
  architect:
    requires:
      - deep_reasoning
      - architecture
      - long_context

  implementer:
    requires:
      - code_generation
      - patch_generation
      - repo_context

  reviewer:
    requires:
      - skeptical_reasoning
      - diff_analysis
      - security_awareness

  designer:
    requires:
      - brand_reasoning
      - visual_reasoning

  asset_director:
    requires:
      - image_prompting
      - asset_specification
```

The model registry should describe models by capability, not hype.

---

## 21. Cheapest model that passes

A major feature should be the **cheapest-passing strategy**.

Flow:

```txt
1. Try cheap model.
2. Validate output.
3. If it passes, accept.
4. If it fails, retry or patch.
5. If it keeps failing, escalate to stronger model.
```

Example:

```yaml
stage_policy:
  implementation:
    strategy: cheapest_passing
    attempts:
      - model_role: cheap_coding
        max_cost: 0.20
      - model_role: balanced_coding
        max_cost: 0.60
      - model_role: premium_coding
        max_cost: 2.00
```

This directly addresses the original frustration: AI harnesses are expensive because they use powerful models inefficiently and lack validation-driven escalation.

---

## 22. Provider and agent adapters

Harmony should support different provider types.

### Completion adapters

For normal text/code APIs.

```ts
interface CompletionAdapter {
  id: string
  provider: string
  listModels(): Promise<ModelProfile[]>
  run(request: CompletionRequest): Promise<CompletionResult>
}
```

### Agent adapters

For systems that can edit repos or run tasks.

```ts
interface AgentAdapter {
  id: string
  provider: string
  capabilities: AgentCapability[]
  runTask(task: AgentTask): Promise<AgentResult>
}
```

Potential adapters:

- OpenAI API
- Anthropic API
- Google API
- OpenRouter
- local models
- Ollama
- Codex-compatible adapter
- Claude Code-compatible adapter
- OpenCode-compatible adapter
- image model adapters

No adapter should be required for the core to function.

Adapters should be optional execution backends.

---

## 23. MCP support

Harmony needs first-class MCP support.

MCP servers should be treated as capability providers.

They may expose:

- tools
- resources
- prompts
- filesystem access
- GitHub access
- database access
- browser automation
- documentation search
- issue trackers
- design asset libraries

But MCP servers should not grant trust.

Rule:

```txt
MCP servers expose capabilities.
Harmony grants permissions.
```

Example config:

```yaml
mcp:
  servers:
    filesystem:
      command: npx
      args: ["server-filesystem", "."]
      permissions:
        default: ask

    github:
      command: npx
      args: ["server-github"]
      env:
        GITHUB_TOKEN: "${GITHUB_TOKEN}"
      permissions:
        default: ask

    postgres:
      command: npx
      args: ["postgres-mcp"]
      permissions:
        default: deny
```

The harness should expose only stage-relevant MCP tools to the model.

---

## 24. Skills support

Skills should be first-class.

A Skill is not just a prompt.

A Skill is a reusable workflow package.

It can include:

- instructions
- resources
- examples
- scripts
- schemas
- checklists
- required inputs
- allowed tools
- allowed MCPs
- permission requirements
- output artifacts
- validators

Example skill folder:

```txt
skills/
  landing-page-review/
    SKILL.md
    skill.yaml
    checklist.md
    schema.json
    examples/
    scripts/
      lighthouse-check.ts
```

Example skill config:

```yaml
id: landing-page-review
name: Landing Page Review

inputs:
  - brand.rules.yaml
  - page-map.md
  - implementation_url

allowed_tools:
  - browser.screenshot
  - file.read

allowed_mcp:
  - playwright
  - filesystem

permissions:
  file.read: allow
  file.write: deny
  bash: ask
  network: ask

outputs:
  - review.md
  - issues.json

validators:
  - schema: issues.schema.json
```

Skills define how work should be done.

MCPs define what tools/data are available.

Permissions define what is allowed.

Models perform the reasoning/labor.

Validators decide whether the result is acceptable.

---

## 25. Permissions

Harmony needs permission levels similar in spirit to OpenCode-style workflows.

Start simple:

```txt
allow = execute without asking
ask   = require user approval
deny  = block entirely
```

Permissions should apply to:

- file read
- file write
- file delete
- shell commands
- package installation
- network access
- MCP tool calls
- Git operations
- deployment
- secrets
- spending/cost

Example:

```yaml
permissions:
  file:
    read: allow
    write: ask
    delete: ask

  bash:
    default: ask
    allow_commands:
      - pnpm test
      - pnpm lint
      - pnpm build
    deny_commands:
      - rm -rf *

  git:
    diff: allow
    commit: ask
    push: deny

  secrets:
    read_env: deny
    read_dotenv: deny

  cost:
    max_task_usd: 0.50
    max_stage_usd: 1.50
    max_daily_usd: 5.00
```

Deny should override allow by default.

There should be permission profiles:

```yaml
permission_profiles:
  planning:
    file.read: allow
    file.write: ask
    bash: deny
    network: ask

  implementation:
    file.read: allow
    file.write: ask
    bash.test: allow
    bash.install: ask
    git.commit: ask
    git.push: deny

  review:
    file.read: allow
    file.write: deny
    bash.test: allow
    network: deny
```

Each stage declares a profile.

---

## 26. Audit log

Harmony should record every meaningful action.

Example:

```json
{
  "time": "2026-05-04T18:20:00Z",
  "stage": "implementation",
  "model": "kimi-k2-6",
  "adapter": "openrouter",
  "action": "file.write",
  "target": "src/pages/Pricing.vue",
  "permission": "ask",
  "decision": "approved",
  "cost_usd": 0.12,
  "result": "success"
}
```

This helps with:

- debugging
- cost tracking
- security
- reproducibility
- grant credibility
- open-source transparency

---

## 27. Validators

Validators make cheaper models viable.

Harmony should not trust outputs because they sound convincing.

It should validate them.

Code validators:

```txt
pnpm typecheck
pnpm lint
pnpm test
pnpm build
```

Design validators:

```txt
No unapproved colors
No fake content
No broken layout assumptions
No inaccessible contrast
No desktop-only implementation
```

Project validators:

```txt
No stack changes without approval
No new dependencies without reason
No secrets read
No forbidden files modified
No cost limit exceeded
No placeholder content in final output
```

Review validators:

```txt
Reviewer is not same model family as implementer
Review includes concrete issues
Review includes severity
Review includes pass/fail recommendation
```

---

## 28. Genericness / slop detector

Harmony should include a “genericness” detector, even if the public name is softer.

Possible names:

- Genericness Index
- Slop Score
- Originality Review
- AI Sludge Detector
- Quality Gate

Bad signals:

- “Revolutionize your workflow” copy with no specifics
- generic purple/blue gradient hero
- fake dashboard screenshots
- meaningless cards
- placeholder testimonials
- vague CTAs
- decorative AI visuals with no product meaning
- sections that look good but say nothing
- repeated SaaS-template structure

This matters because Harmony is trying to produce professional work, not generic AI output.

---

## 29. Open-source positioning

Harmony should be open-source.

The open-source angle is important because the project is about reducing AI waste, improving reproducibility, and letting developers control their own model routing and project memory.

The strongest positioning:

> **An open-source framework for reducing waste and improving reproducibility in agentic AI software development workflows.**

Potential license:

```txt
Apache-2.0
```

Apache-2.0 is a good default for infrastructure/dev tooling because it is permissive and includes stronger patent language than MIT.

---

## 30. Grant angle

The project may be a candidate for grants or credits from AI labs, especially if it demonstrates serious use of agentic coding tools, structured workflows, open-source reproducibility, and cost-aware model orchestration.

The pitch should not be:

```txt
I want free credits for my personal tool.
```

The pitch should be:

```txt
Harmony is an open-source, provider-neutral harness that improves the reliability, reproducibility, and cost-efficiency of AI-assisted software development through project constitutions, staged workflows, permissions, model routing, MCP support, Skills, validators, and cross-model review.
```

---

## 31. MVP direction

Do not start with the full SaaS.

Do not start with every provider.

Do not start with the web UI.

Start with the core local-first system.

### MVP v0.1

```txt
harmony init
harmony council
harmony stage identity
harmony stage stack
harmony stage structure
harmony export-prompt
harmony review
```

Creates:

```txt
.harmony/
  project.yaml
  constitution.md
  memory.md
  rules/
  stages/
  council/
  tasks/
  reviews/
```

### MVP v0.2

Add model registry and OpenRouter/direct API adapter.

```txt
harmony run council --budget cheap
harmony run stage stack --model kimi
harmony run review --model gpt
```

### MVP v0.3

Add permissions and audit log.

```txt
harmony permissions check
harmony audit list
```

### MVP v0.4

Add Skills.

```txt
harmony skill install landing-page-review
harmony skill run landing-page-review
```

### MVP v0.5

Add MCP support.

```txt
harmony mcp add filesystem
harmony mcp list-tools
harmony mcp permissions
```

### MVP v0.6

Add code-agent adapters.

```txt
harmony run implementation --agent codex
harmony run implementation --agent opencode --model kimi
```

### Later

- local web dashboard
- image pipeline
- asset manifest UI
- GitHub PR creation
- shared template marketplace
- cloud sync
- team workspaces
- deployment automation

---

## 32. Suggested initial commands

```txt
harmony init
harmony council
harmony plan
harmony brand
harmony stack
harmony structure
harmony tasks
harmony run
harmony review
harmony audit
```

Example flow:

```txt
harmony init "New SaaS landing page"
harmony council
harmony brand
harmony stack
harmony structure
harmony tasks generate
harmony run task home-hero --budget balanced
harmony review
```

---

## 33. Initial architecture

Suggested monorepo:

```txt
harmony/
  apps/
    cli/
    web/

  packages/
    core/
    pipeline/
    rules/
    artifacts/
    validators/
    permissions/
    routing/
    cost/
    skills/
    mcp/
    adapters/
      openai/
      anthropic/
      google/
      openrouter/
      local/
      codex/
      claude-code/
      opencode/

  templates/
    website/
    saas/
    dashboard/
    library/
    api/

  examples/
    landing-page/
    vue-app/
    node-api/

  docs/
    philosophy.md
    project-constitution.md
    pipeline.md
    routing.md
    permissions.md
    skills.md
    mcp.md
    grants.md
```

---

## 34. Main risks

### 34.1 Scope explosion

This idea can easily become too large.

The MVP must focus on the project constitution, staged artifacts, model routing, and permission foundations.

Avoid trying to support every provider, every image tool, full code execution, and a polished UI at the same time.

### 34.2 Adapter maintenance

Provider SDKs and agent tools may change often.

Harmony must keep adapters isolated from core logic.

If one adapter breaks, the project constitution and pipeline should still work.

### 34.3 Over-engineering before usefulness

The first win should be simple:

```txt
I can start a project and generate a clean .harmony/ folder that any AI agent can use without me re-explaining everything.
```

### 34.4 False confidence from councils

AI Council output can still be wrong.

It should be adversarial and structured, but not treated as divine truth.

Human override must exist.

### 34.5 Security surface from MCPs

MCPs can expose powerful tools and data.

They must be permission-wrapped, audited, and scoped per stage.

### 34.6 Cheap model misuse

Cheap models are valuable, but should not be blindly trusted.

Validation and cross-model review are what make them safe.

---

## 35. Open questions

- Should the project name be `Harmony`, `harmony-ai`, `harmony-dev`, or something more unique for package discovery?
- Should the CLI command be `harmony`, `hy`, or something else?
- Should `.harmony/` be the project folder name?
- Should the core be TypeScript from day one?
- Should Skills follow Codex-style `SKILL.md` conventions directly or use a Harmony-specific `skill.yaml` wrapper?
- How much should MCP support exist in v0.1 versus v0.5?
- Should the first model adapter be OpenRouter because it gives access to many models quickly?
- Should there be a manual prompt-export workflow before direct API execution?
- How strict should the AI Council gate be by default?
- What are the first three real projects to test Harmony on?

---

## 36. Current best first milestone

The best first milestone is not “build the entire harness.”

The best first milestone is:

```txt
Create a local-first CLI that initializes a .harmony/ project brain, runs an AI Council viability pass, generates a project constitution, and exports structured prompts/tasks for external agents.
```

This proves the core concept before deep automation.

Minimum useful output:

```txt
.harmony/project.yaml
.harmony/constitution.md
.harmony/council/verdict.yaml
.harmony/rules/stack.rules.yaml
.harmony/rules/permissions.rules.yaml
.harmony/tasks/backlog.yaml
.harmony/prompts/codex.md
.harmony/prompts/claude.md
.harmony/prompts/openrouter.md
```

Once this exists, the project already becomes useful.

---

## 37. Final summary

Harmony is a response to the current chaos of AI-assisted development.

The important insight is that the model is not the product.

The product is the system around the model:

- project memory
- rules
- pipeline stages
- model routing
- budget policy
- MCP access
- Skills
- permissions
- validators
- review gates
- audit logs

Harmony should let a developer use many AI systems together without losing project coherence.

It should help decide whether an idea is worth building before money is spent.

It should route work to cheaper models when safe.

It should reserve expensive models for judgment and review.

It should make every important decision explicit and persistent.

The first version should be built for personal use, local-first, CLI-first, and open-source.

The long-term vision is a serious AI development runtime that makes agentic coding cheaper, safer, more organized, and more reproducible.
