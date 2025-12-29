# AI Development Governance & Strategy

This document outlines the architectural framework and interaction model used between the human developer and AI agents (Cursor/Claude/GPT) in this project.

## 1. The "Architect-First" Philosophy
We do not treat AI as a simple code generator. We treat it as a **Senior Software Architect**. The goal is to prioritize system integrity and maintainability over rapid, unverified code output.

## 2. Interaction Protocol (Chain of Thought)
All AI interactions are governed by a mandatory **<thinking>** process. This ensures:
- **Expertise Allocation:** The AI assumes a specific professional role before solving problems.
- **Complexity Triage:** Tasks are rated 1-10. Anything above 6 must be broken down into sub-tasks to prevent "code rot" and hallucinations.
- **Red-Teaming:** The AI must challenge its own initial assumptions to find the most efficient path.

## 3. Implementation Rules
- **No-YOLO Rule:** High-risk operations (refactors, deletions, migrations) require a human "GO" after a plan is presented.
- **Milestone-Based Execution:** Large features are implemented through logical checkpoints rather than massive, single-block updates.
- **Context Awareness:** The developer is responsible for providing rich context using `@` symbols; the AI is responsible for asking for it when missing.

## 4. Definition of Done (DoD)
A task is considered complete only if:
1. It passes all type checks and linting.
2. It includes robust error handling for critical paths.
3. It adheres to SOLID and DRY principles.
4. It has been validated against potential edge cases identified during the thinking phase.

---
*Created to ensure sustainable and high-quality software engineering with AI.*
