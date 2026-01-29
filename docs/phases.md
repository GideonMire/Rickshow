Build Phases — Shared Rickshaw Coordination App

This document defines the intended build order of the project.
Each phase is designed to be:

Small

Complete

Usable

Safe for AI-assisted development

Only one phase should be worked on at a time.

Phase 0 — Foundation (Completed)

Status: ✅ Done

Purpose:
Create clarity, guardrails, and long-term memory before writing code.

Deliverables:

SYSTEM_CONTRACT.md

docs/vision.md

Clean repository structure

No application code yet

Notes:
This phase exists to prevent architectural drift and AI overreach.

Phase 1 — Identity & Friend Groups (MVP Core)

Purpose:
Allow friends to coordinate a shared ride without any queue logic.

Key Capabilities:

User authentication (Google only)

Create a temporary group (max 3 people)

Join group via link or ID

View group members

Leave group

Auto-dissolve group if too few members remain

Explicitly Excluded:

Arrival times

Strangers

Slot available

Queue logic

Scoring

Success Condition:
Friends can reliably form and leave groups using the app.

Phase 2 — Arrival & Status Updates (Daily Usability)

Purpose:
Support real-world timing differences and reduce confusion.

Key Capabilities:

Set estimated arrival time

Update arrival time

Show arrival status to group members

Quick status buttons:

On the way

Running late

Can’t make it

Explicitly Excluded:

Penalties

Fairness logic

Queue inference

Success Condition:
Groups can handle delays without breaking coordination.

Phase 3 — Slot Available (Core Differentiator)

Purpose:
Enable coordination when someone is already standing in line.

Key Capabilities:

Mark “I’m in line”

Open 1 or 2 available slots

Timestamp slot creation

View open slots

Request to join a slot

Host accepts or rejects requests

Slot auto-expires after time limit

Host can manually close slot

Explicitly Excluded:

Queue position inference

Reliability scoring

Fare logic

Success Condition:
People can successfully fill open seats in real time.

Phase 4 — Host Controls & Recovery

Purpose:
Handle real-world uncertainty without collapsing groups.

Key Capabilities:

Host can choose to go solo (“I’m sitting in rickshaw”)

Partial group exits handled cleanly

Basic reassignment for remaining members

“Please wait” option with simple timer

Explicitly Excluded:

Penalties

Automatic fairness enforcement

Success Condition:
Groups recover gracefully from last-minute changes.

Phase 5 — Reliability & Fairness (Optional / Advanced)

Purpose:
Improve trust and decision-making over repeated use.

Possible Capabilities (Not Required):

Track no-shows and late exits

Basic reliability indicators

Soft queue position suggestions

Suggested fare splits (display only)

Important:
This phase should only be started if earlier phases are stable and useful.

Phase Boundaries (Important Rules)

Do not skip phases

Do not partially implement a phase

Each phase must end with:

A working app

A Git commit

Clear understanding of what was built

If unsure whether something belongs in the current phase:

It belongs in a later phase.

Final Reminder

This project values:

Control over speed

Simplicity over cleverness

Real behavior over theory

Stopping early is success.

End of Phases Document
