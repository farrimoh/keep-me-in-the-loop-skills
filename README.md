# Keep Me in the Loop

**Keep routine work moving. Keep consequential decisions yours.**

A lightweight [Agent Skill](https://agentskills.io/specification) for agreeing on when a coding agent should pause, explain a choice, and wait for your decision. Packaged for Codex and Claude Code, with a portable skill directory for Hermes Agent and other compatible clients.

[Install](#install) · [Get started](#get-started) · [How it works](#how-it-works) · [Resources](#resources)

## Why use it?

You might want an agent to fix tests and refactor freely, but ask before changing a public API, deleting data, or altering a scientific model. This skill turns those preferences into explicit project boundaries and a concise decision log.

You choose the boundaries. The agent records the evidence, options, and recommendation when work reaches one, then implements the scope you accept.

## Install

Choose the route for your agent. Installation makes the skill available; project adoption is a separate step.

### Codex

Run in your terminal:

```bash
codex plugin marketplace add farrimoh/keep-me-in-the-loop-skills
codex plugin add keep-me-in-the-loop@keep-me-in-the-loop
```

Start a new session, then use the prompt below. See the [official plugin documentation](https://developers.openai.com/plugins/build/plugins) for marketplace setup and desktop installation options.

### Claude Code

Run inside Claude Code:

```text
/plugin marketplace add farrimoh/keep-me-in-the-loop-skills
/plugin install keep-me-in-the-loop@keep-me-in-the-loop
```

You can also try the plugin from a local clone by running `claude --plugin-dir .` at the repository root. See the [Claude Code plugin documentation](https://code.claude.com/docs/en/plugins).

### Hermes Agent

Run in your terminal:

```bash
hermes skills tap add farrimoh/keep-me-in-the-loop-skills
hermes skills install farrimoh/keep-me-in-the-loop-skills/keep-me-in-the-loop
```

See the [Hermes skills documentation](https://hermes-agent.nousresearch.com/docs/user-guide/features/skills) for taps and skill installation.

### Other compatible clients

Install the complete [skills/keep-me-in-the-loop](skills/keep-me-in-the-loop) directory with your client's native skill installer. Keep its `assets/` and `references/` folders alongside `SKILL.md`.

## Get started

Open the project you want to use it in and ask your agent:

```text
Use keep-me-in-the-loop to adopt the protocol in this project.
Propose boundaries for changes to public behavior and destructive operations.
```

The agent inspects existing instructions and shows you the proposed policy and exact instruction changes. After you accept, it merges them into the project:

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Activates the installed skill and its decision rules. |
| `CLAUDE.md` | Imports the activation rule when Claude Code support is needed. |
| `KEEP_ME_IN_THE_LOOP.md` | Defines your accepted boundaries and records decisions. |

Existing instructions are preserved. You review the proposed boundaries before any adoption files are written.

For ongoing work, ask normally or say:

```text
Apply keep-me-in-the-loop while implementing this change.
```

## How it works

1. **Inspect.** Read the project policy and relevant evidence.
2. **Classify.** Continue routine work; identify changes that touch an agreed boundary.
3. **Propose.** Log the choice, alternatives, recommendation, risks, and verification plan.
4. **Decide.** Wait for your explicit acceptance, rejection, or deferral.
5. **Implement and verify.** Apply only the accepted scope and record the result.

For example, if public API changes require a decision, renaming an internal helper may proceed normally. Removing a public endpoint requires a proposal and your acceptance first.

Each entry keeps the proposal, human response, implementation, and verification distinct. Routine edits and commands stay out of the log.

This is an instruction-based collaboration protocol. It has no hooks or enforcement engine and does not provide a security boundary. It adds no runtime dependencies, session logs, or project memory system.

## Resources

| Resource | Purpose |
| --- | --- |
| [Skill instructions](skills/keep-me-in-the-loop/SKILL.md) | Adoption and operation workflows. |
| [Activation template](skills/keep-me-in-the-loop/assets/AGENTS.md) | Instructions to merge into a project's `AGENTS.md`. |
| [Policy template](skills/keep-me-in-the-loop/assets/KEEP_ME_IN_THE_LOOP.md) | Project boundaries and a decision entry template. |
| [Decision levels](skills/keep-me-in-the-loop/references/decision-levels.md) | Guidance for classifying impact. |
| [Scientific example](skills/keep-me-in-the-loop/references/scientific-workflow-example.md) | Example boundaries for model changes and scientific claims. |

Plugin metadata lives in `.codex-plugin/` and `.claude-plugin/`. The native Codex marketplace is in `.agents/plugins/`; the Claude marketplace is in `.claude-plugin/marketplace.json`.

## Contributing

Keep changes focused and examples portable. Use repository-relative paths or clear placeholders, and keep shared plugin metadata consistent across both manifests.

Before submitting, check JSON syntax, relative Markdown links, and whitespace with `git diff --check`. If Claude Code is installed, run `claude plugin validate .` from the repository root. For workflow changes, describe a realistic example and the expected agent behavior in your pull request.

## License

[Apache License 2.0](LICENSE).
