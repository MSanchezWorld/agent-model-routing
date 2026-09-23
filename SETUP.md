# Use this guide on another computer

Anyone can read this public repository in a browser. To make it available locally, clone it:

```sh
git clone https://github.com/MSanchezWorld/agent-model-routing.git ~/agent-model-routing
```

Read `ROUTING.md` before choosing a model for substantial work. If you want Codex to find the local guide automatically, add a short pointer to your existing `~/.codex/AGENTS.md`:

```md
For substantial Codex work, read ~/agent-model-routing/ROUTING.md and choose a supported model and reasoning effort for the task. Verify the route against the current local model list. Report the intended route separately from the runtime model.
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

The guide does not change an active chat's model. Select a different model in the Codex interface when a particular task calls for one. To refresh a local clone later:

```sh
git -C ~/agent-model-routing pull --ff-only
```

The public repository contains only routing guidance and example settings. Keep credentials, private project rules, and private conversation records in their authorized locations.
