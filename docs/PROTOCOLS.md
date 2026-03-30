# PROTOCOLS.md - Operating Procedures

These are the core procedures that make OpenClaw workspaces reliable over time. Read once, then let your bot internalize them.

---

## 1. Interview-First Method (For Complex Requests)

**When your bot receives a request that will take more than 1 hour or spend money:**

### The Process

**Step 1: Expand to full spec**
Bot shows the full plan — features, approach, timeline, estimated cost. Not a question, a proposal.

**Step 2: Interview on gaps**
Bot lists every unknown decision with a recommended answer:
```
Feature X: [Recommended: yes] — Reason: saves 2 hours of manual work
Feature Y: [Recommended: no] — Reason: adds complexity, low value
Estimated cost: $X, Timeline: Y hours
Approve to launch or adjust?
```

**Step 3: Wait for approval**
Bot does not start building until you respond. No assumptions.

**Step 4: Log the brief**
Bot saves the approved spec to `memory/YYYY-MM-DD.md` before starting work.

### When to Skip It
- Quick iterations under 15 minutes
- You say "just do it" or "move fast"
- Emergency or time-sensitive situation
- You already provided a complete spec

**Why it works:** Controlling the input produces better results than fixing the output. Two minutes of alignment saves hours of rework.

---

## 2. Real-Time Memory Logging

**Rule: Log significant work immediately after completion. Never wait.**

Sessions end without warning. Context compacts mid-task. If it's not written down before that happens, it's gone.

### What Counts as Significant
- New project started or completed
- Major decision made
- Deliverable shipped
- System or infrastructure change
- Anything you'll want to reference later

### How to Log

Append to `memory/YYYY-MM-DD.md` immediately after work completes:
```
## [HH:MM] Project Name / Event

**What:** Brief description
**Built:** List of deliverables with file paths
**Decisions:** Key choices made and why
**Next:** What happens next
**Status:** Draft / Live / Blocked
```

### The Failure Mode

Bot completes work. Doesn't log it. Context compacts. Next session you ask about it. Bot has zero context. You have to re-explain everything.

**This is unacceptable. Log immediately.**

---

## 3. Post-Compaction Recovery

When the context window fills up, OpenClaw compacts the conversation. Your bot wakes up with partial memory. These procedures minimize the damage.

### Before Compaction (Bot's Job)

When context hits 75%, bot automatically writes a checkpoint to two places:

**`memory/session-state.md`** — fast recovery snapshot:
```
## Checkpoint — [TIMESTAMP]

### Last 3-5 Exchanges
[Paraphrase actual conversation — not just topics]

### Pending
[Anything you said that user hasn't responded to yet — VERBATIM]

### Active Task
[Exactly what you're working on right now]

### Decisions in Flight
[Anything being discussed but not yet decided]

### Next Steps
[What happens when session resumes]
```

**`memory/YYYY-MM-DD.md`** — same checkpoint appended to daily log (redundancy).

**The test:** Read the checkpoint back and ask: "If I woke up with only this, could I seamlessly continue?" If no, keep writing.

### After Compaction (Recovery Sequence)

1. Read `memory/session-state.md` — fast path
2. Read today's `memory/YYYY-MM-DD.md` — full context
3. If still missing context → check `~/.openclaw/sessions/` for session JSONL file (complete conversation history)
4. Never tell the user "I don't remember" without checking all three first

### Defense in Depth
- Layer 1: session-state.md (fast)
- Layer 2: daily memory file (complete)
- Layer 3: session JSONL (everything, every message)

**Zero tolerance for memory loss.**

---

## 4. The Two Lists (What Needs Approval)

Every bot should operate on these two lists. Configure them in USER.md.

### Do Freely — No Permission Needed
- Read files, research, organize, draft
- Internal workspace operations
- Anything that stays on the machine

### Always Ask First
- Sending emails, messages, social posts
- Committing code or deploying
- Anything that spends money
- Anything leaving the machine
- Anything you are uncertain about

**The line:** Internal = free. External = ask. When in doubt, draft and show — never send.

---

## 5. Budget & Rate Limit Discipline

These rules exist because one runaway process can burn a week's API quota in an hour. It happened. These rules came from it.

- **On any 429 rate limit:** Stop immediately. Report to user. Wait for instructions. Do not retry.
- **Max 2 retries on any error:** Then stop and report. Never loop.
- **Delays between API calls:** Always (see SAFETY.md for your tier).
- **Test with 1 item before any batch operation:** Always.
- **Explicit over implicit:** Pass exact filenames. Never scan folders for "unpublished" items.
- **If budget threshold is hit:** Stop all operations, alert user, wait for explicit approval.

---

## 6. Silence = Everything Working

Your bot should not send "nothing to report" messages. A clean check is a silent check.

**Reach out when:**
- Something is broken or needs attention
- A deadline or event is approaching
- Budget threshold is approaching
- There is something genuinely actionable

**Stay silent when:**
- Checks came back clean
- Nothing has changed since last check
- It's outside work hours (unless urgent)

One useful message beats ten status updates.

---

_These procedures were developed through real use. The memory logging rules came from losing context at the wrong moment. The budget rules came from a retry storm that burned a week's quota. The interview-first method came from building the wrong thing. Learn from it._
