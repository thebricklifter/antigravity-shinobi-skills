---
name: summoning-jutsu
description: Local app launcher, zero-collision port finder, and active localhost port mapper. Use when the user invokes 'Summoning Jutsu', asks to spin up or preview the app locally, wants a clickable localhost link on a free port, or wants a plain-English map of what apps and services are currently running on other local ports.
---

# Summoning Jutsu: Local App Launcher & Port Atlas

Perform the hand seals, slam the palm to the ground, and summon a live local instance of the current application onto a guaranteed free port—without colliding with or killing other running projects. Alongside a prominent clickable link to the newly summoned app, deliver a clean, plain-English **Localhost Port Atlas** mapping what is currently running across other local ports on the machine.

## Core Directives

1. **Zero-Collision Port Selection:**
   - Never blindly launch onto a hardcoded default port (`3000`, `5173`, `8000`) if another process is already listening there.
   - Never kill an existing local server on another port unless the user explicitly asks to replace it.
   - Scan active listening TCP ports first (`lsof -iTCP -sTCP:LISTEN -P -n`) and pick a clean, un-utilized port (e.g., `3000–3099`, `5173–5199`, `8000–8099`, or `4100–4199`).
2. **Plain-English Localhost Port Map (Not Just "node" or "python"):**
   - A raw `lsof` output saying `node (PID 12345)` is useless to a human.
   - For every relevant listening local port, inspect the process's working directory and command line (`lsof -a -p <PID> -d cwd -Fn` and `ps -p <PID> -o args=`) so you can describe **what project or service it actually is** in simple, human terms (e.g., *"Earhart Anomaly Viewer (Vite Frontend)"*, *"PostgreSQL Local Database"*, *"FastAPI Backend for noble-pasteur"*).
   - Separate **Active Dev / Web Apps** from **Databases & Background System Listeners** (like macOS AirPlay Receiver on `5000`/`7000` or ControlCenter) so the map stays scannable and noise-free.
3. **Automatic Stack Detection & Port Injection:**
   - Detect the workspace stack automatically and pass the chosen free port `<PORT>` explicitly:
     - **Vite / React / Vue / Svelte:** `npx vite --port <PORT> --strictPort` or `npm run dev -- --port <PORT>`
     - **Next.js:** `npx next dev -p <PORT>` or `PORT=<PORT> npm run dev`
     - **Node / Express / Custom JS:** `PORT=<PORT> npm run dev` (or `npm start`)
     - **FastAPI / Uvicorn / Flask / Django:** `uvicorn <app>:app --port <PORT>`, `flask run --port <PORT>`, or `python3 manage.py runserver <PORT>`
     - **Streamlit / Gradio:** `streamlit run <script>.py --server.port <PORT> --server.headless true`
     - **Static HTML / Markdown / Prototype:** `python3 -m http.server <PORT>`
   - Launch the server using `run_command` with `IsDaemon: true` so it remains running in the background after your turn ends.
4. **Live Pulse Verification Before Presenting the Link:**
   - Do not hand over a dead link. Verify the newly summoned server is actively listening and returning HTTP responses (`curl -I -s http://localhost:<PORT>` or `lsof -i :<PORT>`) before outputting the final card.
5. **Prominent Clickable Link:**
   - Always format both the newly summoned app URL and any web-accessible ports in the Port Atlas as clickable Markdown links (`[http://localhost:<PORT>](http://localhost:<PORT>)`).

---

## Execution Protocol

### Step 1: Localhost Recon & Port Census
1. Run `lsof -iTCP -sTCP:LISTEN -P -n` to list all listening TCP ports and their PIDs.
2. For each active user/dev PID, inspect its working directory (`lsof -a -p <PID> -d cwd`) and full command (`ps -p <PID> -o comm=,args=`) to determine the project name and a simple 1-line description of what that port is serving.
3. Select an un-utilized port `<PORT>` appropriate for the current project.

### Step 2: Stack Inspection & Daemon Summoning
1. Check the current workspace (`package.json`, `pyproject.toml`, `requirements.txt`, `index.html`, etc.) to determine the exact start command.
2. If dependencies (`node_modules`, `.venv`) are missing, install them or use the appropriate runner.
3. Start the server on `<PORT>` as a background daemon (`IsDaemon: true`).

### Step 3: Readiness Verification
1. Poll briefly (1–3 seconds) and verify via `lsof -i :<PORT>` and `curl -s -o /dev/null -w "%{http_code}" http://localhost:<PORT>` that the server is live and ready for browser navigation.

### Step 4: Render the Summoning Scroll & Port Atlas
1. Output the clickable link to the newly summoned app and the complete map of other active ports using the Output Contract below.

---

## Output Contract

Every Summoning Jutsu execution must follow this exact structure:

```markdown
# 🐸 Summoning Jutsu: Local App Deployed!

### 🚀 Navigate to Your App: **[http://localhost:<PORT>](http://localhost:<PORT>)**
- **Project / Workspace:** `[Workspace or App Name]`
- **Assigned Port:** `<PORT>` *(verified conflict-free)*
- **Runtime / Command:** `[e.g., Vite Dev Server / FastAPI / Python HTTP Server]` (PID `[PID]`)
- **Health Status:** 🟢 **LIVE & LISTENING** (`HTTP 200 OK`)

---

### 🗺️ Localhost Port Atlas (What's Running Where)

#### 🌐 Active Web Apps & Dev Servers
| Port & Link | Project / Folder | Simple Description (What's on this port) | Process / PID |
| :--- | :--- | :--- | :--- |
| **[http://localhost:<PORT>](http://localhost:<PORT>)** | `[current-workspace]` | ⭐ **Just Summoned:** [1-line description of current app] | `[cmd]` (`[PID]`) |
| **[http://localhost:<OTHER>](http://localhost:<OTHER>)** | `[other-project]` | [Plain-English description of what app/UI lives here] | `[cmd]` (`[PID]`) |

#### 🗄️ Databases, APIs & System Listeners
| Port | Service / Owner | Simple Description |
| :--- | :--- | :--- |
| `:<DB_PORT>` | `[e.g., PostgreSQL / Redis / AirPlay]` | [Plain-English explanation, e.g., "macOS AirPlay Receiver (system service)" or "Local Postgres DB"] |

---

### 💡 Quick Controls
- **Open App:** Click **[http://localhost:<PORT>](http://localhost:<PORT>)**
- **Next Move:** Need visual polish on what you see? Summon `/sexy-jutsu`. Found a bug? Summon `/kunai` or `/rasengan`.
```
