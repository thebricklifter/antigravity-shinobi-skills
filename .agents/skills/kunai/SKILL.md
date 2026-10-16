---
name: kunai
description: Rapid-fire tactical micro-fixes, punch-list execution, and surgical bug patches. Use when the user requests immediate, small fixes, typo corrections, styling tweaks, or provides a punch list of minor issues across one or more files. Dispatches one lightweight agent per problem, executes minimal diffs, and reports back with snappy 3-line debriefs (cause, action, status).
---

# Kunai: Tactical Strike & Punch-List Volley

Execute surgical, high-speed micro-fixes with minimal footprint and zero architectural drift. You do not overthink, spawn sprawling planning sessions, or redesign components. When handed a single issue or a bulleted punch list of small problems, dispatch one lightweight agent per target, strike precisely, verify the fix, and report back immediately with a snappy debrief.

## Core Directives

1. **Zero-Ceremony & High Speed:** Pull and throw. Do not write architectural design documents, run extensive discovery, or overhaul surrounding workflows. Apply the minimal necessary patch directly.
2. **Surgical Diff Boundary:** 
   - Touch only the lines directly responsible for the requested fix.
   - **Never** reformat or refactor adjacent functions.
   - **Never** rename untouched variables or reorder imports.
   - **Never** introduce new libraries or heavy dependencies.
3. **Dispatch Pattern (Agent Per Problem):**
   - **Single Strike:** Handed a single problem $\rightarrow$ One agent isolates, fixes, verifies, and debriefs.
   - **Volley Mode (Fan-Out):** Handed a punch list with multiple items $\rightarrow$ Dispatch one dedicated, lightweight worker agent per bullet point to resolve them simultaneously without overlapping files.
4. **Mandatory 3-Part Explanation:** Every fixed item must explicitly state:
   - *Why it happened* (Root cause).
   - *What was done* (Action taken).
   - *Status* (Verification proof).
5. **Snappy & Brief Output:** Keep conversational text to an absolute minimum. Return only the structured debrief.

---

## Execution Protocol

### Step 1: Target Ingestion & Mode Selection
- Inspect the prompt:
  - If a single problem is described $\rightarrow$ Enter **Single Strike Mode**.
  - If a punch list or multiple items are described $\rightarrow$ Enter **Volley Mode**.

### Step 2: Target Isolation & Worker Dispatch
- Isolate the specific file, route, or UI element for each problem.
- In Volley Mode:
  - Assign each punch-list item to a distinct worker agent.
  - Verify workers operate on separate files or lines to prevent merge collisions.

### Step 3: Surgical Execution & Verification
- Apply the targeted fix (target: under 5 lines diff per item).
- Run the immediate unit test, linter check, or local syntax check to verify the patch.

### Step 4: Rapid Debrief Assembly
- Format results into the uniform, snappy Kunai report format.

---

## Output Contract

Every Kunai output must follow this concise format:

### 1. Single Strike Output
```markdown
# 🗡️ Kunai Strike

**Target:** `src/components/Header.tsx` (CTA Button)
**Cause:** Button label was hardcoded as "Log In" instead of pulling the dynamic `user ? "Dashboard" : "Log In"` state.
**Action:** Replaced static string with auth condition check; verified on local render.
**Status:** 🟢 Resolved & Verified
```

### 2. Volley Mode Output
```markdown
# 🗡️ Kunai Volley: [N] Targets Hit

#### Target 1: `src/pages/Pricing.tsx` (Tier 2 Price)
- **Cause:** Typo in pricing string array showing `$49` instead of `$39`.
- **Action:** Corrected value to `$39` in `tierData.ts`.
- **Status:** 🟢 Resolved & Verified

#### Target 2: `src/api/auth.ts` (Redirect URL)
- **Cause:** Missing fallback environment variable caused undefined redirect on logout.
- **Action:** Added fallback default to `/login` when `NEXT_PUBLIC_APP_URL` is unset.
- **Status:** 🟢 Resolved & Verified

#### Target 3: `src/styles/card.css` (Hover Border)
- **Cause:** Missing CSS transition rule caused harsh flickering on mouse hover.
- **Action:** Added `transition: border-color 150ms ease-in-out` to `.card` class.
- **Status:** 🟢 Resolved & Verified
```
