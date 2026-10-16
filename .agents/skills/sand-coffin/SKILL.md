---
name: sand-coffin
description: Internet-facing security hardening, attack surface reduction, and perimeter lockdown. Use before exposing an application to the public internet, before production launches, or during security audits. Enforces zero-trust defense, closes unauthorized endpoints, implements rate limiting, prevents injection and IDOR vulnerabilities, configures defensive HTTP headers, and eliminates data exfiltration risks.
---

# Sand Coffin: Absolute Defense & Perimeter Lockdown

Assume the application is deployed directly to the hostile, public internet where automated scrapers, malicious actors, and credential stuffers are actively probing for weaknesses. Sand Coffin seals every perimeter leak, restricts attack surfaces, sanitizes all inputs and outputs, and locks down endpoints until the system is impervious to exploitation.

## Core Directives

1. **Hostile Web Assumption (Zero Trust):** Never trust the client. Assume all incoming payloads, query parameters, cookies, and HTTP headers are crafted by an adversary. Every route must validate its caller, authenticate identity, and authorize resource ownership.
2. **Attack Surface Reduction:**
   - Detect and disable open development/debug endpoints (e.g., `/debug`, `/test-db`, Swagger docs exposed in production, hot-reload endpoints).
   - Ensure stack traces and internal database errors are swallowed server-side and never returned to the user or client console.
3. **Injection & Input Sanitization Shield:**
   - **SQL / NoSQL Injection:** Enforce parameterized queries or strict ORM boundaries. Flag any dynamic string concatenation in database queries.
   - **XSS & Content Injection:** Enforce strict escaping of user-generated content, sanitize rich text inputs, and block executable scripts.
   - **Command / Shell Injection:** Verify zero user inputs are directly passed into `exec()`, `spawn()`, or terminal sub-processes.
4. **IDOR & Authorization Fortification (Insecure Direct Object Reference):**
   - Ensure endpoints accepting an ID (e.g., `/api/documents/:id`) do not just check if the user is logged in, but verify that the requesting user *owns* that specific document.
5. **Data Exfiltration Defense (Response Pruning):**
   - Inspect API responses: strip out raw database columns, password hashes, internal foreign keys, reset tokens, and unneeded PII before JSON is returned. Return only the exact fields required by the UI.
6. **Perimeter Armor (Headers & Rate Limiting):**
   - Enforce rate limiting on auth endpoints (login, register, forgot-password) and costly AI/calculation routes to prevent brute-force attacks and denial-of-wallet spikes.
   - Enforce modern security headers: Content Security Policy (CSP), CORS restrictions (no open `*` on authenticated endpoints), HSTS, `X-Frame-Options: DENY`, and `X-Content-Type-Options: nosniff`.

---

## Execution Protocol

### Step 1: Perimeter Inventory & Route Audit
- Scan application routing tables to catalog all public, authenticated, and administrative endpoints.
- Check for exposed debug flags, verbose development logging, and unprotected administrative webhooks.

### Step 2: The Attack Vector Battery
Systematically inspect code for common perimeter vulnerabilities:
- **Authentication & Session:** Weak token storage, missing expiry, missing CSRF protection on mutation routes.
- **Access Control:** Horizontal privilege escalation (IDOR) and missing role guards.
- **Input Validation:** Unvalidated request bodies, lack of schema enforcement (e.g., missing Zod/Pydantic/Joi validation).
- **Exfiltration Vectors:** Over-fetching database records that leak directly into API responses.

### Step 3: Hardening & Policy Enforcement
- Configure defensive HTTP security headers.
- Inject rate-limiting middleware on public and sensitive routes.
- Replace dynamic database queries with parameterized statements.
- Apply response serialization schemas to filter returned payload properties.

### Step 4: Defense Scorecard Assembly
Compile findings into the standard perimeter defense contract.

---

## Output Contract

Every Sand Coffin audit and hardening run must follow this exact structure:

````markdown
# 🏺 Sand Coffin: Perimeter Defense & Security Audit

### Security Posture: [ 🟢 FORTIFIED | 🟡 VULNERABILITIES DETECTED | 🔴 CRITICAL EXPOSURE ]
- **Target Inspected:** `[Repository / Public API Routes / Application Surface]`
- **Attack Surface Audit:** [X] Endpoints Scanned ([Y] Public, [Z] Authenticated)
- **Exposure State:** [Production-Ready Hardened | Remediation Required Before Launch]

---

### 1. Perimeter Threat Vector Analysis
Audited against common internet-facing attack patterns:

| Attack Vector | Route / Component Checked | Observed Vulnerability | Defense Status |
| :--- | :--- | :--- | :--- |
| **Debug / Dev Routes** | `/api/debug/reset-db` | Endpoint accessible without auth | 🔴 Critical Exposure |
| **IDOR / Object Access** | `GET /api/invoices/:id` | Validates session, but not user ID ownership | 🔴 IDOR Vulnerability |
| **Data Exfiltration** | `GET /api/user/profile` | API returns entire DB user row (incl. salt) | 🔴 Data Leak |
| **SQL / Code Injection** | `POST /api/search` | Uses parameterized query engine | 🟢 Fortified |
| **Rate Limiting** | `POST /api/login` | No burst limits; vulnerable to brute force | 🟡 Unprotected Route |
| **Security Headers** | Global HTTP Middleware | Missing CSP and X-Frame-Options | 🟡 Missing Armor |

---

### 2. Attack Surface Reduction (What Was Sealed)
- **Closed Routes:** [List of development, debug, or unnecessary endpoints removed/gated]
- **Sanitized Outputs:** [List of sensitive database fields pruned from API responses]
- **Access Control Patches:** [Ownership validation checks injected into route handlers]

---

### 3. Fortification Blueprint & Code Patches
Provide the exact code fixes required to seal the vulnerabilities identified above:

#### Patch 1: [Vulnerability Name, e.g., IDOR on Invoices]
- **File:** `src/api/routes/invoices.ts`
- **Correction:** [Explanation of ownership assertion added]
```[language]
// Before: const invoice = await db.invoices.find(req.params.id);
// After: const invoice = await db.invoices.find({ id: req.params.id, userId: req.user.id });
```

---

### 4. Recommended Next Move
- To verify zero secret leaks or bypassed checks $\rightarrow$ Invoke `/anbu-black-ops`
- To torture-test hardened endpoints under load $\rightarrow$ Invoke `/chunin-exam`
- To package and ship the fortified build to GitHub $\rightarrow$ Invoke `/jiraiya`
````
