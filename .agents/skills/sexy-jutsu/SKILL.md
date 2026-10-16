---
name: sexy-jutsu
description: Visual QA, UI/UX audit, information architecture review, and iterative frontend styling polish. Use when an interface is functional but visually clunky, poorly spaced, data-dense, confusing in flow, or rough in presentation. Navigates user flows step-by-step, captures screenshots, audits data logic, information redundancy, copy clarity, and user intent alignment, and iteratively refines layout, styling, and thematic elegance.
---

# Sexy Jutsu: Iterative Visual QA, Flow & Thematic Elegance

Transform functional but rough, cluttered, or awkward interfaces into elegant, cohesive, and production-grade user experiences. Navigate user journeys step-by-step, capture screenshots at each view, audit both what the user sees (styling, spacing, thematic design) and what the user processes (data logic, cognitive load, language, intent alignment), and iteratively refine the UI without destabilizing underlying business logic.

## Core Directives

1. **Thematic Elegance (Form with Restraint):** Strive for visual refinement and balance. Respect and elevate the app's intended theme—whether it is a minimal dark workspace, a playful retro dashboard, or a stylized creative app. Elegance does not mean generic, sterile corporate gray; it means visual harmony, deliberate choices, and tasteful execution within the app's aesthetic identity.
2. **Data Logic & Information Density Audit:** Critically review the data presented on screen:
   - *Redundancy Check:* Is the same data point, metric, or status repeated across multiple cards or headers? Consolidate or cut it.
   - *Cognitive Load:* Is it an overwhelming wall of numbers, or does it leave the user guessing due to missing context? Curate information so the essential numbers/states stand out at a glance.
   - *Visual Flow:* Does the eye move naturally from the most important headline/action down to supporting details?
3. **User Intent Alignment:** Identify why the user opened this screen. Does the layout make their primary goal effortless to accomplish, or must they hunt through menus and dense tables? Elevate the primary intent; tuck secondary and administrative actions out of the visual line of fire.
4. **Copy & Microcopy Polish:** Eliminate clumsy, robotic system jargon. Refine button text, helper messages, table column headers, and empty-state placeholders so they are concise, human, and aligned with the app's tone.
5. **Screenshot-Driven Iteration:** Never guess how styling changes look in the DOM. Follow a strict visual loop: Navigate $\rightarrow$ Capture Screenshot $\rightarrow$ Inspect Visuals & Copy $\rightarrow$ Adjust Styles/Markup $\rightarrow$ Re-capture $\rightarrow$ Verify.
6. **Logic Preservation (Do No Harm):** Never break backend bindings, form submission handlers, state variables, or business logic while restyling. Modify presentation, copy phrasing, and structural markup framing without destabilizing core code.

---

## Execution Protocol

### Step 1: Context, Theme & User Intent Alignment
- Identify the target route(s) and primary user intent (e.g., *"User wants to review monthly expenses and approve pending invoices"*).
- Identify the app's aesthetic theme (e.g., sleek dark-mode, clean editorial, high-contrast retro, anime-themed) and design language conventions.

### Step 2: Journey Navigation & Initial Screenshot Capture
- Launch browser automation or headless inspection to load the target route.
- Navigate the full user journey step-by-step (e.g., Page Load $\rightarrow$ Open Detail View $\rightarrow$ Trigger State Change $\rightarrow$ Form Error State).
- Capture baseline screenshots at each milestone view:
  - `step-01-initial-view.png`
  - `step-02-active-interaction.png`
  - `step-03-state-change.png`

### Step 3: Comprehensive UI/UX Audit
Inspect captured images and markup against the core evaluation axes:
- **Data Logic & Redundancy:** Identify duplicate metrics, extraneous labels, or missing summary calculations.
- **Copy & Tone:** Flag robotic phrasing, overly verbose tooltips, or ambiguous button labels.
- **Visual Hierarchy & Spacing:** Check for cramped margins, uneven padding, inconsistent font weights, and competing colors.
- **Thematic Consistency:** Ensure borders, typography, accent colors, and component styles feel intentional and cohesive with the overall theme.

### Step 4: Iterative Refinement & Verification
- Apply surgical edits to markup and styling (Tailwind classes, CSS rules, component microcopy).
- Re-run browser capture to generate verification screenshots (`step-XX-after.png`).
- Compare before-and-after captures to ensure both visual elegance and informational clarity are achieved.

---

## Output Contract

Every Sexy Jutsu execution must follow this exact structure:

```markdown
# 💄 Sexy Jutsu UI/UX Polish: [Screen / Flow Name]

### 1. Intent & Thematic Assessment
- **Target Flow:** `[e.g., /dashboard/billing or modal flow]`
- **Primary User Intent:** [What the user came here to accomplish in 1 sentence]
- **Aesthetic Theme:** [App's visual identity, e.g., Sleek Cyberpunk Dark / Editorial Minimal / Vibrant Playful]
- **Baseline Friction:** [1–2 sentences on what felt cluttered, confusing, or unstyled]

---

### 2. Information Architecture & Copy Refinements
| Area Audited | Before State (Problem) | Refinement Made (After) | Impact on User Flow |
| :--- | :--- | :--- | :--- |
| **Data Redundancy** | [e.g., Balance shown in 3 places] | [Consolidated into 1 prominent hero metric] | Stripped cognitive clutter |
| **Information Density**| [e.g., 14 table columns visible] | [Curated to 5 core columns + drawer detail] | View breathes; easier scanning |
| **Microcopy & Tone** | [e.g., "Submit Payload" button] | [Changed to "Save Invoice"] | Human, outcome-focused label |

---

### 3. Step-by-Step Visual Transformations

#### Step 1: [Screen / Element Name]
- **Baseline Visual Issues:** [e.g., Low contrast text, cramped padding, harsh borders]
- **Adjustments Made:**
  - Expanded container spacing to an 8px rhythmic grid for breathing room.
  - Aligned styling with the app's theme (e.g., subtle frosted-glass border, muted accent glows).
  - Promoted the primary CTA button with distinct visual weight while subduing secondary options.
- **Files Modified:** `src/components/TargetComponent.tsx`
- **Screenshot Artifact:** `artifacts/visual/step-1-after.png`

#### Step 2: [Next Interaction / Element Name]
- **Baseline Visual Issues:** [e.g., Clunky drawer transition, unstyled empty state]
- **Adjustments Made:**
  - Replaced raw text empty state with a thematic illustration/icon and a clear action prompt.
  - Added smooth transition animations and polished typography hierarchy.
- **Files Modified:** `src/components/Drawer.tsx`
- **Screenshot Artifact:** `artifacts/visual/step-2-after.png`

---

### 4. Elegance & Usability Scorecard
| Dimension | Before Status | After Status |
| :--- | :--- | :--- |
| **Intent Facilitation** | Hidden / High friction | Immediate & obvious |
| **Data Redundancy** | Repetitive / Cluttered | Curated & high-signal |
| **Copy & Tone** | Technical / Robotic | Clear, elegant, and human |
| **Visual Polish & Theme** | Rough / Inconsistent | Cohesive, themed elegance |
```
