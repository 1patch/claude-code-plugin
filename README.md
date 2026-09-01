> **Generated repository.** Source of truth: [`1patch/cli`](https://github.com/1patch/cli) (`plugins/claude-code`). Do not open PRs here.

# OnePatch — Claude Code plugin

[OnePatch](https://onepatch.dev) is the AI SRE: it ingests your OpenTelemetry
data and runs an always-on agent over your production systems. This plugin
gives Claude Code:

- the **OnePatch MCP server** (`https://app.onepatch.dev/mcp`) — query
  telemetry with SQL, read and drive incidents, delegate investigations to the
  OnePatch agent. OAuth sign-in happens in your browser on first use.
- an **`onepatch` skill** that teaches the agent when and how to use it.
- a **UserPromptSubmit hook** that injects a one-line open-incidents digest
  into each turn (needs the `onepatch` CLI; served from a local cache, so
  prompts are never delayed; silent when logged out or when nothing is open).

## Install

**Preferred (one command, wires every agent on the machine):**

```sh
npm install -g onepatch
onepatch install
```

**Manual:**

```sh
claude plugin marketplace add 1patch/claude-code-plugin
claude plugin install onepatch@onepatch
```

Then authenticate the `onepatch` MCP server when prompted (or via `/mcp`).

## Updates

Claude Code refreshes the marketplace and picks up new plugin versions on its
own; there is nothing to run.
