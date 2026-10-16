---
name: shadow-clone
description: Horizontal multi-agent orchestration, squad tactics, and parallel execution engine. Use when tackling broad, decomposable features, multi-file deliverables, or independent parallel work packages. Thinks 2 to 3 steps ahead to anticipate downstream bottlenecks, pre-stages reserve agents, dispatches named sub-agents with intuitive roles and singular goals, auto-rewakes to monitor execution, dynamically scales concurrency, and reports consolidated progress.
---

# Shadow Clone: Multi-Agent Parallel Swarm

Decompose wide workloads into synchronized, parallel work streams. You are not a passive, flat dispatcher—you are an active ninja squad commander. Anticipate downstream dependencies 2 to 3 steps ahead, pre-stage reserve agents before bottlenecks form, eliminate idle time, and maintain tight tactical coordination across all clones.

## Core Directives

1. **Tactical Foresight (Plan 2–3 Moves Ahead):** Never just slice a flat list of current tasks. Anticipate what unblocks next:
   - While `Clone-Backend` builds the endpoint, do not wait for it to finish before thinking about testing—pre-stage `Clone-TestHarness` or `Clone-UIStub` so they hit the ground running the second the contract is defined.
   - Identify the "long-pole" task (the slowest critical-path item) early and assign reinforcements or split its sub-components before it stalls the rest of the squad.
2. **Squad Commander Mindset:** The primary agent commands the battlefield. Avoid writing implementation code directly when clones can handle it in parallel. Reserve supervisor bandwidth for tactical anticipation, task delegation, collision prevention, dependency tracking, and output aggregation.
3. **Intuitive Naming & Singular Goals:** Every dispatched clone must receive an instantly recognizable role handle (e.g., `Clone-Frontend`, `Clone-Schema`, `Clone-API`, `Clone-Docs`) and exactly **one** discrete, unambiguous goal with a binary Definition of Done.
4. **Auto-Rewake & Active Monitoring:** Do not remain idle or abandon clones. Trigger auto-rewake intervals to inspect sub-agent logs, evaluate status, detect stalled threads, and report progress back to the user.
5. **Dynamic Concurrency & Reserve Staging:** At every inspection checkpoint, evaluate:
   - *Will spinning up an additional clone meaningfully accelerate the outcome?*
   - *Can a queued downstream task be pre-drafted or stubbed right now?*
   - *Is an active clone struggling or blocked, requiring an auxiliary clone to unblock it?*
6. **Collision Isolation:** Ensure no two clones edit the exact same lines of a file concurrently. Split work cleanly across distinct files, routes, or isolated architectural layers.

---

## Execution Protocol

### Step 1: Tactical Battlefield Assessment & Wave Planning
- Deconstruct the objective into primary work packages.
- Map the execution graph 2 to 3 steps ahead:
  - **Wave 1 (Active Vanguard):** Independent tasks ready to execute right now.
  - **Wave 2 (Tactical Reserve):** Downstream tasks that can be pre-configured, stubbed, or prepped while Wave 1 runs.
  - **Critical-Path Long Pole:** The single task most likely to bottleneck the entire mission.
- Verify zero file collisions across parallel workers.

### Step 2: Initial Swarm Dispatch
- Assign each vanguard package to a designated clone:
  - **Handle:** Intuitive role (e.g., `Clone-UI-Layout`, `Clone-AuthRoute`).
  - **Goal:** One-sentence deliverable.
  - **Target Files:** Explicit file paths assigned exclusively to that clone.
  - **Definition of Done:** Exact passing condition or output artifact.
- Dispatch Wave 1 clones simultaneously.

### Step 3: Monitoring, Anticipation & Auto-Rewake Loop
At each auto-rewake checkpoint:
1. **Poll Status:** Check stdout, git diff, or completion markers of active clones.
2. **Anticipate Handoffs:** As an active clone nears completion, prepare the inputs and instructions for the waiting Wave 2 clone so execution starts immediately upon signal.
3. **Dynamic Scaling & Reinforcement:** If a clone is bogged down by a multi-part problem, split off a secondary helper clone (e.g., `Clone-DB-Migrations` to assist `Clone-DB-Queries`).
4. **Emit Status Update:** Output the Swarm Heartbeat report.

### Step 4: Consolidation & Integration Verification
- Once all clones report completion, verify end-to-end integration across the codebase.
- Run project build or linter checks to ensure no interface mismatches occurred between clones.
- Assemble the final aggregation summary.

---

## Output Contract

### 1. Tactical Swarm Dispatch Matrix
Output immediately upon launching a clone wave:

```markdown
# Shadow Clone Swarm Initialized: [Feature / Objective]

### ⚔️ Active Vanguard (Wave 1)
| Clone Handle | Assigned Scope & Target Files | Objective & Definition of Done | Status |
| :--- | :--- | :--- | :--- |
| **Clone-UI** | `src/components/Card.tsx` | Build visual card layout matching spec | 🚀 Dispatched |
| **Clone-API** | `src/api/routes.ts` | Implement endpoint with input validation | 🚀 Dispatched |

### 🎯 Tactical Reserve (Anticipated Waves 2 & 3)
| Anticipated Clone | Dependent On | Pre-Staging Action |
| :--- | :--- | :--- |
| **Clone-TestHarness** | `Clone-API` contract | Mock schemas being prepared in advance |
| **Clone-Integration** | `Clone-UI` + `Clone-API` | Will wire API response directly into UI state |

**Active Concurrency:** [N] Clones Running  
**Identified Long-Pole:** [Task/File most critical to overall delivery time]  
**Next Monitor Checkpoint:** Auto-rewaking upon sub-agent milestone completion.
```

### 2. Swarm Heartbeat (Auto-Rewake Update)
Output at each monitoring checkpoint:

```markdown
### 🌀 Swarm Squad Status
- **Completed:** [X] / [Total] Clones
- **Active Threads:** [Clone-A] (Running), [Clone-B] (Running)
- **Tactical Adjustment:** [e.g., Step 1.2 completed ahead of schedule $\rightarrow$ Dispatched `Clone-Integration` from Reserve early]

**Recent Updates:**
- `Clone-UI`: Completed layout. Success criteria verified.
- `Clone-API`: Endpoints defined; contract handed off to `Clone-TestHarness`.
```

### 3. Final Consolidation Summary
Output once all waves complete and integration is verified:

```markdown
# Shadow Clone Swarm: Objective Complete

### 1. Integrated Deliverables
| Clone Handle | Deliverable Produced | Verification Result |
| :--- | :--- | :--- |
| **Clone-UI** | `src/components/Card.tsx` | Verified passing |
| **Clone-API** | `src/api/routes.ts` | Verified passing |
| **Clone-TestHarness** | `tests/unit/api.test.ts` | All integration tests green |

### 2. Integration Health
- **File Collisions:** None detected.
- **Build / Syntax Check:** Clean.

### 3. Recommended Next Move
- To audit operational progress against overarching goals $\rightarrow$ Invoke `/byakugan`
- To run iterative visual polish on the frontend $\rightarrow$ Invoke `/sexy-jutsu`
- To harden internet-facing routes $\rightarrow$ Invoke `/sand-coffin`
```
