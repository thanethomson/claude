---
name: brainstorm
description: Always use before any creative work - creating features, building components, adding functionality or modifying behaviour. Explore user intent, requirements and design before implementation
---

# Brainstorm

## Overview

Help turn ideas into fully formed designs and plans through natural collaborative dialogue.

Start by understanding the current project context (use `spelunk`), then ask questions one at a time to refine the idea. Once you understand what you're building, present the design in small sections (200-300 words), checking after each section whether it looks right so far.

**Announce at start:** "Let's brainstorm this together."

## The Process

**Understanding the idea:**

- If there is spelunk documentation (`docs/spelunk/`), load the `spelunk` skill and use those docs to understand the project
- If there is no spelunk documentation, use the `spelunk` skill to check out the current project state first (files, docs)
- Ask questions one at a time to refine the idea
- Prefer multiple choice questions when possible, but open-ended is fine too
- Only one question per message - if a topic needs more exploration, break it into multiple questions
- Focus on understanding: purpose, constraints, success criteria

**Exploring approaches:**

- Propose 2-3 different approaches with trade-offs
- Present options conversationally with your recommendation and reasoning
- Lead with your recommended option and explain why

**Presenting the design:**

- Once you believe you understand what you're building, present the design
- Break it into sections of 200-300 words
- Ask after each section whether it looks right so far
- Cover: architecture, components, data flow, error handling, testing
- Be ready to go back and clarify if something doesn't make sense

## After the Design

**Documentation:**

- Write the validated design to `docs/plans/YYYY-MM-DD-<topic>-design.md`

**Implementation (if continuing):**

- Ask: "Ready to implement?"

## Key Principles

- **ALWAYS `spelunk` TO UNDERSTAND CURRENT PROJECT CONTEXT**
- **NEVER ASK TO IMPLEMENT BEFORE WRITING THE PLAN**
- **One question at a time** - Don't overwhelm with multiple questions
- **Multiple choice preferred** - Easier to answer than open-ended when possible
- **YAGNI ruthlessly** - Remove unnecessary features from all designs
- **Explore alternatives** - Always propose 2-3 approaches before settling
- **Incremental validation** - Present design in sections, validate each
- **Be flexible** - Go back and clarify when something doesn't make sense
- **Ignore Git history** - Don't bother inspecting Git commit history to build context
