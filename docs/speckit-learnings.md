# GitHub Speckit - General Knowledge Document

## Overview

GitHub Speckit is a spec-driven development toolkit that "flips the script" on traditional development. Instead of treating specifications as throwaway scaffolding, Speckit makes specifications executable - they directly generate working implementations.

## Core Philosophy

**Intent-Driven Development**: Specifications define the "what" before the "how". This approach:
- Forces clarity about requirements before coding begins
- Creates multi-step refinement processes
- Leverages AI model capabilities for interpretation and implementation

## Installation

### Prerequisites
- Python 3.11+
- Git
- `uv` package manager
- A supported AI coding agent (Claude, Copilot, Cursor, etc.)

### Install Commands
```bash
# Install uv if needed
curl -LsSf https://astral.sh/uv/install.sh | sh

# Install Speckit
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# Initialize a project
specify init <project-name> --ai claude
```

## Key Concepts

### Project Structure
After initialization, Speckit creates:
```
.specify/
├── memory/
│   └── constitution.md      # Project principles and constraints
├── scripts/                  # Automation scripts
├── specs/                    # Feature specifications
│   └── 001-feature-name/
│       ├── spec.md          # What to build
│       ├── plan.md          # How to build it
│       └── tasks.md         # Ordered task breakdown
└── templates/               # Templates for artifacts
```

### Slash Commands (Workflow Phases)

1. **`/speckit.constitution`** - Establish project principles
   - Define code quality standards, testing approaches, UX expectations
   - Creates foundational rules that guide all development

2. **`/speckit.specify`** - Define requirements
   - Describe functionality in plain language
   - Focus on "what" and "why", not technology choices
   - Be explicit but technology-agnostic

3. **`/speckit.clarify`** (optional) - Resolve ambiguities
   - Structured questioning before planning
   - Address unclear requirements
   - De-risk implementation decisions

4. **`/speckit.plan`** - Create implementation plan
   - Select technology stack
   - Define architecture
   - Research rapidly-changing technologies

5. **`/speckit.tasks`** - Generate task breakdown
   - Ordered, dependency-aware tasks
   - Marks parallel work with `[P]` indicator
   - Includes file paths and TDD structure

6. **`/speckit.implement`** - Execute implementation
   - Systematically works through tasks
   - Respects dependencies
   - Handles CLI commands automatically

## Learnings from This Project

### 1. Speckit Integrates with AI Agents
Speckit doesn't work alone - it enhances existing AI coding agents by providing structured workflows. For Claude, it installs slash commands in `.claude/commands/`.

### 2. Constitution is Critical
The constitution file isn't just documentation - it's the source of truth that guides all implementation decisions. Time spent on good principles saves time during implementation.

### 3. Spec-First Forces Clarity
Writing specs before code forces you to think through requirements completely. You can't hand-wave details when they need to be in the spec.

### 4. Templates Provide Structure
Speckit's templates ensure consistency across features. You're not starting from scratch each time - you're filling in a proven structure.

### 5. Works Well for Greenfield Projects
The "0-to-1" workflow is particularly powerful for new projects where there's no existing code to constrain decisions.

---

*This document will be updated as more is learned about Speckit during the blog development process.*
