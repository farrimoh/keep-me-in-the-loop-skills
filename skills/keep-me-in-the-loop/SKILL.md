---
name: keep-me-in-the-loop
description: Set up and run lightweight human-decision boundaries in a project. Use when the user asks to adopt a keep-me-in-the-loop protocol, define areas that require approval, or pause before consequential implementation, including scientific or domain-significant changes.
---

# Keep Me in the Loop

Keep routine work moving while preserving human control over explicitly designated areas. Use one project policy file and the project's existing agent instructions. Do not create a memory system, session log, enforcement engine, or transcript.

## Choose the mode

- Use **adoption** when the user asks to set up, initialize, or revise the protocol or its decision boundaries.
- Use **operation** when project instructions activate this skill or `KEEP_ME_IN_THE_LOOP.md` already exists.

## Adoption

1. Inspect existing `AGENTS.md`, `CLAUDE.md`, `KEEP_ME_IN_THE_LOOP.md`, and relevant project documentation. Do not overwrite or replace existing instructions.
2. Help the human identify only the areas where their judgment is important. Base proposed boundaries on the project's actual risks, such as architecture, external behavior, destructive operations, security, scientific meaning, domain assumptions, or difficult-to-reverse changes.
3. Prepare a reviewable proposal containing:
   - the exact `AGENTS.md` addition or merge, adapted from [assets/AGENTS.md](assets/AGENTS.md);
   - the proposed `KEEP_ME_IN_THE_LOOP.md`, adapted from [assets/KEEP_ME_IN_THE_LOOP.md](assets/KEEP_ME_IN_THE_LOOP.md); and
   - for Claude Code compatibility, an exact `CLAUDE.md` addition that imports `@AGENTS.md`, but only when the existing Claude instructions do not already provide equivalent activation.
4. Explain which areas will require a decision and which routine work will continue without approval.
5. Wait for explicit human acceptance before writing any adoption files. A discussion, recommendation, or silence is not acceptance.
6. Apply only the accepted merge. Preserve unrelated project instructions and avoid duplicating equivalent rules.
7. Show the resulting files and state that the protocol is instruction-based, not technical enforcement.

Do not choose consequential boundaries on the human's behalf. If the human gives only a broad goal, propose a narrow starting set and ask for a decision.

## Operation

1. Read the applicable agent instructions and `KEEP_ME_IN_THE_LOOP.md` before implementation.
2. Inspect the relevant code, documentation, tests, and evidence.
3. Classify intended work by its effect, not by diff size or filename:
   - If it does not touch an area requiring a decision, proceed and summarize normally.
   - If it touches a listed area, inspection and proposal logging may proceed, but implementation must stop.
4. Append a concise proposal to the decision log containing:
   - ID and title;
   - status `proposed`;
   - designated area and why it applies;
   - observed evidence;
   - proposed change and realistic alternatives;
   - recommendation, impact, risks, and verification plan; and
   - the decision requested from the human.
5. Present the same decision concisely in the conversation and wait. Provisional code, prior discussion, or an agent recommendation is not approval.
6. After an explicit response, record `accepted`, `rejected`, or `deferred`, with the accepted scope, decision-maker, and date.
7. Implement only an accepted scope. If another consequential choice appears, create a new proposal and stop again.
8. Record implementation and verification results in the same entry. Keep proposal, human decision, implementation, and verification distinct.

## Stop conditions

- Intended work touches a designated area without an explicit human decision.
- The accepted scope is ambiguous.
- Implementation exposes another consequential choice.
- Required verification cannot demonstrate the intended result.

## Boundaries

- Do not log every command, edit, or routine decision.
- Do not use this file as project memory, a plan, issue tracking, or a handoff log.
- Do not treat existing or provisional code as proof of approval.
- Do not claim that instructions provide a security boundary.

Read [references/decision-levels.md](references/decision-levels.md) when impact is difficult to classify. Read [references/scientific-workflow-example.md](references/scientific-workflow-example.md) only for scientific or model-significant work.
