# Roadmap — Real Estate Sourcing

This roadmap shows how the project is intended to evolve. It is written in terms of direction and priorities, not commitments or timelines, and it reflects an honest view of where the work currently stands.

## Current Stage

- A working **prototype** with a defined staged pipeline (input → processing → AI → qualification → output → human review).
- Core structuring and normalization logic is in place and has been exercised on real workflow design.
- AI is used in a supervised, assistive role; humans make all decisions.
- The project is intended for **supervised use and continued iteration**, not as a finished or autonomous system.

## Next Improvements

Near-term priorities to make the workflow more robust and useful:

- **Strengthen input handling** to support a wider range of source formats consistently.
- **Improve normalization** so structured records are more complete and reliable.
- **Refine the qualification step** so prioritization is clearer and easier to adjust.
- **Improve the output presentation** so reviewers can scan, filter, and act faster.
- **Add lightweight logging/traceability** so it is easy to see why an opportunity was flagged or prioritized.

## Possible Future Features

Longer-term directions worth exploring (not committed):

- Configurable qualification criteria that can be tuned per user or use case.
- Better handling of duplicates and near-duplicates across sources.
- Optional notifications/alerts for high-priority opportunities.
- A simple feedback loop so human decisions can inform future prioritization.
- Integration with the tools a given user or team already relies on.

## Testing and Validation Priorities

To move beyond prototype quality, validation should focus on:

- **Output reliability** — checking that structured records faithfully represent the source.
- **Qualification quality** — reviewing whether prioritization matches expert human judgment on real examples.
- **Edge cases** — incomplete, malformed, or unusual inputs.
- **Human-in-the-loop effectiveness** — confirming the review step is practical and adds value rather than friction.
- **Consistency** — ensuring the same input produces stable, predictable structuring.

## Limitations

Stated honestly:

- This is a **prototype**, not a production-grade or autonomous product.
- Output quality depends on the quality and completeness of the input data.
- AI can misinterpret nuance or context, which is why human review is required.
- The qualification step supports decisions; it does not replace professional judgment.
- The project has not been validated at scale, and no performance metrics are claimed.
