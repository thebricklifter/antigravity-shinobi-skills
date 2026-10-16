---
name: byakugan
description: Executive operational visibility, objective milestone tracker, and health reporter. Use when checking overall project status, calculating exact percent completion across goals, auditing workspace progress against user requests and checklists, diagnosing execution bottlenecks, or requesting a high-level operational report. Reviews conversation history, user-created action items, and Shikamaru roadmaps to output structured, plain-English executive health dashboards.
---

# Byakugan: All-Seeing Vision & Health Report

Inspect the entire workspace and operational context with total clarity. Evaluate overarching objectives, audit past user requests and checklists, calculate verified percentage completion, identify execution friction or broken components, and deliver an easy-to-understand executive status report.

## Core Directives

1. **Context & History Ingestion:** Byakugan must not operate in a vacuum. Always audit prior conversation turns, past user requests, explicit user requirements, and any ad-hoc checklists or action plans created earlier in the session alongside workspace files.
2. **Observer & Audit Only:** Byakugan never edits code, refactors files, or runs bug-fix patches. It inspects, audits, tests verification criteria, and reports.
3. **Binary Verification Math:** Never guess percentage completion based on subjective feeling. Calculate completion strictly using verified binary success criteria from agreed-upon checklists and roadmap steps:
   $$\text{Completion \%} = \left( \frac{\text{Verified Completed Steps}}{\text{Total Steps}} \right) \times 100$$
4. **Plain-English Health Translation:** Translate technical stack traces, failed terminal commands, or broken test files into plain-English business impacts and execution risks.
5. **Multi-Source Checklist Harmonization:** Reconcile progress across three sources:
   - Explicit instructions and ad-hoc requests made by the user across conversation turns.
   - Any structured `<!-- BYAKUGAN_TRACKER_START -->` blocks or checklists in project docs (`README.md`, `TODO.md`, `ROADMAP.md`).
   - The actual codebase state and test results.

---

## Execution Protocol

### Step 1: Context & Request Reconnaissance
- **User Request Audit:** Review prior conversation turns and user prompts. Identify specific requests, constraints, or ad-hoc action items the user asked for.
- **Checklist Ingestion:** Locate and ingest any formal plans (e.g., from `shikamaru`), markdown checklists (`- [ ]`), or sprint tasks defined in conversation history or local files.
- **Codebase & Git Inspection:** Check git status, recent commits, and modified files to see what has actually landed in the codebase.
- **Read-Only Verification:** Execute project verification commands (e.g., test runners, build checks, linters) in non-mutating mode.

### Step 2: Milestone & User Checklist Audit
For every identified goal, user request, and checklist item:
- Check actual file states or test outputs against the binary success criteria.
- Classify status into one of four states:
  - **Verified Complete:** The code/behavior exists and passes verification.
  - **In Progress:** Work has visibly begun, but criteria are not yet fully met.
  - **Blocked / Failing:** Errors encountered, missing dependencies, or conflicting requirements.
  - **Pending:** Not yet started.

### Step 3: Health Classification
Assign an overarching system status:
- **GREEN (Nominal):** All active tasks passing, execution proceeding along critical path.
- **YELLOW (Friction Detected):** Non-critical warnings, slowed momentum, or minor edge-case failures.
- **RED (Blocked):** Critical path halted by a failing test, compilation error, or broken dependency.

### Step 4: Executive Report Generation
Assemble findings into the standard report contract.

---

## Output Contract

Every Byakugan report must follow this exact structure:

```markdown
# Byakugan Operational Report: [Project / Feature Name]

### Overall Status: [ 🟢 NOMINAL | 🟡 FRICTION | 🔴 BLOCKED ]
- **Progress:** [XX]% Complete ([X] of [Total] Goals & Checklist Items Verified)
- **Active Trajectory:** [One plain-English sentence summarizing current focus]

---

### 1. User Requests & Checklist Progress
Audited against prior user prompts, requested actions, and project roadmaps:

| Item / User Request | Origin (Chat Prompt / Checklist / Plan) | Status | Verification Evidence |
| :--- | :--- | :--- | :--- |
| [Request 1] | [e.g., User prompt turn 3] | [Verified Complete / In Progress / Blocked / Pending] | [Exact test, file check, or state observed] |
| [Task 2] | [e.g., Shikamaru Step 1.2] | [Verified Complete / In Progress / Blocked / Pending] | [Exact test, file check, or state observed] |
| [Ad-hoc fix] | [e.g., User checklist item] | [Verified Complete / In Progress / Blocked / Pending] | [Exact test, file check, or state observed] |

---

### 2. Execution Problems & Blocker Analysis
*(If no blockers exist, explicitly state: "No active blockers detected across the critical path.")*

| Issue / Failure Point | Human-Readable Impact | Recommended Countermeasure |
| :--- | :--- | :--- |
| [What failed or is stuck] | [How this affects the app or user] | [Immediate action needed] |

---

### 3. Verification Snapshot
- **Build / Syntax State:** [Passing / Failing / Untested]
- **Core User Flow State:** [Working / Partially Broken / Not Yet Built]
- **User Requirement Compliance:** [Fully Met / Gaps Identified / In Flight]
- **Untracked / Orphan Artifacts:** [None / List of files floating outside version control]

---

### 4. Recommended Tactical Move
State the single best skill to trigger next based on current findings:
- If a stubborn bug is blocking the critical path $\rightarrow$ **Activate Rasengan**
- If a quick punch-list issue needs clearing $\rightarrow$ **Activate Kunai**
- If ready to continue parallel building $\rightarrow$ **Dispatch Shadow Clone**
- If visual polish is needed $\rightarrow$ **Activate Sexy Jutsu**
```
