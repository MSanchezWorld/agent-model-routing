# Proposal: model watch and route review

Proposed 2026-09-25. This is a **proposal-only** review process. A new leaderboard rank, release, or vendor price does not change the active route. The owner chose to approve each recommendation before a default changes.

## Cadence and signal sources

Run one quiet review **twice a week, Monday and Thursday**, with an earlier manual review when a new model directly affects an active task or a current route fails. Reuse the existing routing-review automation rather than creating another monitor. Its current prompt covers Codex only; updating it requires an approved automation change. Stay silent when nothing material changed.

| Signal | Sources to check | What it can establish |
| --- | --- | --- |
| Release, access, retirement, model options | Official [OpenAI](https://openai.com/news/), [Anthropic](https://www.anthropic.com/news), [xAI](https://x.ai/news), [Qwen](https://github.com/QwenLM), and [TypeSafe](https://typesafe.ai/blog/) announcements and current documentation | Candidate exists, its advertised capabilities, and whether an access path needs verification. Vendor claims are not workspace results. |
| Coding agent quality, cost and time | [Artificial Analysis Coding Agent Index](https://artificialanalysis.ai/agents/coding-agents) and its [methodology](https://artificialanalysis.ai/methodology/coding-agents-benchmarking); official [SWE-bench](https://www.swebench.com/) as secondary evidence | Comparative performance for a defined agent, settings and benchmark suite. Do not treat an agent row as bare-model quality or compare scores across methodology versions without normalization. |
| Human preference for web and product design | [Arena Code/WebDev](https://arena.ai/leaderboard/code) and [leaderboard changes](https://arena.ai/company/leaderboard-changelog) | A crowd preference signal for that task distribution, with rank uncertainty and vote count. It cannot replace evaluation of the actual product design brief. |
| General capability, API price and speed | [Artificial Analysis model data and API](https://artificialanalysis.ai/api-reference), plus provider price pages | Candidate shortlist and API economics. Subscription allowance, local compute and API dollars remain separate. A free data API still requires a key and its own terms; do not activate it without an approved connection. |
| Miguel's task outcomes | Private, permission-safe comparison cards based on [the template](ROUTE_EVALUATION_TEMPLATE.md) | Accepted result, retries, repair, elapsed time, confirmed model/host, and usage for the real task family. This is the primary promotion evidence. Never publish private prompts or artifacts. |

## What the review does

1. Read the active route version, previous candidate snapshot and last evidence date. Fetch only sources that are relevant and accessible. Record each source's publication date, observation date, benchmark version, model/configuration, and any changed terms or prices. Unknown is not zero.
2. Check **all eligible families**, including proprietary subscriptions and open weights that fit each available host. Compare candidates **within the same task family and harness** where possible. A newly released model starts as `discovered`; it is not inserted at the top of every list.
3. Flag a potential change only for a relevant release, changed access or economics, a robust benchmark movement, a route failure, or better local task evidence. Ignore tiny leaderboard movements inside uncertainty and marketing-only announcements. If a benchmark changes its rubric, treat its old and new scores as different series.
4. For a plausible challenger, propose a bounded comparison on representative tasks with a frozen acceptance check. Design uses blinded review of rendered results; coding uses verified behavior and maintainability. Track complete cost to an accepted result, not only input-token price. Keep new paid runs within an owner-approved cap.
5. Write a short recommendation: task type; current order; proposed order; why; source dates; access and host checks; task sample; quality and cost evidence; uncertainty; fallback; rollback condition. Open a sanitized PR when the public route would change. **Wait for owner approval** before merging it, changing settings, or updating the active dispatcher.

Notify the owner only for a material proposed reorder, lost availability of an active route, a material regression, or input/approval required to check a serious candidate. A routine scan with no action produces no notification. A review that could not access a source says what was unavailable; it never silently treats the missing source as proof that nothing changed.

## Promotion rule

The default remains the incumbent until a challenger clears the task's quality floor and either improves the accepted result or reduces the complete cost at comparable quality on relevant work. Record sample size, uncertainty and the cost unit. An open-weight model is evaluated on the **actual host and quantization** proposed for use. A subscription's quota must be checked through a supported interface or an observed limit response. If evidence is insufficient, keep the incumbent and schedule a targeted comparison rather than guessing a new ranking.

After owner approval, publish the new route version, reconcile private host/account inventory and startup pointers, and verify that at least one intended task actually uses the new candidate. Keep the prior route for rollback. Do not infer that every agent or computer refreshed its pointer from a GitHub merge.
