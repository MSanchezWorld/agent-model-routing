# Routing guide

Reviewed 2026-10-01 against the current Codex model guidance, model availability and credit table. **Proposed update for owner review; not an active default until approved and merged.** Start with the lowest model and reasoning effort likely to deliver a complete result. Verify the outcome before treating a cheaper route as successful.

## Choose by task

| Task | Start with | Change when |
| --- | --- | --- |
| Mechanical edits, extraction, formatting, simple documentation, or a known fix | GPT-6 Luna / low | Use GPT-6.1 Sol / low or medium when requirements interact or judgment matters. |
| Normal app development, integrations, debugging, research, and bounded review | GPT-6.1 Sol / medium | Use Luna for clear repeatable work; use GPT-6 Sol / medium where 6.1 is unavailable. |
| Demanding code or planning with several interacting constraints | GPT-6.1 Sol / medium or high | Compare Astra / low or medium when errors or rework could outweigh the added cost. |
| Consequential architecture, benchmark methodology, security or recovery design, and stubborn failures | GPT-6 Astra / medium | Raise to high for unusually hard unresolved reasoning; compare GPT-6.1 Sol / high where it clears the same quality bar. |

For one ongoing app build, GPT-6.1 Sol / medium is the proposed usual chat setting when available. Use a focused Astra task for a difficult design or review decision. For an evaluation system, establish consequential measurement rules with Astra / medium, then use GPT-6.1 Sol / medium for implementation of settled requirements. These are starting judgments, not measured winners for every project. Availability depends on the account, client and rollout; use the previous Sol route if 6.1 is unavailable. [OpenAI models](https://learn.chatgpt.com/docs/models)

One agent is a conservative default. Add another agent only when independent work is worth the context, coordination, and review cost and local authorization permits it. Pass the exact model and reasoning effort to any worker; a name or Markdown instruction alone does not switch its runtime.

## Credit rates and limits

[Standard Codex credit rates](https://learn.chatgpt.com/docs/pricing), checked 2026-10-01, per million input / cached input / output tokens:

| Model | Credits |
| --- | --- |
| GPT-6 Luna | 2.5 / 0.25 / 12.5 |
| GPT-6.1 Sol | 50 / 2.5 / 250 |
| GPT-6 Sol | 50 / 5 / 250 |
| GPT-6 Astra | 250 / 25 / 1,250 |

Astra's listed input and output rates are 5 times GPT-6.1 Sol's; GPT-6.1 Sol's cached-input rate is half GPT-6 Sol's. Complete task cost can differ because models may use different amounts of reasoning and output, repeat failed attempts, call tools, or require human review. These rates do not determine a subscription allowance, and API prices use a separate rate card. Standard speed is the cost baseline; purchased-credit Fast usage is currently listed at 2 times Standard where available. [OpenAI pricing](https://learn.chatgpt.com/docs/pricing)

## Reasoning effort

[OpenAI's Codex guidance](https://learn.chatgpt.com/docs/agent-configuration/subagents) now starts most tasks with GPT-6.1 Sol when available. [Its API model page](https://developers.openai.com/api/docs/models/gpt-6.1-sol) lists low, medium (default), high, xhigh and max effort; none and minimal are unsupported. Client controls may differ. A higher effort can improve difficult work but also increases response time and token use. Check the selected model's supported effort levels in your own runtime before applying a route. Do not treat effort labels as equivalent intelligence or cost across models.

## How to improve the route

For recurring work, compare models on equivalent tasks with the same acceptance checks. Record usable result, retries, tokens or credits, elapsed time, and tool or review effort. Keep the least expensive route that reliably meets the quality bar. Record the date and evidence when changing a recommendation. Do not publish private prompts, customer material, credentials, or unsupported savings claims as proof.
