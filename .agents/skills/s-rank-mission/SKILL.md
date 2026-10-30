---
name: s-rank-mission
description: Master end-to-end project orchestrator and Shinobi pipeline commander. Use at the start of a chat or project when the user invokes 'S Rank Mission' or wants to kick off a full structured workflow from ideation to completion. Always includes Shikamaru to architect the clever execution plan and Byakugan tracker (and only runs Genjutsu if the user explicitly asks for it), then dynamically sequences Sharingan, Shadow Clone/Rasengan/Kunai, Byakugan, Sexy Jutsu, Chunin Exam, ANBU Black Ops, and conditional Sand Coffin/Jiraiya phases.
---

# S Rank Mission: Master End-to-End Shinobi Orchestrator

Take a project from raw spark to verified completion by orchestrating the entire Shinobi skill arsenal in a disciplined, adaptive sequence. Invoking **S Rank Mission** establishes the Mission Charter and immediately opens **Shikamaru** (unless the user explicitly asks for **Genjutsu** first) to architect the clever execution roadmap, lock the **Exposure & Release Profile**, and initialize the **Byakugan Baseline Tracking Ledger**.

## Core Directives

1. **Always Include `shikamaru` on the Highest-Level Model (`argon` / `pro`) — Only Include `genjutsu` If Explicitly Requested:**
   - **Frontier Model Routing for Planning (`argon`):** Always route `Stage 3: shikamaru` (strategic architecture, critical-path decomposition, and the "Shikamaru Move") to the **highest-level language model available—ideally `argon`** (or `Model="pro"` / `Model="inherit"` when running on `argon`). Never downgrade planning to `flash` or `flash_lite`.
   - **Default Entry (`shikamaru` Always Active):** When `s-rank-mission` is invoked without an explicit request for `genjutsu`, skip the Socratic interrogation and jump straight into **`shikamaru`** (preceded by optional `sharingan` recon only if needed) to formulate the "Shikamaru Move", Action Plan, and Byakugan Tracker, and begin executing immediately.
   - **Opt-In `genjutsu` Entry:** Run **`genjutsu`** *only* if the user explicitly asks for it (e.g., *"S Rank Mission with Genjutsu"* or *"Run Genjutsu first"*).
2. **Scope & Exposure Profile (Local vs. Public Web & GitHub Account):** Determine from the user's prompt (or ask only if genuinely ambiguous and blocking):
   - **Audience & Exposure:** `Local / Private Only` vs. `Public Internet`
   - **Destination:** `Local Workspace Only` vs. `Personal GitHub (thebricklifter)` vs. `Work GitHub (haydenamaro-ai)`
3. **Dynamic Pipeline Pruning:** Tailor the downstream mission stages based on the Exposure & Release Profile:
   - **If Local-Only (Not Public Internet):** Automatically **skip `sand-coffin`** (no need for public rate-limiting, hostile-web perimeter lockdown, or public CORS/CSP overhead unless requested).
   - **If Staying Off GitHub:** Automatically **skip `jiraiya`'s GitHub push** (run only local scratch-file cleanup at the end of the mission, or skip `jiraiya` entirely). If shipping to GitHub, lock the target account (`thebricklifter` vs. `haydenamaro-ai`) for `jiraiya`.
   - **If Headless / No UI:** Automatically **skip `sexy-jutsu`** (focus purely on CLI/data/automation ergonomics).
4. **Stage-Gate Discipline:** Transition cleanly from one skill to the next. At the end of each stage, announce the completed stage and automatically trigger the next stage in the active mission pipeline (pausing only when user input is genuinely required).

---

## The Adaptive S-Rank Pipeline

```text
[Stage 1: GENJUTSU]  ──► (Conditional: ONLY if explicitly requested by the user) Socratic outcome interrogation until "Kai"
        │                (💡 Summon KAKASHI SENSEI at any stage for an in-character field lesson on the problem domain)
        ▼
[Stage 2: SHARINGAN] ──► (Optional) Technical recon & pattern comparison if tricky/unfamiliar tech is involved
        │
        ▼
[Stage 3: SHIKAMARU] ──► (MANDATORY — ALWAYS INCLUDED) Clever architectural shortcut + step-by-step Action Plan & Byakugan Tracker
        │
        ▼
[Stage 4: BUILD]     ──► Execute via SHADOW CLONE (parallel waves), RASENGAN (vertical grind), or KUNAI (micro-fixes)
        │                + SUMMONING JUTSU (if spinning up a local web app on a free port)
        ▼
[Stage 5: BYAKUGAN]  ──► Mid/Post-build audit: verify exact % completion against the Shikamaru ledger
        │
        ▼
[Stage 6: SEXY JUTSU]──► (Conditional: UI projects only) Screenshot-driven visual, copy & information density polish
        │
        ▼
[Stage 7: TRIALS]    ──► CHUNIN EXAM (verify true intent, speed & edge-case resilience)
        │                + ANBU BLACK OPS (verify zero faked tests, hollow stubs, or secret leaks)
        ▼
[Stage 8: PERIMETER] ──► (Conditional: ONLY if Public Internet) SAND COFFIN perimeter security lockdown
        │
        ▼
[Stage 9: CLOSEOUT]  ──► (Conditional: ONLY if GitHub) JIRAIYA release chronicle & push to [thebricklifter | haydenamaro-ai]
                         (If Local-Only: quick workspace scratch cleanup & final Byakugan 100% sign-off)
```

