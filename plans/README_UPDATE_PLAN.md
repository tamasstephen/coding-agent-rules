# Plan: Update README.md for New Prompts Library

## Overview

This plan outlines the changes needed to update the root `README.md` to document the new **AI-Safe Prompting Toolset** (`prompts/` folder) while maintaining the existing governance documentation.

---

## Current State Analysis

### Existing README Structure

- **Overview** section (AI-assisted software development governance)
- **Key Principles** (Architect-First, CoT Protocol, No-YOLO, DoD)
- **Documentation** section (core documents in `general-rules/`)
- **Key Concepts** (CoT structure, Meta-Process, Coding Standards)
- **Usage** section (for Cursor IDE)
- **Project Structure** tree

### New Addition: Prompts Library

The `prompts/` folder contains 4 files:

- `README.md` - Summary of 3 prompt templates
- `architect.md` - Master Architect prompt template (currently empty)
- `debugger.md` - Forensic Debugger prompt template
- `refactor.md` - Refactor Master prompt template

---

## Proposed README Updates

### 1. New Section: "AI-Safe Prompting Toolset"

Add after the **Documentation** section, a new section documenting the prompts library:

```markdown
## AI-Safe Prompting Toolset

This project includes a library of high-performance prompt templates designed for Senior-level AI interaction. These prompts enforce architectural integrity, rigorous debugging, and safe refactoring through structured multi-phase workflows.

### Core Prompts

| Prompt                | Purpose                                | File                                           |
| --------------------- | -------------------------------------- | ---------------------------------------------- |
| **Master Architect**  | New feature/module design from scratch | [`prompts/architect.md`](prompts/architect.md) |
| **Forensic Debugger** | Root cause analysis for complex bugs   | [`prompts/debugger.md`](prompts/debugger.md)   |
| **Refactor Master**   | Code quality & safety refactoring      | [`prompts/refactor.md`](prompts/refactor.md)   |

### Usage

Each prompt follows a phased approach with mandatory "STOP" checkpoints for human approval:

1. **Phase 1 (Thinking):** Analysis and context gathering
2. **Phase 2 (Multi-Perspective):** Alternative approaches and trade-offs
3. **Phase 3 (Blueprint):** Detailed implementation plan
4. **Phase 4 (Red-Teaming/Verification):** Self-critique and validation

Example usage in Cursor:
```

"Analyze the following task: [DESCRIPTION]. Apply the **Master Architect Template**..."

```

See [`prompts/README.md`](prompts/README.md) for complete prompt templates and usage guidelines.
```

### 2. Updated Project Structure

Change the Project Structure section from:

```text
coding-agent-rules/
├── README.md                 # This file
└── general-rules/            # Core governance documents
    ├── AI-GOVERNANCE.md      # Architectural framework
    ├── ai-role.md            # Role definition and CoT enforcement
    ├── enforce-cot.md        # Mandatory thinking process
    └── meta-role.md          # Full-stack architect workflow
```

To:

```text
coding-agent-rules/
├── README.md                 # This file
├── general-rules/            # Core governance documents
│   ├── AI-GOVERNANCE.md      # Architectural framework
│   ├── ai-role.md            # Role definition and CoT enforcement
│   ├── enforce-cot.md        # Mandatory thinking process
│   └── meta-role.md          # Full-stack architect workflow
└── prompts/                  # AI-Safe Prompting Toolset
    ├── README.md             # Prompt library overview
    ├── architect.md          # Master Architect template
    ├── debugger.md           # Forensic Debugger template
    └── refactor.md           # Refactor Master template
```

### 3. Enhanced Usage Section

Update the **Usage** section to include prompt library usage:

```markdown
## Usage

### For Core Governance Rules

Place these rules in your project's `.cursorrules` file or reference them via `@general-rules/`. The AI will automatically follow the Architect-First philosophy and Chain of Thought protocol.

### For Prompt Templates

Reference specific prompts via `@prompts/` for targeted workflows:

- **New Feature Design:** Use `@prompts/architect.md` for designing modules from scratch
- **Bug Investigation:** Use `@prompts/debugger.md` for root cause analysis
- **Code Refactoring:** Use `@prompts/refactor.md` for quality improvements

### Key Behaviors

- **Context Awareness:** The developer provides rich context using `@` symbols; the AI asks for it when missing
- **Milestone-Based Execution:** Large features are implemented through logical checkpoints
- **Human-in-the-Loop:** Prompts include STOP commands requiring approval before implementation
- **No Business Logic Removal:** Existing business logic is preserved unless explicitly instructed
- **Concise Communication:** Every response starts with a one-sentence summary of the intended action
```

### 4. Updated Documentation Section

Add prompts to the Documentation section:

```markdown
### Core Documents

- **[AI-GOVERNANCE.md](general-rules/AI-GOVERNANCE.md)** - Architectural framework and interaction model between human developers and AI agents. Defines the Architect-First philosophy, interaction protocols, implementation rules, and Definition of Done.

- **[ai-role.md](general-rules/ai-role.md)** - Role definition and mindset for AI agents. Establishes the Senior Software Architect persona with strict Chain of Thought enforcement, meta-process workflow, and coding standards.

- **[enforce-cot.md](general-rules/enforce-cot.md)** - Mandatory Chain of Thought requirements. Specifies the exact structure and content required in the thinking process before any code or solution is provided.

- **[meta-role.md](general-rules/meta-role.md)** - Full-stack architect role and workflow. Defines the meta-process for task execution, coding standards, and communication style for AI agents.

### Prompt Templates

- **[prompts/README.md](prompts/README.md)** - Overview of the AI-Safe Prompting Toolset with usage guidelines and summary of all available prompts.

- **[prompts/architect.md](prompts/architect.md)** - Master Architect prompt for designing new modules, components, or systems from scratch.

- **[prompts/debugger.md](prompts/debugger.md)** - Forensic Debugger prompt for investigating complex bugs and identifying root causes.

- **[prompts/refactor.md](prompts/refactor.md)** - Refactor Master prompt for cleaning up legacy or messy code while maintaining functional behavior.
```

---

## Summary of Changes

| Section                       | Change Type  | Description                                 |
| ----------------------------- | ------------ | ------------------------------------------- |
| **Documentation**             | Modification | Add Prompt Templates subsection             |
| **Key Concepts**              | No change    | Keep existing content                       |
| **AI-Safe Prompting Toolset** | Addition     | New section documenting the prompts library |
| **Usage**                     | Enhancement  | Add prompt template usage instructions      |
| **Project Structure**         | Update       | Include `prompts/` folder in tree           |

---

## Files to Modify

- `README.md` - Update to document the new prompts library

## Files to Create

- None (plan only)

---
