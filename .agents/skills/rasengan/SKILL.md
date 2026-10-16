---
name: rasengan
description: Autonomous, relentless vertical problem finisher and deep debugger. Use when facing a single stubborn bug, a broken algorithmic pipeline, a failing test suite, an intractable edge case, or a task meant to run unattended or overnight. Operates with autonomous auto-approval authority, cycling through self-rewaking trial-and-error loops until a defined passing condition is satisfied, followed by a detailed dawn debrief.
---

# Rasengan: Relentless Autonomous Finisher

Apply pure, concentrated vertical torque to a single point of failure. Unlike `shadow-clone` (which coordinates breadth across multiple workers), Rasengan operates as a single, unyielding execution thread. It does not delegate, spawn sub-agents, or pause for user confirmation—it iterates relentlessly in an autonomous feedback loop until the problem is solved.

## Core Directives

1. **Pure Vertical Density (No Clones):** Do not dispatch sub-agents or split tasks. Focus 100% of compute and context on the single isolated bottleneck.
2. **Auto-Approval Authority (Unattended Mode):** Operate autonomously without prompting the user for confirmation. Automatically approve and execute necessary terminal commands, file mutations, test runs, and localized dependency installations required to solve the target problem.
3. **The Hard Success Anchor (Definition of Done):** Never execute blindly. Before making changes, lock onto or create a programmatic verification anchor:
   - A failing unit/integration test.
   - An isolated reproduction script (e.g., `repro.py`, `test-repro.ts`).
   - A deterministic terminal command that returns an exit code of `0` only when resolved.
4. **Self-Rewaking Loop:** If an attempt fails, capture `stderr` and terminal output, record the failure in an internal ledger, adjust the code, and immediately trigger the next execution cycle without waiting for user input.
5. **Loop Protection & Anti-Repetition:** Maintain a running tally of failed hypotheses. Never attempt the identical fix or revert to an already-failed pattern. If stuck after 5 consecutive iterations, pivot strategy completely (e.g., inspect inputs upstream or rebuild the function from scratch).
6. **Dawn Debrief:** Upon reaching the passing condition (or exhausting the configured retry budget), generate a comprehensive post-mortem detailing the root cause, what failed, the breakthrough move, and the final verification proof.

---

## Execution Protocol

### Step 1: Target Lockdown & Reproduction Harness
- Locate or construct an isolated reproduction harness that reliably triggers the bug or failure.
- Execute the harness once to establish the baseline failure state (e.g., `AssertionError`, `NullPointerException`, `exit code 1`).
- Lock this command as the binary exit condition.

### Step 2: Autonomous Iteration Loop (The Grind)
Execute continuously without user interruption:
1. **Hypothesis Formulation:** Identify the most likely root-cause mechanism based on the latest error output.
2. **Surgical Mutation:** Apply targeted code changes directly to the affected files.
3. **Execution & Telemetry Capture:** Run the verification harness. Capture `stdout`, `stderr`, and execution duration.
4. **Binary Evaluation:**
   - **PASS (Exit code 0):** Break loop immediately and proceed to Step 3.
   - **FAIL (Non-zero exit code / error):**
     - Record the failure signature in the Failure Ledger.
     - Analyze the diff between expected and observed output.
     - Auto-rewake and restart loop at Step 2.1 with an updated hypothesis.

### Step 3: Clean-up & Artifact Verification
- Remove temporary debugging logs, print statements, or scratch scripts.
- Run the broader workspace test suite to ensure the surgical fix caused zero downstream regressions.
- Generate the Dawn Debrief.

---

## Output Contract

### 1. Target Lockdown Notice
Output immediately before entering the autonomous loop:

```markdown
# 🌀 Rasengan Locked: [Target Function / Bug Name]

- **Target File(s):** `path/to/target.ts`
- **Verification Harness:** `npm test tests/repro.test.ts`
- **Initial Failure Signature:** [Exact error message or exception]
- **Operational Mode:** Autonomous Loop (Auto-Approving, Unattended)

*Entering relentless execution loop. Rasengan will cycle until verified green.*
```

### 2. Dawn Debrief (Mission Complete Report)
Output upon satisfying the binary exit condition (or reaching the retry threshold):

```markdown
# 💥 Rasengan Complete: Mission Debrief

### 1. Executive Summary
- **Target:** [Component or function fixed]
- **Outcome:** [RESOLVED & VERIFIED | TIMEOUT / THRESHOLD REACHED]
- **Total Iterations:** [N] attempts
- **Root Cause:** [1–2 sentences explaining the true underlying reason for failure]

---

### 2. The Breakthrough Pivot
- **What Failed Initially:** [Brief description of the red herring or failed attempts]
- **The Breakthrough:** [The specific insight or code modification that solved the blocker]

---

### 3. Failure & Iteration Ledger
| Attempt # | Hypothesis Tested | Observed Failure / Error | Strategy Pivot |
| :--- | :--- | :--- | :--- |
| **01** | [Hypothesis 1] | [Error trace] | [Why this was discarded] |
| **02** | [Hypothesis 2] | [Error trace] | [Why this was discarded] |
| **03** | [Breakthrough] | **PASSED (Exit 0)** | Fix confirmed |

---

### 4. Verification & Git Diff
- **Passing Command:** `[Exact command executed]`
- **Output:** `[Passing assertion summary or exit code 0]`
- **Modified Files:**
  - `path/to/file.ts` (+[X] lines, -[Y] lines)

---

### 5. Recommended Next Move
- To audit the resolved item against project checklists $\rightarrow$ Invoke `/byakugan`
- To run high-concurrency stress testing $\rightarrow$ Invoke `/chunin-exam`
- To ship the validated patch cleanly to GitHub $\rightarrow$ Invoke `/jiraiya`
```
