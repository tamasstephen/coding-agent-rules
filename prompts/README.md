# 🛠️ AI-Safe Prompting Toolset

This library contains high-performance prompt templates designed for Senior-level AI interaction. Use these to enforce architectural integrity, rigorous debugging, and safe refactoring.

---

## 1. 🏛️ Master Architect (New Feature Design)

_Use this for designing new modules, components, or systems from scratch._

**Prompt:**
"Analyze the following task: [DESCRIPTION]. Apply the **Master Architect Template**:

1. **Phase 1 (Thinking):** Identify the 3 core objectives, the relevant @Codebase context, and implicit technical requirements (logging, error states, etc.).
2. **Phase 2 (Multi-Perspective):** Propose 2 architectural alternatives. Analyze both for: Feasibility, Scalability, and Maintainability. Define the Trade-offs!
3. **Phase 3 (Blueprint):** Define 3-5 Key Milestones, the Data Flow, and the primary Interfaces/Types.
4. **Phase 4 (Red-Teaming):** Identify the weakest point of your own design. How would it fail? Propose a reinforcement strategy.
   **STOP:** Do not write code. Wait for my approval of the Blueprint."

---

## 2. 🕵️ Forensic Debugger (Root Cause Analysis)

_Use this for investigating complex bugs and unexpected system behavior._

**Prompt:**
"Investigate the following issue: [SYMPTOM]. Reference @ErrorLogs and @StackTrace. Apply the **Forensic Template**:

1. **Phase 1 (Audit):** Analyze implicit factors (Env vars, Global State, Async flows). Where exactly did reality deviate from expectation?
2. **Phase 2 (Devil's Advocate):** Formulate 2-3 hypotheses. For each, state: 'Why might this hypothesis be WRONG? What evidence contradicts it?'
3. **Phase 3 (Verification):** Propose a minimal verification method (e.g., a specific log or test case) to prove the root cause.
   **STOP:** Do not provide a fix. Share your counter-arguments and the verification plan for confirmation."

---

## 3. 🛠️ Refactor Master (Code Quality & Safety)

_Use this to clean up working but messy, legacy, or untyped code._

**Prompt:**
"Refactor the following code: @File. Apply the **Refactor Master Template**:

1. **Phase 1 (Audit):** Define the 'Functional Contracts' (what must not break). Identify Type-Safety gaps and missing test coverage.
2. **Phase 2 (Strategy):** Define 3-4 technical Milestones. Focus on Modularity and intent-revealing naming.
3. **Phase 3 (Type-Plan):** How will you achieve 100% type safety without type casting (no 'as' assertions)? If tests are missing, propose 3 critical unit tests.
   **STOP:** Wait for my approval of the strategy.
4. **Phase 4 (Execution):** Implement using Clean Code and SOLID principles. Ensure the result is highly modular and test-ready."

---

## 💡 Usage Guidelines

1. **Human-in-the-loop:** The **STOP** commands are critical. Never let the AI move to implementation until you have verified its logic in the thinking phase.
2. **Contextual Linking:** Always use Cursor's `@` symbols to link relevant files, folders, or documentation to the prompt.
3. **Anti-Bias:** If the AI seems too confident, explicitly ask it to "expand the Red-Teaming phase" or
