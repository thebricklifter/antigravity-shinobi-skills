---
name: s-rank-mission
description: Master end-to-end project orchestrator and Shinobi pipeline commander. Use at the start of a chat or project when the user invokes 'S Rank Mission' or wants to kick off a full structured workflow from ideation to completion. Begins with Genjutsu to lock down user outcomes and determine deployment/release scope (local-only vs. public internet, local storage vs. GitHub), then dynamically sequences Sharingan, Shikamaru, Shadow Clone/Rasengan/Kunai, Byakugan, Sexy Jutsu, Chunin Exam, ANBU Black Ops, and conditional Sand Coffin/Jiraiya phases.
---

# S Rank Mission: Master End-to-End Shinobi Orchestrator

Take a project from raw spark to verified completion by orchestrating the entire Shinobi skill arsenal in a disciplined, adaptive sequence. Invoking **S Rank Mission** at the top of a chat establishes the Mission Charter and immediately opens **Phase 1: Genjutsu** to clarify the product outcome and lock in the project's **Exposure & Release Profile** (whether it stays local or goes to the public internet, and whether it stays on disk or ships to GitHub).

## Core Directives

1. **Immediate Genjutsu Kickoff:** When `s-rank-mission` is invoked, do not jump straight into code or architecture. Output the **S Rank Mission Charter** and immediately begin **Phase 1 (`genjutsu`)**—asking **one** sharp Socratic question at a time until the user releases with **"Kai"**.
2. **Early Scope Lock (Local vs. Public Web & GitHub Account):** During the `genjutsu` interrogation (if not already stated by the user), explicitly ask and lock down two operational boundaries in plain English:
   - **Audience & Exposure:** Is this purely for personal/local use on your machine, or will it be exposed to outside users on the public internet?
   - **Destination:** Is this staying strictly local on your machine, or shipping to GitHub—and if GitHub, is it **Personal (`thebricklifter`)** or **Work (`haydenamaro-ai`)**?
3. **Dynamic Pipeline Pruning:** Tailor the downstream mission stages based on the locked Exposure & Release Profile:
   - **If Local-Only (Not Public Internet):** Automatically **skip `sand-coffin`** (no need for public rate-limiting, hostile-web perimeter lockdown, or public CORS/CSP overhead unless requested).
   - **If Staying Off GitHub:** Automatically **skip `jiraiya`'s GitHub push** (run only local scratch-file cleanup at the end of the mission, or skip `jiraiya` entirely). If shipping to GitHub, lock the target account (`thebricklifter` vs. `haydenamaro-ai`) for `jiraiya`.
   - **If Headless / No UI:** Automatically **skip `sexy-jutsu`** (focus purely on CLI/data ergonomics).
4. **Stage-Gate Discipline:** Transition cleanly from one skill to the next. At the end of each stage, announce the completed stage and either automatically trigger the next stage in the active mission pipeline or pause when user input is required.

---

## The Adaptive S-Rank Pipeline

