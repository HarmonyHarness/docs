# Harmony - Product Thesis

Status: early product thesis

Harmony is an open-source, native, UI-first development runtime for AI-assisted software work.

It is meant to replace the scattered workflow people currently build around Codex, Claude Code, Cursor, OpenCode, chat windows, model pickers, manual prompts, disconnected reviews, and fragile project memory.

Harmony is not an automation-first tool. It is not a web app prototype. It is not a JavaScript product. The product is planned as a native Rust application with real native builds.

The interface is the main product surface. Automation workflows may exist later, but only as supporting surfaces.

## The Core Idea

Modern AI coding tools are powerful, but the workflow around them is messy.

Every agent needs context. Every model makes different assumptions. Every session drifts. Expensive models get used for cheap labor. Cheap models get trusted too quickly. Review happens inconsistently. Project decisions live in chats instead of in the project itself.

Harmony makes the project the center of gravity.

The project should carry its own memory, rules, decisions, tasks, design direction, review history, permissions, and budget policy. Agents and models become workers inside that system, not the system itself.

## What Harmony Replaces

Harmony replaces the chaotic layer around AI-assisted development:

- repeated project explanations
- scattered prompt files
- manual model picking
- disconnected agent sessions
- inconsistent review habits
- forgotten architecture decisions
- unclear permission boundaries
- expensive model calls for low-risk work
- weak validation before trusting output
- chat history pretending to be project memory

The goal is not to make a shallow clone of existing coding agents.

The goal is to own the workflow they currently fail to own.

## Product Positioning

Harmony is a governed workspace for building software with AI.

It gives the developer a visual control center for the whole process:

- define the project
- challenge the idea before building
- lock decisions
- plan the product
- route work to suitable models or agents
- control what tools can be used
- track cost and risk
- review outputs before accepting them
- preserve decisions inside the project

The user should not need to remember what was decided last week. The project should remember.

## Native First

Harmony should be built as a native Rust application.

That matters because Harmony needs to feel like a serious local tool, not a browser tab pretending to be a development environment. It should have direct local project awareness, fast startup, reliable filesystem access, and a stable foundation for long-term desktop workflows.

No Node, Bun, or JavaScript runtime should be required for the core product.

## UI First

Harmony should be visual from the beginning.

The first useful version should let the user open a project, create the Harmony project brain, walk through the early planning stages, review decisions, and export or run structured work.

The UI is not decoration. It is where the developer sees the project state, understands what stage they are in, approves risky actions, compares outputs, and decides what becomes part of the project.

An automation surface can come later for scripting and release workflows. It should not define the product.

## Brand Direction

Harmony should feel like a native developer product, not a generic AI startup.

The brand should be compact, deliberate, and controlled. The current direction uses a strong monogram, restrained contrast, and a wordmark that gives the product more identity than another abstract assistant interface.

The visual language should avoid generic AI gradients, fake futuristic dashboards, soft SaaS decoration, and meaningless product imagery.

## Local First

Harmony should start as a local-first tool.

The first version should not be a hosted SaaS. It should work on the developer's machine, with project state stored alongside the project.

This makes the tool useful before cloud sync, teams, billing, hosted execution, or marketplace features exist.

Cloud features can come later, but they should not be required for the core experience.

## Project Memory

Harmony should turn important project context into durable artifacts.

Instead of relying on a long chat thread, Harmony should preserve:

- what is being built
- why it is being built
- who it is for
- what is out of scope
- what decisions are locked
- what risks are accepted
- what models and tools are allowed
- what work has been done
- what still needs review

The project should become legible to any future agent, reviewer, or human collaborator.

## The Project Constitution

The central idea is the Project Constitution.

This is the project's source of truth. It should describe the product, goals, constraints, non-goals, style, permissions, routing rules, review expectations, and accepted risks.

The constitution should be easy for a human to read and strict enough for agents to follow.

When an agent tries to change direction, introduce a new dependency, ignore a constraint, or invent product scope, Harmony should be able to catch that drift.

## Staged Workflow

Harmony should guide work through clear stages instead of letting implementation start too early.

The early flow should include:

- idea intake
- adversarial product review
- project constitution
- brand and identity direction
- scope and stack decisions
- structure and user flows
- task generation
- implementation runs
- review and acceptance
- audit history

Feature work should follow a smaller version of the same path.

This is how Harmony keeps AI-assisted development from turning into a pile of impressive but incoherent output.

## Adversarial Review

Harmony should not flatter bad ideas.

Before serious work begins, it should challenge the project like a skeptical product council. It should look for weak assumptions, unclear users, risky scope, high maintenance cost, legal exposure, distribution problems, and fake confidence.

The point is not to kill ambition. The point is to avoid spending time and money building the wrong thing.

The user can override the review, but Harmony should record that override and the risks attached to it.

## Model Routing

Harmony should not treat one model as the universal answer.

Different work has different risk. Some tasks need strong judgment. Some tasks need cheap execution. Some tasks need visual reasoning. Some tasks need strict review.

Harmony should route work based on capability, trust, cost, and validation needs.

Cheap models should be used where they are good enough. Stronger models should be reserved for judgment, architecture, security-sensitive work, and final review.

The important rule is simple: output is not trusted because it sounds good. It is trusted only after it survives the right checks.

## Permissions

The model should not be the trusted actor.

Harmony should decide what an agent can read, write, run, spend, access, or publish.

Models can request actions. Harmony grants or blocks them based on project rules, stage, risk, and user approval.

This matters because agentic tools become dangerous when they can act without a clear policy.

## Review Discipline

Review should be built into the workflow, not treated as optional cleanup.

Harmony should support design review, code review, accessibility review, security review, performance review, cost review, and product review.

The reviewer should often be different from the worker. That reduces shared blind spots and makes cheaper execution models more useful.

## Quality Bar

Harmony should fight generic AI output.

It should notice vague marketing copy, fake product claims, meaningless dashboards, placeholder sections, weak visual direction, repeated template structures, and features that look impressive but do not serve the product.

The standard is not "the model produced something."

The standard is "this belongs in the project."

## Open Source

Harmony should be open-source.

The open-source angle matters because the product is about transparency, reproducibility, cost control, and developer ownership.

Developers should be able to inspect how decisions are made, how permissions are enforced, how reviews are recorded, and how model routing works.

## First Useful Version

The first useful version should be small but real.

It should let a developer open a local project, create the Harmony project brain, define the product, run the first review gates, generate a project constitution, create tasks, and preserve the results.

That is enough to prove the core value: the project can carry its own operating memory instead of depending on a fragile conversation.

## What Comes Later

Later versions can add deeper model execution, agent adapters, richer review screens, design asset workflows, cloud sync, GitHub workflows, team workspaces, and deployment support.

Those should come after the local native product proves its value.

## Main Risks

The biggest risk is scope explosion.

Harmony can easily become too many things at once: agent runner, design tool, project manager, model router, reviewer, documentation engine, deployment tool, and marketplace.

The early product should stay focused on the core promise:

- make the project coherent
- make decisions explicit
- make agents governable
- make model use cheaper and safer
- make review unavoidable

Another risk is false confidence.

Even a structured workflow can be wrong. Harmony should help developers think better, not pretend the system is infallible.

## Final Summary

Harmony is a response to the current chaos of AI-assisted development.

The important insight is that the coding agent is not the product.

The product is the runtime around the agent: the project memory, decision system, permission layer, routing logic, review discipline, and visual workflow that make AI-assisted development coherent.

Harmony should let a developer use many AI systems without losing the plot, wasting money, or trusting output too early.

The first version should be personal, local-first, native, UI-first, Rust-based, and open-source.
