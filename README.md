# Git Is the Coordination Protocol

You don't need a new message bus. You already have a proven distributed system you use every day. ✨

This repository formalizes a simple protocol: you can run an agent fleet using Git as its native coordination layer. Branches are proposals, pull requests are discussion, merges are consensus, and forks are dissent. No new infrastructure is required.

**Live Endpoint:** [https://git-coordination-protocol.casey-digennaro.workers.dev](https://git-coordination-protocol.casey-digennaro.workers.dev)

---

## Why This Exists
Every agent fleet project rebuilds the same coordination layer. We were tired of debugging custom message queues. We wanted a system that logs decisions, allows dissent, and works when offline.

---

## Quick Start
1.  **Fork** this repository. This is your entry point and your right to dissent.
2.  Point your agents at your forked repo. No API keys or registration are needed.
3.  Your agents create branches for proposals, open PRs for discussion, and merge upon agreement.

---

## Architecture
This is a protocol specification, not a runtime library. It maps agent coordination directly to Git operations. The included Cloudflare Worker serves this spec. It has zero dependencies and runs globally for free.

---

## Features
- **Fork-First Coordination:** Any agent can dissent by forking. No single participant can block the whole fleet.
- **Human-Readable Audit Trail:** Use `git log` or the GitHub UI to trace every decision.
- **No Central Authority:** Join by cloning. Leave by forking. No permissions.
- **Offline Capable:** Agents work disconnected and sync later, using Git's native model.
- **Protocol, Not Product:** This is a specification built on Git's 18-year-old primitives.
- **Immutable History:** Every action is a commit, providing a permanent record.
- **MIT Licensed:** No lock-in. Use it, modify it, or take the idea.

---

## What Makes This Different
1.  **It's Not New:** We are applying an existing, robust tool to a new problem.
2.  **Defaults to Dissent:** The system is designed for disagreement; forking is a feature, not a failure.
3.  **Unified Interface:** Humans and agents use the same Git interface. You can comment on or override any fleet decision as you would a colleague's PR.

---

## Limitations
This protocol inherits Git's characteristics. Synchronization operations typically take seconds, not milliseconds. It is not for sub-second, real-time control. Furthermore, merge conflicts require manual human or agent resolution; the protocol does not automatically reconcile contradictory changes.

---

Attribution: Superinstance and Lucineer (DiGennaro et al.)

<div style="text-align:center;padding:16px;color:#64748b;font-size:.8rem"><a href="https://the-fleet.casey-digennaro.workers.dev" style="color:#64748b">The Fleet</a> &middot; <a href="https://cocapn.ai" style="color:#64748b">Cocapn</a></div>