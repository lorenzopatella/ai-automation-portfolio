# Content Generation — AI-Assisted Workflow

## Context

Brands and small teams need a steady flow of content — for social media, product communication, and broader brand messaging. Producing that content consistently is demanding: it requires turning loosely defined creative requests into finished outputs that respect brand identity and production constraints, repeatedly and at pace.

This project is a practical AI-assisted automation **workflow** built to support that production process. It is not a generic prompt collection, and it is not a finished SaaS product. It is presented here to demonstrate workflow orchestration, pragmatic use of AI for content, and the ability to design a system that non-technical users can interact with.

## Business Problem

Content production for brands and small teams typically suffers from:

- Creative requests that are vague, inconsistent, or incomplete
- Repetitive manual effort to produce similar content again and again
- Difficulty keeping outputs consistent with brand identity over time
- Multiple disconnected tools for text, image, and visual content
- Limited capacity, which makes it hard to keep up with demand

The result is slow, inconsistent output and a lot of time spent on coordination and rework rather than on the creative decisions that matter.

See [`business-case.md`](./business-case.md) for the full reasoning.

## Solution Overview

The workflow structures content production into a repeatable pipeline while keeping humans in control of creative judgment:

1. **Capture requests** through a simple, structured intake.
2. **Interpret the request** and turn it into clear, structured inputs.
3. **Use an AI generation / transformation layer** to support text, image, and/or visual content.
4. **Apply brand-consistency checks** so outputs align with defined guidelines.
5. **Output** content in a reviewable, ready-to-finalize format.
6. **Route everything through human review** before anything is published or delivered.

See [`architecture.md`](./architecture.md) for the high-level system design.

For a concrete example of the workflow in action — turning a short natural-language request into a presentation-ready product image — see [`demo-scenario.md`](./demo-scenario.md).

## What This Project Demonstrates

- Workflow orchestration for repeatable content production
- Pragmatic use of AI tools for text, image, and/or visual content support
- Turning loosely defined creative requests into structured inputs and outputs
- Awareness of brand consistency and production constraints
- Designing a practical system that **non-technical users** can interact with
- Confidentiality-conscious handling of prompts, assets, and workflow logic

## Stack Used

- **n8n** — workflow orchestration and automation logic
- **APIs and webhooks** — connecting tools and moving content through the pipeline
- **LLMs (ChatGPT / Claude / Gemini)** — request interpretation, text generation and workflow reasoning
- **AI image / visual tools** — supporting image generation, transformation and visual production workflows
- **GitHub Codespaces** — cloud development environment used to structure and iterate on the project
- **Claude Code / Codex** — AI coding assistants used for repository work, documentation, debugging support and workflow logic iteration
- **GitHub** — versioning, documentation and project organization

See the repository-level [`tools-and-stack.md`](../../tools-and-stack.md) for the broader toolset.

## What Is Intentionally Not Public

To protect creative know-how and any third-party assets, this repository does **not** include full workflows, exact prompts, private brand assets, internal creative direction, credentials, or any client/proprietary content.

See [`what-is-not-public.md`](./what-is-not-public.md) for the full list and the reasoning.

## Current Status

This is a working **prototype / project**, not a productized tool. The core production pipeline is defined and has been exercised on real content workflow design, but it is intended for supervised use and continued iteration rather than as a finished, autonomous system.

See [`roadmap.md`](./roadmap.md) for current stage, next steps, and limitations.
