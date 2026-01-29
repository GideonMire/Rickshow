You are working inside an existing GitHub project.

READ AND FOLLOW THESE FILES STRICTLY.

--- START SYSTEM_CONTRACT.md ---
SYSTEM CONTRACT — READ FIRST Project Overview

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

Folder Responsibility Rules Root Directory

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
--- END SYSTEM_CONTRACT.md ---

--- START docs/vision.md ---
Vision — Shared Rickshaw Coordination App
What This App Is

This is a real-time coordination app for daily commuters, especially college students, who use meter-based shared rickshaw queues on fixed routes (e.g., station → college).

The app helps passengers coordinate with other passengers so that:

The required number of people (usually 3) can board together

Money is saved compared to fixed-rate or demand-based options

Queue fairness and social norms are respected

This app does not book vehicles.
It only helps people find and coordinate with other people.

The Problem This App Solves

Shared rickshaws are cheap and fair because they run by meter, but they require an exact number of passengers.

In real life:

Friends arrive at different times

Communication is messy (calls, texts, waiting)

People give up and take more expensive options

Queue etiquette makes coordination awkward

The core problem is coordination, not availability or pricing.

Who This App Is For

Daily commuters

College students

People who regularly travel the same short route

Users who already plan their commute (e.g., while on the train)

This app is not designed for:

Tourists

One-time riders

City-wide on-demand transport

Long-distance travel

What This App Does

At a high level, the app allows users to:

Coordinate groups of 2–3 people before reaching the rickshaw stand

Share estimated arrival times

Indicate current status (on the way, late, leaving)

Offer open seats if already standing in line (“slot available”)

Join others who are going to the same destination

Make decisions that respect queue fairness

The app supports both:

Friends coordinating together

Optional coordination with nearby strangers (later phase)

What This App Explicitly Does NOT Do

To avoid confusion and over-engineering, this app does not:

Book rickshaws

Assign or contact drivers

Handle payments or fares

Guarantee seats

Enforce behavior

Replace ride-hailing apps

Operate city-wide in early versions

All decisions remain human and situational.

Design Philosophy

This app is built with the following principles:

Assist, don’t control — the app suggests, users decide

Small scope first — one route, one use case

Behavior-aware — real people are late, impatient, or flexible

Fairness-first — queue etiquette matters

Clarity over cleverness — simple flows beat complex logic

MVP Definition

The MVP should answer one question:

Can people reliably coordinate shared rickshaw rides using this tool?

If the answer is yes, the app is successful — even without advanced features.

Long-Term Possibilities (Not Commitments)

Potential future ideas (only if the MVP works):

Reliability indicators

Better wait/leave handling

Suggested fairness rules

Improved matching logic

These are not required for initial success.

Success Criteria

This project is successful if:

A small group of real users can use it daily

Coordination becomes easier than manual texting

The app remains simple and understandable

The developer maintains control over the system

Final Reminder

This project is intentionally:

Local

Modest

Human-centered

It is a tool, not a platform.
--- END docs/vision.md ---

--- START docs/phases.md ---
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
--- END docs/phases.md ---

Rules:
- Follow SYSTEM_CONTRACT.md at all times
- Do NOT create new features
- Do NOT create new folders unless explicitly allowed
- If unsure, ask before proceeding

TASK:
We are starting Phase 1.1 — App Skeleton.

GOAL:
Create a minimal React + Vite + TypeScript application that boots locally and shows a blank screen.

HARD CONSTRAINTS (NON-NEGOTIABLE):
- You MUST use the official Vite + React + TypeScript template
- You MUST use npm as the package manager
- You MUST use `npm create vite@latest`
- You MUST NOT use import maps, esm.sh, CDN-based React, or custom setups
- You MUST NOT assume any pre-existing file structure
- You MUST NOT use index.tsx assumptions
- You MUST NOT add or suggest any files other than those generated by Vite itself
- You MUST NOT add mock files, services, components, metadata, or unused code
- You MUST NOT skip steps or combine commands
- You MUST NOT explain future phases or improvements

EXPECTED OUTPUT FORMAT:
1. The exact command to create the Vite project
2. The exact selections to choose in the Vite CLI
3. The exact commands to run the project
4. A brief explanation of ONLY the default files created by Vite

If you cannot meet all constraints, STOP and say so.
