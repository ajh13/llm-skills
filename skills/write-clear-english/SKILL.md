---
name: write-clear-english
description: Write and edit clear, precise English using ASD-STE100 principles adapted for software and everyday communication. Apply to human-facing prose, including ordinary answers, progress updates, PR descriptions, reviews, design documents, documentation, plans, task instructions, and handoff summaries. Use alongside other task skills to keep meaningful technical terms, simplify surrounding language, and preserve facts and uncertainty.
---

# Clear Technical Writing

Use ASD-STE100 Simplified Technical English principles adapted for the reader and task. Prioritize accuracy, clarity, and then brevity. Treat this as an adaptation; claim full standard compliance only after appropriate validation.

## Write clearly

- Lead with the answer, decision, or concrete behavior change.
- Prefer active voice, direct verbs, and sentences with one main idea. Name the actor when it matters.
- Keep established technical terms when they add precision. Use one term consistently for each concept.
- Explain a term once when the reader needs it. Match the reader's expertise; avoid turning routine engineering communication into a beginner tutorial.
- Simplify surrounding language: use "use" for "utilize" and "start" for "commence." Replace abstract noun stacks with concrete actions.
- Preserve conditions, exceptions, quantities, causal relationships, and uncertainty. Keep words such as "may," "only," "after," and "unless" when they affect meaning.
- Preserve exact identifiers, commands, paths, API names, quotations, and evidence when referring to them. Edit these only when the task requires it.
- Remove filler, repetition, inflated wording, and invented terminology. Use headings and lists only when they improve navigation or comparison.
- Scale detail to the task. Prefer short sentences without enforcing a word limit that distorts meaning. Avoid extra model calls solely for a style pass.

## Combine with the task

Keep other skills' subject matter, required sections, and output formats. Apply this style to the prose inside those structures. Follow the user's explicit communication preferences when they conflict with a skill's style defaults, subject to the harness's instruction hierarchy. Preserve required machine-readable syntax and verbatim material.

For PRs, state the problem, resulting behavior, rationale, and relevant verification. Distinguish checks that passed, failed, or were not run. For design documents, retain assumptions, alternatives, tradeoffs, failure cases, and open questions. For summaries and handoffs, retain decisions, constraints, evidence, unresolved issues, and next actions.

Before delivering, check that the text says who does what, uses necessary technical terms accurately, and preserves the source meaning. Report only work and verification actually performed.

## Examples

Rewrite "The client utilizes exponential backoff to mitigate excessive request volume during transient upstream failures" as "The client uses exponential backoff to space out retries when the upstream service temporarily fails."

Rewrite "This may result in credential disclosure if debug logging is enabled" as "If debug logging is enabled, credentials may appear in the logs." Preserve the condition and uncertainty.

Keep "race condition," "idempotent," and "exponential backoff" when appropriate. Avoid replacing them with vague claims such as "timing issue," "safe," or "wait a bit."

## Apply as a standing preference

For every-response coverage, place [the standing instructions](assets/standing-instructions.md) in the harness's always-loaded user instructions as well. A skill can load on demand; its presence alone does not enforce use on every turn. Reuse this folder in Agent Skills-compatible clients and confirm each client's installation and instruction precedence. Treat skill discovery, installation paths, and enforcement as harness-specific.
