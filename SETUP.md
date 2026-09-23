# Use this guide on another computer

Anyone can read this public repository in a browser. To make it available locally, clone it:

```sh
git clone https://github.com/MSanchezWorld/agent-model-routing.git ~/agent-model-routing
```

Read `AGENTS.md` and `ROUTING.md` before choosing a model for substantial work. A GitHub link by itself does not make an agent load the guide while working in another repository. Add this pointer once to each agent's persistent startup instructions. For Codex, use the existing `~/.codex/AGENTS.md`; for another agent, use its equivalent startup file:

```md
At the start of a substantial new session, refresh the clean local clone at ~/agent-model-routing with `git -C ~/agent-model-routing pull --ff-only` when network access permits. Read its AGENTS.md usage section and ROUTING.md before choosing a supported model and reasoning effort. Follow its maintenance section only when asked to review the guide. Local user and workspace instructions take precedence. Report the intended route separately from the runtime model; do not infer that Markdown changed the active chat.
```

For a new Codex configuration, these are the current starting values. Merge them into your existing `~/.codex/config.toml`: place the top-level keys before any table, and add the agent keys inside an existing `[agents]` table if one is already present. Keep all other settings intact.

```toml
model = "gpt-6-sol"
model_reasoning_effort = "medium"
service_tier = "default"

[agents]
default_subagent_model = "gpt-6-sol"
default_subagent_reasoning_effort = "medium"
```

The guide does not change an active chat's model. Select a different model in the Codex interface when a particular task calls for one. To refresh a local clone manually:

```sh
git -C ~/agent-model-routing pull --ff-only
```

The public repository contains only routing guidance and example settings. Keep credentials, private project rules, and private conversation records in their authorized locations.
