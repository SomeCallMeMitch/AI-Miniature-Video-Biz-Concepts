# Chat Handoff Protocol

## Goal

Make the repository the durable project memory so any future chat can recover context quickly and avoid repeating or losing work.

## New-chat startup procedure

When starting a new ChatGPT conversation about this project, provide the repository URL and ask the assistant to read, at minimum:

1. `README.md`
2. `PROJECT_STATE.md`
3. `HANDOFF.md`

Then ask it to inspect the relevant `docs/` file(s) for the current task.

Recommended startup prompt:

> This project uses this GitHub repo as durable memory: https://github.com/SomeCallMeMitch/AI-Miniature-Video-Biz-Concepts. Read README.md, PROJECT_STATE.md, HANDOFF.md, and any docs relevant to my request before continuing. Treat PROJECT_STATE.md as the current truth, but preserve useful older ideas rather than deleting them. Search the archive if something seems missing.

## Mandatory persistence rule

Any substantial Chat, Work, Deep Research, or Codex session for this project must treat GitHub as the durable system of record.

Do not leave important findings, decisions, hypotheses, pricing ideas, experiments, workflows, research sources, or next actions only in chat history.

At the end of a meaningful task—or earlier when a major decision is reached—the assistant should write the useful durable output back to the repository when it has GitHub access.

If direct GitHub write access is unavailable, the assistant should produce the exact proposed file updates so they can be committed in a follow-up session.

## Research-session requirements

For a substantial research task, especially Deep Research or Work:

1. Read `PROJECT_STATE.md` before forming recommendations.
2. Search relevant `docs/` and `archive/chats/` before assuming an idea is new.
3. Preserve source links, dates, pricing snapshots, commercial-use/API notes, and confidence labels for time-sensitive claims.
4. Separate observed facts from hypotheses and recommendations.
5. Update or create the relevant research/domain document rather than bloating `PROJECT_STATE.md` with all raw detail.
6. Update `PROJECT_STATE.md` with only the conclusions that change current strategy, assumptions, or next actions.
7. Rewrite `HANDOFF.md` so the next session knows what was learned and what to do next.
8. Create a dated archive summary for significant sessions.
9. Never silently replace an older conclusion. Record what changed and why.

## End-of-chat procedure

At the end of a meaningful session, the assistant should update the repository rather than relying on chat memory.

### Always update

- `PROJECT_STATE.md` with important new conclusions, experiments, decisions, metrics, and next actions.
- `HANDOFF.md` with what the next chat needs to know immediately.

### Update when relevant

- stable domain docs in `docs/`
- market research and competitor findings
- economics/pricing assumptions
- production/tool findings
- validated prompts/workflows
- experiment results
- ideas backlog

### Archive the session

Create a dated summary in:

`archive/chats/YYYY-MM-DD-short-session-name.md`

The archive should preserve useful context that is too detailed for `PROJECT_STATE.md` but could matter later.

## Information hierarchy

### `PROJECT_STATE.md`

Current truth. Short enough that every new chat can read it.

### `HANDOFF.md`

Immediate continuation instructions. This is allowed to be temporary and should be rewritten often.

### `docs/`

Stable knowledge organized by subject.

### `archive/chats/`

Historical record of significant conversations. Use this to recover details or ideas that were intentionally compressed out of the current state.

## Required labels inside docs

Use explicit confidence/status labels when appropriate:

- **Validated** — tested with direct evidence.
- **Observed** — seen in research/examples but not tested by us.
- **Hypothesis** — plausible but unproven.
- **Needs revalidation** — time-sensitive research that may be stale.
- **Rejected** — intentionally not pursuing, with reason.

## Decision discipline

When a conclusion changes, do not simply erase the old reasoning.

In `PROJECT_STATE.md` or the relevant archive entry, note:

- prior belief
- new evidence
- new decision
- date

This prevents future chats from rediscovering abandoned ideas without knowing why they were abandoned.

## Search discipline for future chats

Before assuming an idea is new, search the repo for keywords and check `archive/chats/`.

Useful search concepts:

- market name
- tool/model name
- competitor name
- offer/pricing
- format name
- experiment ID
- key phrase from the idea

## Suggested future folders

Create only when needed:

- `research/` — deeper competitive/tool research
- `experiments/` — one file per formal experiment
- `prompts/` — validated prompt/version library
- `offers/` — pricing/package/copy experiments
- `assets/` — non-sensitive project assets or references
- `automation/` — workflow/code notes

## Rule of thumb

A future chat should be able to answer these questions after reading the repo:

1. What are we building/testing?
2. Why do we think it might work?
3. What have we ruled out?
4. What evidence do we have?
5. What is the next highest-value action?
6. Where can I find the detailed history if something seems missing?
