---
name: ninja-scroll
description: Interactive jutsu directory, skill inventory, and tactical command reference. Use when the user asks to see their skills, list available jutsus, open the Ninja Scroll, check what Naruto skills are installed, or asks which skill to invoke for a task. Scans local and global skill directories and presents a categorized, scannable reference of the user's custom skill arsenal.
---

# Ninja Scroll: The Master Jutsu Arsenal & Command Index

Unfurl the master scroll to display the user's complete arsenal of custom Shinobi skills. Organize all installed skills by tactical phase so the user can immediately see what each jutsu does, when to summon it, and how the skills chain together across a build lifecycle.

## Core Directives

1. **Live Ground-Truth Discovery:** Never rely solely on a static list. Quickly check `.agents/skills/` (and `~/.gemini/config/skills/` if accessible) to ensure any newly forged custom skills are included in the scroll.
2. **Focus on User's Custom Arsenal:** Prioritize the user's custom local/global skills (the Shinobi suite and any user-authored additions). Do not clutter the scroll with dozens of default system/plugin skills unless the user explicitly asks for built-in skills too.
3. **Tactical Lifecycle Grouping:** Present skills in logical mission order—from ideation and planning, to parallel/vertical execution, to UI polish and stress-testing, to security/integrity audits and GitHub shipping.
4. **Actionable Trigger Reference:** Show the exact `/skill-name` or natural-language trigger phrase alongside a punchy 1-line summary of when to use it.

---

## Execution Protocol

### Step 1: Scroll Inventory Check
- Inspect `.agents/skills/` in the current workspace (and `~/.gemini/config/skills/` if synced globally) to verify all installed custom skills.

### Step 2: Tactical Categorization
Group discovered skills into the core operational phases:
- **👑 Mission Command & Orchestration:** `s-rank-mission`, `ninja-scroll`
- **🧠 Strategy, Recon & Ideation:** `genjutsu`, `sharingan`, `shikamaru`
- **⚡ Execution, Swarm & Bug Finishing:** `shadow-clone`, `rasengan`, `kunai`
- **✨ Visual Polish & Competency Trials:** `sexy-jutsu`, `chunin-exam`, `byakugan`
- **🛡️ Defense, Internal Affairs & Release:** `anbu-black-ops`, `sand-coffin`, `jiraiya`
- *(Plus any newly added custom skills discovered in the directory)*

### Step 3: Unfurl the Output Contract
Render the structured Ninja Scroll table and lifecycle workflow guide.

---

## Output Contract

Every Ninja Scroll invocation must follow this exact structure:

```markdown
# 📜 The Forbidden & Master Ninja Scroll

**Installed Custom Jutsus:** [N] Active Skills | **Scope:** [Workspace `.agents/skills/` | Global `~/.gemini/config/skills/`]

---

### 👑 0. Mission Command & Master Orchestration
| Jutsu / Skill | Trigger | Role & Core Superpower | When to Summon |
| :--- | :--- | :--- | :--- |
| **S Rank Mission** | `/s-rank-mission` | End-to-End Mission Commander | Top of a chat—kicks off `Genjutsu` (including Local vs. Public Web & GitHub scope check) and orchestrates the tailored pipeline from start to finish. |
| **Ninja Scroll** | `/ninja-scroll` | Master Jutsu Directory | Displays this categorized command reference of all installed custom skills. |

---

### 🧠 I. Ideation, Recon & Strategic Planning
| Jutsu / Skill | Trigger | Role & Core Superpower | When to Summon |
| :--- | :--- | :--- | :--- |
| **Genjutsu** | `/genjutsu` | Socratic Product Sparring | Before coding—interrogates human flows, edge cases, and deployment/GitHub scope 1 question at a time until released with `"Kai"`. |
| **Sharingan** | `/sharingan` | Technical Recon & Mentor | Stuck on a tricky architecture choice—researches real-world patterns, compares tradeoffs & teaches the mental model. |
| **Shikamaru** | `/shikamaru` | Master Strategic Planner | Ready to plan—finds the clever 20-line shortcut and builds a step-by-step roadmap for Shadow Clones & Byakugan. |

---

### ⚡ II. Execution, Parallel Swarms & Bug Finishing
| Jutsu / Skill | Trigger | Role & Core Superpower | When to Summon |
| :--- | :--- | :--- | :--- |
| **Shadow Clone** | `/shadow-clone` | Multi-Agent Parallel Swarm | Broad multi-file build—plans 2–3 waves ahead, dispatches parallel worker clones & monitors handoffs. |
| **Rasengan** | `/rasengan` | Relentless Vertical Finisher | Single stubborn bug or failing test—locks onto a binary test anchor and grinds autonomously until green. |
| **Kunai** | `/kunai` | Tactical Micro-Fix Volley | Quick punch list or small tweaks—strikes surgically (<5 lines) with zero ceremony and a 3-line debrief. |

---

### ✨ III. Operational Vision, UI Polish & Stress Testing
| Jutsu / Skill | Trigger | Role & Core Superpower | When to Summon |
| :--- | :--- | :--- | :--- |
| **Byakugan** | `/byakugan` | All-Seeing Health & Tracker | Need status clarity—audits chat history, checklists & code to calculate exact % completion and blockers. |
| **Sexy Jutsu** | `/sexy-jutsu` | Visual QA & UI/UX Elegance | Functional but ugly/cluttered UI—screenshots user flows, cuts redundant data, refines copy & polishes theme. |
| **Chunin Exam** | `/chunin-exam` | Intent & Chaos Stress Audit | Pre-ship trial—verifies math/AI/flows actually do what was intended under boundary torture & load. |

---

### 🛡️ IV. Security, Anti-Cheating & GitHub Release
| Jutsu / Skill | Trigger | Role & Core Superpower | When to Summon |
| :--- | :--- | :--- | :--- |
| **ANBU Black Ops**| `/anbu-black-ops`| Internal Affairs Inquisition | Trust check—audits git diffs & logs to catch faked tests, hollow stubs, `@ts-ignore` cheats & leaked secrets. |
| **Sand Coffin** | `/sand-coffin` | Perimeter Security Lockdown | *(Conditional: Public Internet only)* Seals debug routes, fixes IDOR/injection risks, prunes responses & adds rate limits/headers. |
| **Jiraiya** | `/jiraiya` | Release Author & GitHub Ship | *(Conditional: GitHub projects only)* Purges temp files, writes release chronicles, creates clean commits & pushes to GitHub. |

---

### 🔄 The S-Rank Mission Lifecycle
`S Rank Mission` $\rightarrow$ `Genjutsu` *(locks Idea + Local vs. Public Internet + Local vs. GitHub)* $\rightarrow$ `Sharingan` *(if needed)* $\rightarrow$ `Shikamaru` $\rightarrow$ `Shadow Clone` / `Rasengan` / `Kunai` $\rightarrow$ `Byakugan` $\rightarrow$ `Sexy Jutsu` *(if UI)* $\rightarrow$ `Chunin Exam` + `ANBU` $\rightarrow$ `Sand Coffin` *(only if Public Internet)* $\rightarrow$ `Jiraiya` *(only if GitHub)*
```
