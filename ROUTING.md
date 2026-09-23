# Routing guide

Reviewed 2026-09-23 against the current Codex model guidance and credit table. Start with the lowest model and reasoning effort likely to deliver a complete result. Verify the outcome before treating a cheaper route as successful.

## Choose by task

| Task | Start with | Change when |
| --- | --- | --- |
| Mechanical edits, extraction, formatting, simple documentation, or a known fix | GPT-6 Luna / low | Use Sol / medium when requirements interact or judgment matters. |
| Normal app development, integrations, debugging, research, and bounded review | GPT-6 Sol / medium | Use Luna for clear repeatable work; try Astra / low when ambiguity or costly rework is material. |
| Demanding code or planning with several interacting constraints | GPT-6 Astra / low or Sol / medium | Raise Astra to medium if the unresolved decisions require more depth. |
| Consequential architecture, benchmark methodology, security or recovery design, and stubborn failures | GPT-6 Astra / medium | Raise to high for unusually hard unresolved reasoning; use Sol / high when task evidence shows it meets the same quality bar. |

For one ongoing app build, Sol / medium is the usual chat setting. Use a focused Astra task for a difficult design or review decision. For an evaluation system, establish the measurement rules with Astra / medium, then use Sol / medium for implementation of settled requirements. These are starting judgments, not measured winners for every project.

One agent is a conservative default. Add another agent only when independent work is worth the context, coordination, and review cost and local authorization permits it. Pass the exact model and reasoning effort to any worker; a name or Markdown instruction alone does not switch its runtime.

## Credit rates and limits

[Standard Codex credit rates](https://learn.chatgpt.com/docs/pricing), checked 2026-09-23, per million input / cached input / output tokens:

| Model | Credits |
| --- | --- |
| GPT-6 Luna | 2.5 / 0.25 / 12.5 |
| GPT-6 Sol | 50 / 5 / 250 |
| GPT-6 Astra | 250 / 25 / 1,250 |

Astra's listed rate is 5 times Sol's in each token category; Sol's is 20 times Luna's. Complete task cost can differ because models may use different amounts of reasoning and output, repeat failed attempts, call tools, or require human review. These rates do not determine a subscription allowance, and API prices use a separate rate card. Standard speed is the cost baseline; Fast uses 2.5 times the GPT-6 Codex credits where available.

## Reasoning effort

[OpenAI's Codex guidance](https://learn.chatgpt.com/docs/agent-configuration/subagents) starts Sol at medium and Astra at low. A higher effort can improve difficult work but also increases response time and token use. Check the selected model's supported effort levels in your own runtime before applying a route. Do not treat effort labels as equivalent intelligence or cost across models.

## How to improve the route

For recurring work, compare models on equivalent tasks with the same acceptance checks. Record usable result, retries, tokens or credits, elapsed time, and tool or review effort. Keep the least expensive route that reliably meets the quality bar. Record the date and evidence when changing a recommendation. Do not publish private prompts, customer material, credentials, or unsupported savings claims as proof.
