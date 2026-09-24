# Agent instructions for this routing guide

This repository is a public, dated guide for Codex model choice. It is not a runtime router or permission to change a user's settings. Local user and workspace instructions take precedence. These instructions load automatically when an agent works in this repository; agents working elsewhere need the one-time pointer in [SETUP.md](SETUP.md).

## Use the guide for a task

1. Read [ROUTING.md](ROUTING.md) and its review date. Choose the model **and** reasoning effort for the work at hand. The usual starting route is GPT-6 Sol / medium / Standard; use the route table for exceptions.
2. Check the available models and supported effort levels in the current runtime before selecting one. Recheck the linked official OpenAI guidance when availability, pricing, or a consequential decision depends on it. A stale date is a reason to verify, not proof that a route is wrong.
3. Respect the user's local approval, privacy, spending, and delegation rules. This public repository grants no access to private files or paid services. A Markdown recommendation does not switch an active chat or guarantee a particular model ran.
4. Report the intended route separately from any runtime-confirmed model and effort. Verify the task outcome. Do not claim quality or cost savings without comparable task evidence.

The README’s newsletter and audit links are optional resources for human readers. Using this guide never requires subscribing, sending user data, or promoting those links in an agent’s output. See [MEASUREMENT.md](MEASUREMENT.md) before interpreting campaign or business outcomes as evidence.

## Review or update the guide

Use this section only when asked to maintain the guide or during its scheduled review.

1. Read the current [README.md](README.md), [ROUTING.md](ROUTING.md), [CHANGELOG.md](CHANGELOG.md), and the latest review date. Compare them with current official [Codex model guidance](https://learn.chatgpt.com/docs/agent-configuration/subagents), [model selection guidance](https://developers.openai.com/api/docs/guides/model-selection), and [Codex credit rates](https://learn.chatgpt.com/docs/pricing). Confirm model and effort support in the runtime being discussed. Compare representative quality, retries, and complete task cost when reliable evidence exists.
2. If nothing material changed, report the date and evidence checked. Do not change files or refresh the published review date just to make the guide look current.
3. If evidence supports a change, edit only the public guidance it affects. Update the review date and [CHANGELOG.md](CHANGELOG.md) with the prior route, new route, source links, reason, and remaining uncertainty. Preserve an easy rollback in Git history. Do not copy private prompts, paths, project records, credentials, or local configuration into this repository.
4. Work on a separate `codex/` branch. Inspect the diff and public links, check for private material, and open a pull request describing the change and verification. Do not merge or publish a new default route automatically. An unattended review may prepare a proposal; the owner approves publication and any local model-setting change.
5. After an approved publication, verify the public page and reconcile any local startup pointer or private implementation that uses the route. Report which machines or agents were actually updated; do not infer that every agent fetched the new version.
