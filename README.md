# Codex agent model routing

- **Current starting route:** GPT-6 Sol / medium / Standard.
- **Last reviewed:** 2026-09-23.
- **Scope:** Codex GPT-6 model selection. Other agent runtimes need their own model and effort mapping.

This public guide helps choose a model for a task while accounting for quality, token use, retries, tools, and review effort. It is a set of recommendations, not an automatic router or a claim that one model has been proven cheapest for every task.

| Work | Starting route |
| --- | --- |
| Clear, repetitive edits or extraction | GPT-6 Luna / low |
| Most app building, debugging, research, and integration work | GPT-6 Sol / medium |
| Ambiguous work where stronger reasoning may prevent rework | GPT-6 Astra / low |
| Consequential architecture, benchmark validity, or unresolved hard problems | GPT-6 Astra / medium; raise effort only when needed |

See [the full routing guide](ROUTING.md) for exceptions and cost limits. [Agent instructions](AGENTS.md) explain how to use and review it. [Set up another computer](SETUP.md) to use the guide without access to a private file store. [Changes](CHANGELOG.md) records reviewed revisions.

The starting points follow [OpenAI's Codex subagent guidance](https://learn.chatgpt.com/docs/agent-configuration/subagents) and [model selection guide](https://developers.openai.com/api/docs/guides/model-selection). [Codex credit rates](https://learn.chatgpt.com/docs/pricing) help compare token prices. There is no published benchmark here showing which route minimizes complete task cost for a specific workspace.

## Keeping this useful

Check the review date before relying on model availability or prices. Recheck official documentation and the model list in your own Codex runtime. Update this guide when those facts change or when comparable task results support a different route. A date changes only after a real review; a recommendation does not become a measured result because it was published here.
