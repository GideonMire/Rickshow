SYSTEM CONTRACT — READ FIRST
Project Overview

This project is a shared rickshaw coordination app designed for daily commuters (especially students) to help them coordinate with other passengers, not drivers, for meter-based rickshaw queues on fixed routes (e.g., station → college).

The app:

Does not book vehicles

Does not assign drivers

Does not handle payments

Coordinates people with people in real time

Respects queue fairness and real-world social rules

This project is being built incrementally by a solo beginner developer using AI assistance.

Core Development Principles

These rules are non-negotiable.

Small, complete steps only

Every change must result in a working app

No half-built or placeholder features

One feature per session

Never build multiple features at once

If unsure, stop and ask

Human understanding > AI speed

Code must be readable and explainable

If the developer cannot explain it, it must be simplified

This is a coordination tool, not a platform

Avoid over-engineering

Avoid “startup-scale” abstractions

Folder Responsibility Rules
Root Directory

Only the following are allowed at the root:

SYSTEM_CONTRACT.md

README.md

/src

/docs

config files (added later intentionally)

❌ Do NOT add random files or folders at root.

/docs — Project Memory (Critical)

Purpose:

Preserve decisions

Preserve intent

Preserve context for future AI sessions

Allowed files:

vision.md — what this app is and why it exists

phases.md — build phases and scope

decisions.md — why choices were made

❌ No code inside /docs.

/src — Application Code Only

All code lives inside /src.

Inside /src, folders will be introduced gradually and intentionally.

Planned high-level structure (do NOT create unless instructed):

/app → app shell, routing, providers

/features → user-facing features (group, slot, auth)

/core → business rules (queue logic, timing rules)

/services → external services (auth, database)

/types → shared data definitions

/utils → pure helpers only

❌ Do NOT create new folders unless explicitly allowed.

Code Placement Rules (Very Important)

UI components show data and handle user interaction only

Business logic must NOT live in UI components

External calls (auth, database) must be isolated

Shared rules must live in one place only

If unsure where code belongs:

STOP and ask before writing code.

AI Usage Rules (Critical)

When AI is used:

AI must read this file first

AI must only modify files explicitly listed

AI must not create new folders or files unless instructed

AI must not refactor unrelated code

AI must explain what changed and why

If AI suggests:

Extra features

Architectural changes

New folders

→ The correct response is NO unless explicitly approved.

Git & Version Control Rules

Git must be initialized before writing code

Commit after every session

One logical change per commit

Commit messages must describe intent, not implementation

Example:

✅ Add ability to create and leave a group

❌ Update files

Reverting is always acceptable.

MVP Scope Guardrails

For MVP phases (0–3), the app MUST NOT include:

Reliability scoring

Queue position inference

Fare splitting logic

Phone calling

Stranger matching

Native mobile builds

These are future phases only.

Quality & Simplicity Rules

Prefer clarity over cleverness

Prefer fewer files over many

Prefer explicit code over abstraction

If something feels complex, it probably is

This project optimizes for:

Learnability, control, and real-world usefulness

Final Authority Rule

If there is ever a conflict between:

Speed vs understanding

Feature vs stability

AI suggestion vs human judgment

👉 Human judgment wins.

Reminder (Read This Often)

You are not trying to build everything.

You are building:

Confidence

Control

A working system step by step

Slow and steady progress is success.

End of SYSTEM CONTRACT
