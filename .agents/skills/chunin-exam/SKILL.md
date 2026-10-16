---
name: chunin-exam
description: Verification, stress testing, and model competency audit. Use before shipping to verify if what was built actually does what was intended—evaluating AI prompt outputs, mathematical calculations, system latency, and edge-case resilience. Outputs a concise pass/fail scorecard with actionable fixes.
---

# Chunin Exam: Intent Verification & Stress Audit

Determine one fundamental truth: **Does the thing we built actually do what we want it to do?** 

Test beyond happy paths. Verify that calculations are correct, AI models follow instructions, flows produce the intended outcomes, and the system does not crumble under stress, weird inputs, or concurrency.

## Core Directives

1. **The True Intent Test:** Evaluate core functionality against desired outcomes:
   - **For Features & Flows:** Does the action achieve the user's primary goal with zero friction?
   - **For Mathematical / Algorithmic Models:** Are formulas, rankings, and scoring outputs mathematically sound, numerically stable, and verified against benchmark cases?
   - **For AI / LLM Workflows:** Does the prompt produce accurate, high-quality results while strictly adhering to negative constraints and output schemas?
2. **Boundary & Chaos Torture:** Actively probe for failure points:
   - *Data Extremes:* Zero values, empty states, massive text blobs, negative numbers, division by zero.
   - *Human Chaos:* Rapid repeated clicks, invalid formats, malformed payloads.
3. **Speed & Stability:** Ensure operations run within acceptable latency thresholds and maintain stability under simulated concurrent usage.
4. **Actionable Scorecard:** Avoid verbose logs. Hand back an executive pass/fail verdict with direct, punchy fixes for anything that falls short.

---

## Execution Protocol

1. **Verify Intent & Accuracy:** Run the core feature, formula, or prompt against a representative battery of target cases. Confirm outputs match the intended result.
2. **Torture Edge Cases:** Push extreme boundaries, missing inputs, and malformed data to ensure graceful error handling rather than unhandled crashes.
3. **Benchmark Latency & Load:** Measure response times ($p50$/$p95$) and verify stability under concurrent hits.
4. **Deliver Scorecard:** Grade the build (**PROMOTED**, **CONDITIONAL**, or **FAILED**) with surgical fixes for detected flaws.

---

## Output Contract

```markdown
# 📜 Chunin Exam Report Card: [Feature / Target Name]

### Final Verdict: [ 🟢 PROMOTED | 🟡 CONDITIONAL PASS | 🔴 FAILED ]
- **Core Intent Test:** [Passing / Failing] — [1 sentence verifying if it does what was wanted]
- **Target Type:** [Feature Flow | Math/Algorithm | AI Prompt Engine]
- **Stability & Concurrency:** [XX]% success rate under load

---

### 1. Intent & Accuracy Verification
| Test Vector | Intended Outcome | Observed Output | Verdict |
| :--- | :--- | :--- | :--- |
| **Primary Workflow** | [Expected outcome] | [Actual outcome observed] | 🟢 Pass |
| **Model / Formula Precision**| [Expected calculation/result] | [Observed output/accuracy] | 🟢 Pass |
| **Negative Constraints** | [Rule to respect] | [Did it obey?] | 🟢 Pass |

---

### 2. Edge-Case & Stress Torture
| Chaos Vector | Input Applied | System Reaction | Verdict |
| :--- | :--- | :--- | :--- |
| **Boundary / Extreme Input** | [e.g., zero value, 1MB blob] | [Handled cleanly / 500 error] | 🟢 Pass |
| **Rapid Concurrency** | [e.g., 20 parallel requests] | [Fast & stable / slowed down] | 🟡 Acceptable |

---

### 3. Remediation (What Needs Fixing)
*(If all tests pass cleanly: "Build performs exactly as intended. Zero blockers detected.")*

- **Issue:** [What broke or missed the target outcome]
- **Root Cause:** [Why it happened in 1 sentence]
- **Fix:** [Exact code or prompt change needed]
```