---

## Execution Protocol

### Step 1: Mission Activation & Direct Shikamaru Kickoff (Default)
When the user invokes **S Rank Mission**:
1. Render the **S Rank Mission Charter & Locked Pipeline** banner below.
2. **Unless the user explicitly asked for `genjutsu`**, mark `Stage 1: genjutsu` as `⏭️ Skipped (Not requested)` and immediately execute **`Stage 3: shikamaru`** (or `Stage 2: sharingan` $\rightarrow$ `Stage 3: shikamaru` if technical recon is needed first).
3. Output the full **`shikamaru`** Strategic Plan (Executive Summary & The "Shikamaru Move", Architectural Traps & Countermeasures, Action Plan & Shadow Clone Dispatch Matrix, and Byakugan Baseline Tracking Ledger) and immediately proceed into **Stage 4: Build / Execution**.

### Step 2: Optional Opt-In Genjutsu Path (Only When Requested)
If the user explicitly requests **`genjutsu`**:
1. Ask one sharp Socratic question at a time until the user releases with **"Kai"**.
2. Once released with **"Kai"**, flow directly into **`shikamaru`**.

### Step 3: Build, Polish & Audit Loop
1. Execute the **`shikamaru`** plan using **`shadow-clone`** (for parallel tasks), **`rasengan`** (for deep single-point problems / iterative trials), and **`kunai`** (for rapid punch-list items).
2. Run **`byakugan`** to verify progress percentage against the ledger.
3. Run **`sexy-jutsu`** if a frontend/UI exists.
4. Run **`chunin-exam`** and **`anbu-black-ops`** to verify that the build genuinely does what was intended with zero faked tests, zero formula corruption, and zero hollow stubs.
5. Run **`sand-coffin`** *only* if marked `Public Internet`.
6. Run **`jiraiya`** *only* if shipping to GitHub (`thebricklifter` or `haydenamaro-ai`); otherwise perform a clean final Byakugan 100% sign-off.

---

## Output Contract

### 1. Mission Kickoff & Pipeline Lock Banner
Output when `s-rank-mission` is triggered:

```markdown
# 👑 S-Rank Mission Initialized: [Project / Idea Name]

- **Exposure Profile:** `[Local-Only | Public Internet]`
- **Release Target:** `[Local Workspace | Personal GitHub (thebricklifter) | Work GitHub (haydenamaro-ai)]`
- **Interface Profile:** `[Visual UI | Headless / CLI / Browser Automation]`

| Stage | Jutsu | Mission Status | Reason |
| :--- | :--- | :--- | :--- |
| **1** | `genjutsu` | `[⏭️ Skipped / ⚡ Active]` | `[Skipped: Only runs when explicitly requested / Active by user request]` |
| **2** | `sharingan` | `[⚡ Active / ⏭️ Skipped]` | `[Recon needed for X / Skipped: Architecture known]` |
| **3** | `shikamaru` | 🚀 **Active (Mandatory)** | Drafting clever architecture & Byakugan ledger |
| **4** | `shadow-clone` / `rasengan` | ⏳ Queued | Execution & iterative verification |
| **5** | `byakugan` | ⏳ Queued | Milestone & binary % verification |
| **6** | `sexy-jutsu` | `[⏳ Queued / ⏭️ Skipped]` | `[Visual UI polish / Skipped: No visual UI]` |
| **7** | `chunin-exam` + `anbu` | ⏳ Queued | True intent stress-test & anti-cheat truth audit |
| **8** | `sand-coffin` | `[⏳ Queued / ⏭️ Skipped]` | `[Public web lockdown / Skipped: Local-only project]` |
| **9** | `jiraiya` | `[⏳ Queued / ⏭️ Skipped]` | `[GitHub release / Skipped: Staying off GitHub]` |
```
