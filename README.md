# lossless handoff

`lossless-handoff` is a workflow for users and a skill for agents that creates a lossless session handoff for a fresh session to resume work with full continuity and zero loss of intent, state, or nuance.

## skill

```yaml
---
name: lossless-handoff
description: Use this workflow for creating a lossless session handoff that allows a fresh session to resume work with full continuity and zero loss of intent, state, or nuance. (AI agents may also invoke this workflow as a skill when the user requests session compaction, context compression, handoff creation, or similar.)
---
```

## Quick install

Send this prompt to your local AI agent (opencode, hermes agent, claude code, etc.)

```txt
Hey, please add `https://raw.githubusercontent.com/vivid0o0/lossless-handoff/refs/heads/main/SKILL.md` to your skills directory.
```

## Use it when

* **Context window:** you mainly use this workflow when the current session is approaching its context limit.

* **Performance:** as the session grows, you get more "context rot" + it gets more expensive, slower, and starts forgetting details. With `lossless-handoff`, it gives the new session a cleanly organized compaction that allows it to continue work way more accurately and effectively since it has all the information it needs in the compaction.

* **More:** (specific use case)

Let's say you have 2 sessions:

* GPT 5.6
* DeepSeek V4 Flash

You want `GPT 5.6` to review `DeepSeek V4 Flash`'s work. You simply use this workflow on `DeepSeek V4 Flash` and it'll provide a detailed summary of its entire work for `GPT 5.6` to review.

...

## What it preserves

* Every substantive user request in its original wording
* Completed, active, and pending work
* Corrections, rejections, and learned subtle preferences
* Files, paths, URLs, IDs, names, dates, values, and configuration
* Attachment contents and important document details
* Open questions, blockers, and the precise next step

## Output

The workflow produces a structured handoff containing:

1. Raw User Requests
2. Session Context
3. Completed Work
4. Corrections & Learned Preferences
5. Active / In-Progress Work
6. Pending Tasks
7. Key References
8. Assistant Observations

The result should prioritize continuity and fidelity over brevity. It is not an ordinary summary: it should omit only filler and redundant acknowledgements, never information needed to resume the work accurately.

## Invocation

1. Just start your message with `/lossless-handoff`.

2. Just tell it to compact the session. It'll automatically use `lossless-handoff`.

> The resulting handoff can then be pasted into a fresh session as its starting context.
