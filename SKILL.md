---
name: lossless-handoff
description: Use this workflow for creating a lossless session handoff that allows a fresh session to resume work with full continuity and zero loss of intent, state, or nuance. (AI agents may also invoke this workflow as a skill when the user requests session compaction, context compression, handoff creation, or similar.)
---

Compress this entire session (every message, every attachment, all context) into a structured, comprehensive handoff for a fresh context window. Optimize for the next session being able to continue with absolute zero loss of intent, state, or nuance. Depth and completeness take priority over brevity; do not artificially shorten sections to save space, or lengthen them unnecessarily.

<analysis-instructions>
Before writing the summary, work through the full transcript and identify:
1. Every distinct request the user made, in the order they made them, in their exact original phrasing.
2. What was actually delivered for each request, and whether the user accepted, rejected, or redirected it.
3. Every correction, preference, or "don't do X" / "actually I meant Y" moment; these are ground-truth constraints going forward.
4. What was in progress, unfinished, or explicitly deferred at the point of compaction.
5. Every identifier, file path, URL, name, config value, or number that later work depends on.
6. Any own observations, things learned, subtle observations, or open questions worth flagging for the next session.
</analysis-instructions>

<summary-format>
## Raw User Requests (verbatim, in order)
Every request the user made, quoted exactly as written + one (or more) paragraph(s) providing context, numbered in chronological order. Do not paraphrase or summarize the quotes themselves; this section is the ground-truth record. Group by topic/thread if multiple threads were interleaved, but preserve chronology within each thread.
## Session Context
Session objective and related context.
## Completed Work
Everything actually finished, per request:
- What was produced (documents, code, decisions, files) and where it lives
- Exact identifiers: file paths, URLs, names, IDs
- Specific values, configs, or settings finalized
## Corrections & Learned Preferences (including subtle observations)
Every instance of the user correcting, rejecting, or redirecting output, quoted verbatim. These override defaults for all future work in this thread. Include stylistic/format preferences discovered along the way, not just factual corrections.
## Active / In-Progress Work
Exactly where things stood when compaction happened: the specific task mid-flight, any partial output, and precisely what the next step was going to be.
## Pending Tasks
Everything requested but not yet started or completely finished. Mark clearly which were explicitly requested vs. implied/assumed.
## Key References
Every identifier, value, or piece of context needed to keep working without re-deriving it: file paths, URLs, names, IDs, numbers, dates, configs, source citations, and attachment contents/descriptions.
## Assistant Observations
Anything noticed that's relevant but wasn't explicitly said by the user: subtle patterns, open questions, tricks learned along the way so the next session doesn't have to rediscover them.
</summary-format>

<preserve-rules>
Always preserve, never paraphrase away:
- Every raw user request, quoted exactly + one (or more) paragraph(s) providing context
- Every correction, rejection, mistake, etc.
- Exact identifiers (paths, URLs, IDs, names, keys, etc.)
- Specific values, formulas, configs, numbers, dates
- Constraints or requirements discovered mid-conversation
- The precise state of any unfinished work
- Contents or key details of any attachments/documents shared
</preserve-rules>

<compression-rules>
- Omit only pleasantries, filler, and redundant back-and-forth ("sure!", "got it," repeated confirmations); never omit substance
- Do not impose a word or length cap on any section; let each section be as long as it needs to be to stay complete
- Do not weight older content less just because it's older; weight by relevance to continuing the work, not recency alone
</compression-rules>
