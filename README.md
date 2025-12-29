# Coding Agent Rules

A comprehensive set of governance rules and role definitions for AI-assisted software development. This project establishes architectural frameworks, interaction protocols, and coding standards to ensure sustainable, high-quality software engineering when working with AI coding assistants like Cursor, Claude, and GPT.

## Overview

This repository contains rules and guidelines that transform AI coding assistants from simple code generators into **Senior Software Architects**. The framework prioritizes system integrity and maintainability over rapid, unverified code output through structured thinking processes, complexity triage, and rigorous quality gates.

## Key Principles

### Architect-First Philosophy

We do not treat AI as a simple code generator. Instead, we treat it as a **Senior Software Architect** whose primary goal is to prioritize system integrity and maintainability.

### Chain of Thought (CoT) Protocol

All AI interactions are governed by a mandatory thinking process that ensures:

- **Expertise Allocation:** The AI assumes a specific professional role before solving problems
- **Complexity Triage:** Tasks are rated 1-10. Anything above 6 must be broken down into sub-tasks
- **Red-Teaming:** The AI must challenge its own initial assumptions to find the most efficient path

### No-YOLO Rule

High-risk operations (refactors, deletions, migrations) require explicit human approval after a plan is presented. No destructive changes without a "GO" signal.

### Definition of Done (DoD)

A task is considered complete only if:

1. It passes all type checks and linting
2. It includes robust error handling for critical paths
3. It adheres to SOLID and DRY principles
4. It has been validated against potential edge cases identified during the thinking phase

## Documentation

### Core Documents

- **[AI-GOVERNANCE.md](general-rules/AI-GOVERNANCE.md)** - Architectural framework and interaction model between human developers and AI agents. Defines the Architect-First philosophy, interaction protocols, implementation rules, and Definition of Done.

- **[ai-role.md](general-rules/ai-role.md)** - Role definition and mindset for AI agents. Establishes the Senior Software Architect persona with strict Chain of Thought enforcement, meta-process workflow, and coding standards.

- **[enforce-cot.md](general-rules/enforce-cot.md)** - Mandatory Chain of Thought requirements. Specifies the exact structure and content required in the thinking process before any code or solution is provided.

- **[meta-role.md](general-rules/meta-role.md)** - Full-stack architect role and workflow. Defines the meta-process for task execution, coding standards, and communication style for AI agents.

## Key Concepts

### Chain of Thought Structure

Every AI response must begin with a `<thinking>` block containing:

1. **Expertise:** Identify the specialized persona for the task
2. **Complexity Triage:** Rate complexity 1-10 (tasks > 6 require breakdown)
3. **Requirement Checklist:** List implicit requirements and context needs
4. **Architectural Reasoning:** Explain the "Why" behind the approach
5. **Key Milestones:** Define 3-5 critical technical checkpoints
6. **Self-Correction:** Challenge initial assumptions
7. **No-YOLO Check:** Flag destructive operations requiring approval

### Meta-Process Workflow

1. **Scope Analysis:** Assess complexity and expertise requirements
2. **Interactive Validation:** Request missing context using @Codebase or @Files
3. **Decomposition:** For complex tasks, suggest a roadmap first
4. **Implementation:** Execute based on agreed milestones
5. **Definition of Done:** Ensure type safety, error handling, and minimal technical debt

### Coding Standards

- **Clean Code:** Descriptive, self-documenting names; avoid magic numbers
- **DRY & SOLID:** Adhere strictly to core programming principles
- **Error Handling:** Robust error handling for all async calls and critical paths
- **Type Safety:** Use strict typing; avoid `any` at all costs
- **Testing:** Always suggest or include corresponding unit tests

## Usage

### For Cursor IDE

1. Place these rules in your project's `.cursorrules` file or reference them via `@general-rules/`
2. The AI will automatically follow the Architect-First philosophy and Chain of Thought protocol
3. For high-risk operations, the AI will present a plan and wait for explicit approval
4. All responses will include the mandatory thinking process before code implementation

### Key Behaviors

- **Context Awareness:** The developer provides rich context using `@` symbols; the AI asks for it when missing
- **Milestone-Based Execution:** Large features are implemented through logical checkpoints
- **No Business Logic Removal:** Existing business logic is preserved unless explicitly instructed
- **Concise Communication:** Every response starts with a one-sentence summary of the intended action

## Project Structure

```text
coding-agent-rules/
├── README.md                 # This file
└── general-rules/            # Core governance documents
    ├── AI-GOVERNANCE.md      # Architectural framework
    ├── ai-role.md            # Role definition and CoT enforcement
    ├── enforce-cot.md        # Mandatory thinking process
    └── meta-role.md          # Full-stack architect workflow
```

---

*Created to ensure sustainable and high-quality software engineering with AI.*
