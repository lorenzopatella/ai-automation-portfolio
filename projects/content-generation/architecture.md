# Architecture — Content Generation

This document describes the **high-level** system design of the workflow. It intentionally stays at the conceptual level and does not expose implementation details, prompts, brand assets, or production logic. The goal is to show how the pipeline is structured, not how to reproduce it.

## Design Principles

- **Staged pipeline.** Each stage has a clear, single responsibility.
- **Structure the request first.** Loosely defined creative requests are turned into structured inputs before generation begins.
- **AI-assisted, human-approved.** AI accelerates drafting and transformation; humans approve the final creative output.
- **Brand consistency by design.** Alignment with brand guidelines is a built-in step, not an afterthought.
- **Built for non-technical users.** Interaction happens through simple inputs, not code.
- **Confidentiality by design.** Sensitive prompts, assets, and logic are kept out of scope by default.

## Layers

### 1. Input Layer
Captures content requests through a **simple, structured intake** (e.g. a form or guided request) so non-technical users can submit work without needing to understand the underlying system. Responsible only for collecting the request and passing it forward.

### 2. Request Interpretation Layer
Turns a loosely defined creative request into **clear, structured inputs**: what is being produced, for which channel/context, with which constraints. This stage reduces ambiguity and prepares a clean brief for generation. (Exact interpretation prompts are not disclosed.)

### 3. AI Generation / Transformation Layer
Uses AI to support content creation — drafting **text**, and generating or transforming **image / visual** content as needed. This is where structured inputs become draft outputs. (Prompts, model configuration, and the visual pipeline details are not disclosed.)

### 4. Brand Consistency Layer
Checks and adjusts draft outputs against **defined brand guidelines** (tone, style, format, and visual identity at a conceptual level) so that what reaches review is already aligned. (The actual brand rules and assets are private and not disclosed.)

### 5. Output Layer
Presents the resulting content in a **reviewable, ready-to-finalize format**, organized so a reviewer can quickly assess and select what to keep.

### 6. Human Review Layer
A person reviews, refines, and **approves** the content before anything is published or delivered. No output is finalized on the basis of automation alone. This is where creative judgment and accountability sit.

## Text-Based Flow Diagram

```
        ┌──────────────────────────────────────────────┐
        │              1. INPUT LAYER                    │
        │   Structured content request (intake form)     │
        │   Submitted by non-technical users             │
        └───────────────────────┬────────────────────────┘
                                 │  raw request
                                 ▼
        ┌──────────────────────────────────────────────┐
        │       2. REQUEST INTERPRETATION LAYER          │
        │   Turn request into clear, structured inputs   │
        └───────────────────────┬────────────────────────┘
                                 │  structured brief
                                 ▼
        ┌──────────────────────────────────────────────┐
        │     3. AI GENERATION / TRANSFORMATION LAYER    │
        │   Draft text • generate/transform visuals      │
        └───────────────────────┬────────────────────────┘
                                 │  draft outputs
                                 ▼
        ┌──────────────────────────────────────────────┐
        │          4. BRAND CONSISTENCY LAYER            │
        │   Align tone • style • format • identity       │
        └───────────────────────┬────────────────────────┘
                                 │  brand-aligned drafts
                                 ▼
        ┌──────────────────────────────────────────────┐
        │              5. OUTPUT LAYER                   │
        │   Reviewable, ready-to-finalize content        │
        └───────────────────────┬────────────────────────┘
                                 │  presented outputs
                                 ▼
        ┌──────────────────────────────────────────────┐
        │           6. HUMAN REVIEW LAYER                │
        │   Review • refine • approve (final judgment)   │
        └──────────────────────────────────────────────┘
```

## What This Architecture Deliberately Omits

This document does not include code, node-level workflow configuration, prompt content, brand assets, creative direction, or the specifics of the visual pipeline. Those elements are kept private — see [`what-is-not-public.md`](./what-is-not-public.md) for the full reasoning.
