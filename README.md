# LLM skills

Portable skills and writing preferences for AI assistants.

## Clear Technical Writing

[write-clear-english](skills/write-clear-english/SKILL.md) applies ASD-STE100-inspired principles adapted for software and everyday communication. Keep precise technical terms and simplify the language around them. Preserve conditions, uncertainty, exact technical references, and verification results.

The skill follows the open [Agent Skills specification](https://agentskills.io/specification). Clients that support this format can reuse the folder. Installation paths, activation, and instruction precedence depend on the client. Optional agents/openai.yaml metadata supplies OpenAI UI labels; the core instructions do not depend on it.

## Make the style the default

Use [the standing writing preference](skills/write-clear-english/assets/standing-instructions.md) in the harness's always-loaded instructions. The skill supplies fuller guidance and examples on demand. The standing preference contains the core rules, so they remain available without loading the skill.

| Harness | Standing instructions | Optional local skill folder |
| --- | --- | --- |
| Codex CLI | Append the preference to ~/.codex/AGENTS.md, or the equivalent under CODEX_HOME. | ~/.agents/skills/write-clear-english/ |
| Claude Code | Append the preference to ~/.claude/CLAUDE.md. | ~/.claude/skills/write-clear-english/ |
| Pi | Add the preference to ~/.pi/agent/APPEND_SYSTEM.md. | ~/.pi/agent/skills/write-clear-english/ |
| Other clients | Use the client's documented persistent instructions or application-controlled system prompt. | Use its Agent Skills installation mechanism, if supported. |

Preserve existing configuration when adding the preference. Check for project-level overrides and conflicting instructions. In Pi, a trusted project .pi/APPEND_SYSTEM.md takes precedence over the global file; files of the same name are not combined. If consistent policy inclusion across projects is needed, use a reviewed Pi extension to add the shared policy to each run's system prompt.

These instructions guide model behavior. They cannot guarantee every stylistic judgment or override higher-priority provider instructions, required schemas, or exact quotations. For custom harnesses, apply style checks to all relevant output paths, including prose written to files and PRs; changing terminal display alone will not cover saved artifacts.

## Add a skill

Create skills/your-skill-name/SKILL.md with YAML name and description fields followed by Markdown instructions. Use lowercase names with hyphens and keep the folder name equal to the skill name. Keep vendor-specific adapters optional and outside the core instructions.

## Validation

The first skill passed the skill creator's format validator. A sample PR rewrite preserved HTTP 503 eligibility, the idempotency requirement, 200 ms initial delay, doubling, a 3-second cap, unchanged HTTP 429 handling, uncertainty about recovery, and the distinction between unit tests run and integration tests not run. This is a limited behavior check, not a guarantee of model compliance or token savings.

## References

- [Agent Skills specification](https://agentskills.io/specification)
- [Codex standing instructions](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Codex skills](https://learn.chatgpt.com/docs/build-skills)
- [Claude Code memory and instructions](https://code.claude.com/docs/en/memory)
- [Claude Code skills](https://code.claude.com/docs/en/skills)
- [Pi configuration](https://docs.pi.dev/latest/configuration)
- [Pi extensions](https://docs.pi.dev/latest/extensions)
- [ASD-STE100 guidance](https://www.asd-ste100.org/STE_faq.html)

This repository contains an adapted writing style, not the ASD-STE100 specification or a compliance certification.
