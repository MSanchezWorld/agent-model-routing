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

## Follow the experiments

**The Miguel Sanchez World Report**

Weekly experiments on AI video, agency growth, and capital leverage.

**Follow the race to commercially reliable AI video.** Get one short weekly issue about what I’m testing. The planned topic preferences let you choose AI video, agency growth, capital leverage, or AI agents for more focused field notes.

[**Get the Weekly Report**](https://miguelsanchez.world/?utm_source=github&utm_medium=repository&utm_campaign=agent_routing&utm_content=readme_primary)

Want help applying AI to a business workflow? [Explore the AI workflow audit](https://growth.massideation.com/checkout/audit?brand_route=miguel_sanchez_world&utm_source=github&utm_medium=repository&utm_campaign=agent_routing&utm_content=readme_audit).

The guide remains freely available. These links use campaign tags to distinguish their source; they contain no personal identifiers. See [measurement and attribution](MEASUREMENT.md) for what the tags can and cannot prove.

Building the same kind of audience system? The [audience routing contract](AUDIENCE_ROUTING.md) defines sources, preferences, audience types, consent, and confirmed product events. [Entry page drafts](ENTRY_PAGES.md) contain the three topic promises. These documents describe the planned funnel; they do not claim its automation is live.
