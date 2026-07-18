# Keep Me in the Loop

A lightweight Agent Skill that sets up and applies project-specific human decision boundaries. Routine work proceeds while the human stays in control of consequential choices.

The skill works with Claude Code, Codex, Hermes Agent, and other clients that implement the [Agent Skills specification](https://agentskills.io/specification).

## What it does

```text
Inspect → notice a boundary → log the choice → ask the human
                                              ↓
                              implement only after acceptance
                                              ↓
                                    record and verify the result
```

The skill has two modes:

- **Adoption:** propose the project's activation rule and decision boundaries, then wait before writing them.
- **Operation:** apply accepted boundaries to ongoing work.

Projects identify specific areas where human judgment is required. Typical examples are architecture, public behavior, destructive operations, security, scientific meaning, domain assumptions, and difficult-to-reverse changes.

When work touches one of those areas, the agent:

1. Writes a short proposal in `KEEP_ME_IN_THE_LOOP.md`.
2. Shows the decision to the human.
3. Waits for an explicit `accepted`, `rejected`, or `deferred` decision.
4. Implements only the accepted scope.
5. Records the implementation and verification result.

Routine implementation work proceeds normally and is summarized without filling the decision log.

## What it does not do

- No project memory system
- No session logs or handoffs
- No hooks or enforcement engine
- No authorization database
- No agent orchestration
- No logging of every command or edit

This is a collaboration protocol, not a security boundary.

## Project adoption

After installing, ask your agent:

```text
Use keep-me-in-the-loop to adopt the protocol in this project.
```

The skill inspects existing project instructions and proposes a merge for review. It never silently overwrites `AGENTS.md`, `CLAUDE.md`, or an existing policy.

An adopted project uses:

- `AGENTS.md` to activate the installed skill for Codex, Hermes, and compatible agents;
- `CLAUDE.md` to import the activation rule when Claude Code support is needed; and
- `KEEP_ME_IN_THE_LOOP.md` to define the accepted decision boundaries and hold concise decision entries.

The proposed policy starts with this shape:

```markdown
# Keep Me in the Loop

## Areas requiring a decision

- Changes to public behavior
- Destructive or difficult-to-reverse operations

## Decision log
```

The project decides which areas belong in the list. Decision entries remain concise and keep proposal, human decision, implementation, and verification distinct.

## Install with Claude Code

Test from a clone:

```bash
claude --plugin-dir .
```

After hosting the repository:

```text
/plugin marketplace add OWNER/REPOSITORY
/plugin install keep-me-in-the-loop@keep-me-in-the-loop
```

## Install with Codex

Add the repository as a plugin marketplace:

```bash
codex plugin marketplace add OWNER/REPOSITORY
```

Open `/plugins` in Codex, select the marketplace, and install **Keep Me in the Loop**. Start a new session before using the installed skill.

## Install with Hermes Agent

The repository is a Hermes-compatible skill tap:

```bash
hermes skills tap add OWNER/REPOSITORY
hermes skills install OWNER/REPOSITORY/keep-me-in-the-loop
```

## Other Agent Skills clients

Install the `skills/keep-me-in-the-loop` directory using the client's native skill installer or place it in that client's documented skills directory.

## Project instructions

The installed skill includes a concise `AGENTS.md` activation template. During adoption, the agent adapts and merges that template only after explicit human acceptance. Installing the skill by itself does not modify any project.

## Scientific example

The same lightweight pattern can identify scientific-model changes as decision areas while allowing ordinary logging, parsing, and invariant-preserving refactoring to proceed. The installed skill includes a neutral scientific example under `references/` and reads it only for scientific or model-significant work.

Licensed under the [Apache License 2.0](LICENSE).
