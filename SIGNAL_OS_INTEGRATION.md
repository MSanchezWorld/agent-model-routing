# Signal OS first: routing integration

Proposed September 26, 2026. This extends the existing Signal OS work, rather than creating another product. It is an implementation handoff, not a deployed router or a change to active defaults.

## First useful outcome

For one task submitted from Signal OS, explain the recommended model, effort, supported access path and host; preserve the owner's dispatch approval; then show what actually ran and whether its result was accepted. Begin with the current supported adapter. Add providers individually after verifying their execution interfaces.

## Fit into the existing flow

1. **Before dispatch:** classify the task, read the approved versioned policy and private candidate inventory, and exclude unavailable or unsuitable candidates. Produce a recommendation and fallback with a reason. Keep the task's agent identity separate from its model and host.
2. **At claim:** recheck availability and applicable quota through a supported interface. Pin the approved route for this attempt; a newly published guide must not silently change an in-flight task.
3. **During execution:** use the existing worker and receipt boundaries. Record an unavailable route as an access failure. Fail over only after reconciling any completed side effects and preserving the task state. Unsupported subscription integrations produce a visible handoff.
4. **On return:** store intended and runtime-confirmed model, effort, access path, policy version, fallback reason, usage unit, elapsed time, acceptance result and repair count. Missing runtime or cost evidence remains unknown.
5. **For later review:** reuse existing usage collection and learning signals. Benchmark changes produce proposals for owner approval, never automatic default changes.

## Bounded first implementation

- Add a route recommendation object to a task/dispatch attempt without changing the existing adapter's behavior.
- Show its reason and availability in the existing dispatch review, with a manual override.
- Extend the return receipt with optional runtime and outcome fields; preserve older receipts.
- Join outcome and usage records by stable attempt ID. Do not guess usage from a nearby timestamp.
- Leave paid comparisons, additional adapters, automatic failover and schedule updates as separate steps.

## Acceptance evidence to gather when implementation is authorized

One app-originated task retains its route through queue, claim and return; older tasks still load; an unavailable candidate gives a clear fallback or handoff; an ambiguous side effect is not repeated; unavailable usage is visibly unknown. Confirm the actual serving model through the runtime before claiming a model switch. Local source checks are not phone acceptance or deployment proof.

Private source maps, account inventory, host addresses, credentials, prompts and usage reports stay outside this public guide. Reconcile the current app and worker branches before editing; recent work may be unmerged and the shared source can contain unrelated changes.

Related: [multi-provider design](MULTI_PROVIDER_ROUTING_PROPOSAL.md), [outcome template](ROUTE_EVALUATION_TEMPLATE.md), [model watch](MODEL_WATCH_PROPOSAL.md).
