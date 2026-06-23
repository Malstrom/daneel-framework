# daneel-framework

> The AI remembers everything you have done. You just work.

Daneel is an AI-native framework that acts as **persistent professional memory and operational assistant** for any type of knowledge work. The AI does not track tasks — it accompanies you in doing them, remembers everything, and uses that memory when needed.

## Problems this solves

- “I worked 3 years for a client and cannot remember what I did.”
- “I need to reply to a client but do not remember the context.”
- “I receive a task and do not know if I have done something similar before.”
- “I want to log what I did without switching to another tool.”

## Who it’s for

Consultants, developers, freelancers — anyone doing recurring work for multiple clients.

## Core concepts

| Concept | Description |
|---|---|
| **client** | An external entity you do work for |
| **contact** | A person at a client you communicate with (global, not per-client) |
| **playbook** | Step-by-step instructions for a recurring work type |
| **recall** | AI operation to retrieve past work via closed GitHub issues |
| **reindex** | AI maintenance operation to rebuild playbook index files |

## Structure

```
daneel-framework/
├── .agent.yml          # AI manifest — entry point for the AI
├── .daneel.yml         # User profile, roles, domains, language, timezone
├── clients/            # One subfolder per client
│   └── {slug}/
│       ├── context.yml     # Static client info
│       └── playbooks/      # Client-specific playbooks
├── contacts/           # External contact profiles
└── playbooks/          # Root playbooks (promoted from client playbooks)
```

## Scenarios

- `session_start` — reads context before every session
- `work_session` — accompanies you through a task
- `close_task` — logs and closes a completed task
- `ingest_task` — registers a new incoming task as a GitHub issue
- `create_playbook` — captures a recurring workflow as a playbook
- `draft_reply` — drafts a reply to a client
- `recall` — retrieves past work and context
- `reindex` — rebuilds playbook index files

## Derives from

[zeroth](https://github.com/Malstrom/zeroth) — canonical framework spec and rules.
