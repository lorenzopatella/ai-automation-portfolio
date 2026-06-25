# Architecture — Real Estate Sourcing

This document describes the **high-level** system design of the workflow. It intentionally stays at the conceptual level and does not expose implementation details, sourcing methods, prompts, or scoring rules. The goal is to show how the pipeline is structured, not how to reproduce it.

## Design Principles

- **Staged pipeline.** Each stage has a clear, single responsibility.
- **Structure early.** Raw inputs are normalized as soon as possible so everything downstream is consistent.
- **AI-assisted, human-decided.** AI accelerates structuring and pre-qualification; humans make decisions.
- **Confidentiality by design.** Sensitive logic and data are kept out of scope by default.

## Layers

### 1. Input Layer
Collects incoming opportunities from defined sources via APIs, webhooks, or structured imports. Responsible only for capturing raw input and passing it forward. (The specific sources and collection methods are not disclosed.)

### 2. Processing Layer
Cleans and **normalizes** raw inputs into a consistent internal format. Handles deduplication, basic validation, and field standardization so that every opportunity is represented the same way regardless of its origin.

### 3. AI / LLM Layer
Uses an LLM to interpret the **unstructured** parts of an opportunity — for example, summarizing free-text descriptions and extracting key details into structured fields. This layer turns messy text into clean, comparable data. (Prompts and exact instructions are not disclosed.)

### 4. Scoring / Qualification Layer
Applies defined qualification criteria to flag, filter, and prioritize opportunities. The output is a relative ordering / shortlist rather than a final decision. (The actual criteria and weighting are proprietary and not disclosed.)

### 5. Output Layer
Presents the structured, qualified results in a reviewable format (e.g. a structured list or table) so they are easy to scan, filter, and act on.

### 6. Human Review Layer
A person reviews the shortlist, validates the structured information, and makes the actual decisions. No opportunity proceeds on the basis of automation alone. This layer is where accountability and final judgment sit.

## Text-Based Flow Diagram

```
        ┌──────────────────────────────────────────────┐
        │              1. INPUT LAYER                    │
        │   Opportunities from defined sources           │
        │   (APIs / webhooks / structured imports)       │
        └───────────────────────┬────────────────────────┘
                                 │  raw input
                                 ▼
        ┌──────────────────────────────────────────────┐
        │           2. PROCESSING LAYER                  │
        │   Clean • deduplicate • normalize fields       │
        └───────────────────────┬────────────────────────┘
                                 │  structured records
                                 ▼
        ┌──────────────────────────────────────────────┐
        │            3. AI / LLM LAYER                   │
        │   Interpret & summarize unstructured text      │
        │   Extract key details into consistent fields   │
        └───────────────────────┬────────────────────────┘
                                 │  enriched records
                                 ▼
        ┌──────────────────────────────────────────────┐
        │       4. SCORING / QUALIFICATION LAYER         │
        │   Apply criteria • filter • prioritize         │
        └───────────────────────┬────────────────────────┘
                                 │  qualified shortlist
                                 ▼
        ┌──────────────────────────────────────────────┐
        │              5. OUTPUT LAYER                   │
        │   Structured, reviewable list / table          │
        └───────────────────────┬────────────────────────┘
                                 │  presented results
                                 ▼
        ┌──────────────────────────────────────────────┐
        │           6. HUMAN REVIEW LAYER                │
        │   Validate • decide • act (final judgment)     │
        └──────────────────────────────────────────────┘
```

## What This Architecture Deliberately Omits

This document does not include code, node-level workflow configuration, exact data sources, prompt content, or qualification criteria. Those elements are kept private — see [`what-is-not-public.md`](./what-is-not-public.md) for the full reasoning.