```text
[Stage 1: GENJUTSU]  ──► Clarify outcome, edge cases + lock [Local vs Public] & [Local vs GitHub (thebricklifter / haydenamaro-ai)]
        │                (💡 Summon KAKASHI SENSEI at any stage for an in-character field lesson on the problem domain)
        ▼
[Stage 2: SHARINGAN] ──► (Optional) Technical recon & pattern comparison if tricky/unfamiliar tech is involved
        │
        ▼
[Stage 3: SHIKAMARU] ──► Clever architectural shortcut + step-by-step Action Plan & Byakugan Tracker
        │                (Scoped strictly to the Exposure & Release Profile from Stage 1)
        ▼
[Stage 4: BUILD]     ──► Execute via SHADOW CLONE (parallel waves), RASENGAN (vertical grind), or KUNAI (micro-fixes)
        │
        ▼
[Stage 5: BYAKUGAN]  ──► Mid/Post-build audit: verify exact % completion against the Shikamaru ledger
        │
        ▼
[Stage 6: SEXY JUTSU]──► (Conditional: UI projects only) Screenshot-driven visual, copy & information density polish
        │
        ▼
[Stage 7: TRIALS]    ──► CHUNIN EXAM (verify true intent & edge-case resilience)
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

### Step 1: Mission Activation & Genjutsu Entry
When the user invokes **S Rank Mission** (with or without an initial project idea):
1. Render the **S Rank Mission Charter** banner below.
2. If the user hasn't described what we're building yet, ask them to pitch the idea in 1–2 sentences.
3. If the user *has* pitched the idea, immediately activate **`genjutsu` Phase 1**: identify the first product/human-behavior blindspot (or ask the scope/exposure question) and fire **Question 1**.

### Step 2: The "Kai" Transition into Shikamaru (and Optional Sharingan)
Once the user says **"Kai"**:
1. Output the completed **Genjutsu Feature Specification**, including the locked **Exposure & Release Profile**:
   - **Internet Exposure:** `Local / Private Only` vs. `Public Internet`
   - **Repository Target:** `Local Workspace Only` vs. `Personal GitHub (thebricklifter)` vs. `Work GitHub (haydenamaro-ai)`
   - **Interface Type:** `Visual UI` vs. `CLI / Script / Backend`
2. Display the **Locked Mission Pipeline** showing exactly which downstream skills are **ACTIVE** and which are **SKIPPED** based on that profile.
3. If the build involves a tricky technical unknown, run **`sharingan`** first; otherwise, flow directly into **`shikamaru`** to produce the execution roadmap and Byakugan tracker.

### Step 3: Build, Polish & Audit Loop
1. Execute the **`shikamaru`** plan using **`shadow-clone`** (for parallel tasks), **`rasengan`** (for deep single-point problems), and **`kunai`** (for rapid punch-list items).
2. Run **`byakugan`** to verify progress percentage.
3. Run **`sexy-jutsu`** if a frontend/UI exists.
4. Run **`chunin-exam`** and **`anbu-black-ops`** to verify that the build genuinely does what was intended with zero faked tests or hollow stubs.
5. Run **`sand-coffin`** *only* if marked `Public Internet`.
6. Run **`jiraiya`** *only* if shipping to GitHub (`thebricklifter` or `haydenamaro-ai`); otherwise perform a silent local scratch cleanup and deliver the final S-Rank Mission Complete summary.

---

## Output Contract

### 1. Mission Kickoff Banner (Turn 1)
Output when `s-rank-mission` is first triggered:

```markdown
# 👑 S-Rank Mission Initialized: [Project / Idea Name]

**Active Phase:** `Stage 1 — Genjutsu (Outcome & Scope Interrogation)`  
**Pipeline Status:** Awaiting `"Kai"` release to lock the **Exposure & Release Profile** (Local vs. Public Web / Local vs. GitHub: `thebricklifter` or `haydenamaro-ai`) and assemble the tailored execution pipeline.

---

### 🌀 Genjutsu Activated
[1–2 sentences acknowledging the user's idea and pointing out the first human-flow or scope question]

**Question 1:** [Single sharp, layman-friendly question]
```

### 2. Post-"Kai" Pipeline Lock (Transition to Shikamaru)
Output immediately after the `genjutsu` Feature Specification when the user says `"Kai"`:

```markdown
---

### 🗺️ S-Rank Mission Pipeline Locked
Based on your answers, here is the tailored Shinobi execution sequence for this mission:

- **Exposure Profile:** `[Local-Only | Public Internet]`
- **Release Target:** `[Local Workspace | Personal GitHub (thebricklifter) | Work GitHub (haydenamaro-ai)]`
- **Interface Profile:** `[Visual UI | Headless / CLI / Custom]`

| Stage | Jutsu | Mission Status | Reason |
| :--- | :--- | :--- | :--- |
| **1** | `genjutsu` | 🟢 Complete | Feature spec & scope boundaries locked |
| **2** | `sharingan` | `[⚡ Active / ⏭️ Skipped]` | `[Recon needed for X / Standard stack, no recon needed]` |
| **3** | `shikamaru` | 🚀 **Up Next** | Drafting clever architecture & Byakugan ledger |
| **4** | `shadow-clone` / `rasengan` | ⏳ Queued | Parallel build & vertical problem finishing |
| **5** | `byakugan` | ⏳ Queued | Milestone & binary % verification |
| **6** | `sexy-jutsu` | `[⏳ Queued / ⏭️ Skipped]` | `[Visual UI polish / Skipped: No visual UI]` |
| **7** | `chunin-exam` + `anbu` | ⏳ Queued | True intent stress-test & anti-cheat truth audit |
| **8** | `sand-coffin` | `[⏳ Queued / ⏭️ Skipped]` | `[Public web lockdown / Skipped: Local-only project]` |
| **9** | `jiraiya` | `[⏳ Queued / ⏭️ Skipped]` | `[GitHub release (thebricklifter / haydenamaro-ai) / Skipped: Staying off GitHub]` |
```
