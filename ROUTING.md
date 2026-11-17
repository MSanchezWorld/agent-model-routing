# Routing guide

Reviewed 2026-11-17 against the [GPT-6.2 release](https://openai.com/index/introducing-gpt-6-2-astra-sol/), [Codex guidance](https://learn.chatgpt.com/docs/agent-configuration/subagents), current runtime catalog and [credit rates](https://learn.chatgpt.com/docs/pricing). These are starting judgments, not locally benchmarked winners.

## Choose by task

Start general work with **GPT-6.2 Sol / medium / Standard** when available. Keep cheaper candidates for bounded work; use Astra for a consequential subtask, not as an always-running project manager.

| Work | Starting route | Change when |
| --- | --- | --- |
| Mechanical edits, formatting, extraction, known fixes, simple documentation | GPT-6 Luna / low | Use GPT-6.2 Sol / low or medium if requirements interact or judgment matters |
| Visual reasoning, bounded computer use, concise writing, scoped fixes | GPT-6.1 Terra / medium | Use low for clear small tasks; Sol medium for interacting requirements or a demonstrated capability gap |
| Routine engineering, integrations, normal debugging, bounded review | GPT-6.2 Sol / medium | Use GPT-6 Luna / low or medium for a clear repeated workflow; compare GPT-6.2 Astra / low when ambiguity or rework risk is material |
| Demanding coding, multi-step computer work, research synthesis, ambiguous planning | GPT-6.2 Sol / medium or high; GPT-6.2 Astra / low when justified | Raise Astra to medium or high when evidence and consequence justify the added reasoning |
| Consequential decisions, novel security/recovery design, unresolved hard failures | GPT-6.2 Astra / medium or high | Use xhigh or max only for exceptional remaining uncertainty; use GPT-6.2 Sol / high when it meets the quality bar at lower total cost |

Always choose both model and effort. Route by the task rather than assigning every task in a project to the strongest model. State why Astra is needed and return routine implementation to Sol once that subtask is resolved. Terra visual and low-effort fallback routes remain provisional pending representative checks. If Luna is unavailable, consider Terra / low for clear work with an acceptance check before Sol / low. Previous Sol 6.1 and Astra 6 remain availability fallbacks after verifying runtime support.

One agent is the default. Delegation still requires local authorization and independent work worth its coordination cost. A routing document does not switch an active chat. Reusable desktop profiles and pinned production workers are separate: do not bulk-upgrade qualified workers without their own tests and release process.

## Credit rates and limits

Standard credits per million input / cached input / output tokens, checked 2026-11-17:

| Model | Credits |
| --- | --- |
| GPT-6 Luna | 2.5 / 0.25 / 12.5 |
| GPT-6.1 Terra | 25 / 1.25 / 125 |
| GPT-6.2 Sol | 50 / 2.5 / 250 |
| GPT-6.2 Astra | 200 / 10 / 1,000 |
| GPT-6.1 Sol (availability fallback) | 50 / 2.5 / 250 |
| GPT-6 Astra (availability fallback) | 250 / 25 / 1,250 |

Complete task cost includes reasoning, retries, tools and review. Vendor benchmark savings are not evidence of savings on your work. Subscription allowance, purchased credits and API billing are distinct.

Keep Standard speed as the default. For 6.2, Fast consumes 2x included usage and credits. Ultrafast consumes 6x included usage; eligible purchased-credit/PAYG pricing is 3x through February 28, 2027, then 6x. Verify eligibility before use; this guide authorizes no spending or speed change. [Pricing](https://learn.chatgpt.com/docs/pricing)

## Reasoning effort and evidence

The checked Codex catalog lists low, medium, high, xhigh, max and ultra for both 6.2 models, with **low** as its default. Our general route explicitly chooses **medium**. Check your runtime rather than assuming API and app defaults match. Use xhigh/max only for concrete exceptional uncertainty under local rules. The `ultra` effort mode can delegate automatically; it is separate from Ultrafast speed. Neither is enabled by this guide.

Preserve raw failures privately and report unresolved blockers. Require independent tests or review evidence before calling work complete; a self-report or model vote is not acceptance. Compare accepted quality, retries, latency and full usage before promoting an unmeasured route.

## Claude routes

Added 2026-11-12; checked 2026-11-16 against Anthropic's [model-choice guidance](https://platform.claude.com/docs/en/about-claude/models/choosing-a-model), [cost and intelligence guide](https://platform.claude.com/docs/en/about-claude/models/optimizing-for-cost-and-intelligence) and [Claude Code model configuration](https://code.claude.com/docs/en/model-config). The rows did not change. This section maps Claude models to work for people who run Claude alongside Codex. No comparison on equivalent tasks has been run, so treat every row as a starting judgment.

The rule: **route by the cost of a wrong answer and whether an automatic check can catch it.** If tests, schemas, hashes or scripts verify the output, use the cheaper model and rely on the check. If nothing can check it (taste, meaning, strategy, security judgment), use the strongest model you already have access to.

| Work | Start with | Change when |
| --- | --- | --- |
| Simple extraction, classification, formatting, status notes, file inventories | Claude Haiku 5.5 / low | Use Sonnet 5.5 when requirements interact or the note needs judgment. |
| Bounded drafting, routine review, small scoped code fixes, gathering research | Claude Sonnet 5.5 / medium | Use Opus 5.5 for substantial judgment or a consequential review. |
| Planning, architecture, code and security review, research conclusions, writing in a specific person's voice, visual judgment of images or video frames | Claude Opus 5.5 / medium | Raise to high for consequential releases, unresolved edge cases, or taste decisions that nothing else checks. |
| Exceptional reasoning and long-horizon work | Claude Fable 5.2 / high | Only with existing account access and a task-specific benefit; use Opus 5.5 if it meets the acceptance check. |
| Repeated release checks (HTTPS, hashes, frozen pages) | No model: a deterministic script | A model only reads the script's result. |

When both providers are available, have a reviewer from a different provider than the builder check substantial work. Select an exact model and effort for any review you want to attribute; account defaults and aliases can change with releases. A documented model is not proof that your account, plan or client can use it. Check the model your runtime actually reports.

### Mixing Claude models

Anthropic's guidance as of 2026-11-16, with what it means for these routes:

- **Start with Opus 5.5 at its default effort.** Anthropic says most workloads start there. Move to Fable 5.2 only when Opus 5.5 at its highest effort still falls short on demanding or long-running work.
- **Tune effort before switching models.** Claude Code now defaults Fable 5.2, Opus 5.5, Sonnet 5.5 and Haiku 5.5 to medium. A saved setting that forces a higher effort overrides that on every session.
- **Escalate by failure where a check exists.** For work with tests, run at low effort and re-run only the failures at high. Anthropic measured about 40% lower cost at the same pass rate.
- **Advisor (experimental).** A cheaper main model consults a stronger one at decision points. Anthropic's own measurements showed small gains, some within noise, and it helps only on long multi-step tasks where the main model actually consults. Treat it as a candidate for large refactors or stubborn bugs, not a default.
- **Orchestrator with cheaper helpers.** For work that splits into independent pieces, an Opus 5.5 lead with Sonnet 5.5 helpers matched Opus 5.5 alone for about a third less. Claude Code helpers inherit the main model unless their definition sets one, so set it explicitly. Don't use this for one dependent chain of work.

These are vendor measurements, not results from equivalent tasks in this workspace.

## How to improve the route

For recurring work, compare models on equivalent tasks with the same acceptance checks. Record usable result, retries, tokens or credits, elapsed time, and tool or review effort. Keep the least expensive route that reliably meets the quality bar. Record the date and evidence when changing a recommendation. Do not publish private prompts, customer material, credentials, or unsupported savings claims as proof.
