# Real Estate Sourcing — AI-Assisted Workflow

## Context

Real estate sourcing and opportunity qualification involve collecting, structuring, and assessing a large volume of potential opportunities from heterogeneous sources. Much of this work is manual, repetitive, and time-consuming, which limits how many opportunities a professional can realistically review and compare.

This project is a practical AI-assisted automation **prototype** built to support that work. It is not a finished SaaS product. It is presented here to demonstrate business understanding, workflow design, AI-assisted structuring, and lead qualification logic.

## Business Problem

Sourcing teams and real estate professionals typically face:

- Opportunities arriving in inconsistent formats from multiple channels
- Significant manual effort to clean, structure, and compare them
- Limited time to qualify and prioritize what actually matters
- Difficulty keeping a consistent, repeatable evaluation process

The result is that good opportunities can be missed, and time is spent on low-value manual processing rather than decision-making.

See [`business-case.md`](./business-case.md) for the full reasoning.

## Solution Overview

The workflow automates the repetitive parts of sourcing while keeping humans in control of the decisions:

1. **Ingest** opportunities from defined input sources.
2. **Normalize** them into a consistent, structured format.
3. **Use an AI/LLM layer** to help interpret, summarize, and structure unstructured details.
4. **Apply a qualification step** to flag and prioritize opportunities against defined criteria.
5. **Output** a structured, reviewable shortlist.
6. **Route everything through human review** before any decision is made.

See [`architecture.md`](./architecture.md) for the high-level system design.

## What This Project Demonstrates

- Ability to translate a concrete business problem into an automation workflow
- Designing a clear, staged pipeline (input → processing → AI → qualification → output → review)
- Pragmatic use of AI to handle unstructured information
- Lead qualification and prioritization logic
- Awareness of confidentiality and the limits of automation
- Ability to work on ambiguous, non-technical business problems and turn them into structured automation logic that a client can understand and review.

## Stack Used

- **n8n** — workflow orchestration and automation logic
- **APIs and webhooks** — data ingestion and integration
- **LLMs (ChatGPT / Claude / Gemini)** — interpreting and structuring unstructured information
- **GitHub Codespaces** — cloud development environment used to structure and iterate on the project
- **Claude Code / Codex** — AI coding assistants used for repository work, documentation, debugging support and workflow logic iteration
- **GitHub** — versioning, documentation and project organization

See the repository-level [`tools-and-stack.md`](../../tools-and-stack.md) for the broader toolset.

## What Is Intentionally Not Public

To protect business logic and any third-party data, this repository does **not** include full workflows, exact sourcing methods, proprietary scoring rules, prompts, credentials, or any lead/client data.

See [`what-is-not-public.md`](./what-is-not-public.md) for the full list and the reasoning.

## Current Status

This is a working **prototype / project**, not a productized tool. The core pipeline structure is defined and the approach has been exercised on real workflow design, but it is intended for supervised use and continued iteration rather than as a finished, autonomous system.

See [`roadmap.md`](./roadmap.md) for current stage, next steps, and limitations.
