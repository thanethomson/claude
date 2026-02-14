---
name: implement-design
description: After brainstorming or co-creating a design, use to break the design down into and actionable plan and execute on the plan
---

# Implement Design

## Overview

Turn designs created through `/brainstorm` into working code.

**Announce at start:** "I'm using the implement-design skill."

## The Process

1. **ALWAYS** start with fresh context.
2. Read and understand the plan.
3. Break the plan down into actionable, reasonably-sized tasks.
4. For each task, launch a sub-agent to execute on it.
   1. Make the sub-agent report status at reasonable intervals.
   2. If the sub-agent ever gets stuck, or gets stuck in a loop, intervene
      appropriately. Learn from the sub-agent's mistakes.
   3. After a task is complete, stop and wait for review from your human
      partner.

**AFTER EACH TASK IS IMPLEMENTED:** Ask yourself, am I continuing without
review from my human partner? If so, **STOP** and ask for review.

## Principles

- Human-in-the-loop review after each task.
- Ask questions if anything is unclear.
- Each task implemented using a **SEPARATE** sub-agent.
