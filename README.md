ret-scan.yml/badge.svg?branch=main)](https://github.com/KatieBarnes147/week3-sprint/actions/workflows/secret-scan.yml)

Week 3 builds on Git workflow habits (feature branches, clean merges, safe reverts) and runs a small set of services (Node/Python and/or Docker Compose). This repo is sanitized for public viewing.

---

## 🎯 Objectives
- Use branches → merge cleanly (no force-pushes)
- Practice **`git revert`** to preserve history
- Run services locally (Node/Python) or via **Docker Compose**
- Keep repos clean with **`.gitignore`** + **`.env.example`**
- Enable CI secret scanning (Gitleaks)

---

## 🔧 Tech Stack
- **Node.js** / **Python** (service code)
- **Docker & Docker Compose** (optional)
- **GitHub Actions** (Gitleaks, code scanning)

---

## 🚀 Quick Start

### A) Docker Compose (if `docker-compose.yml` exists)
```bash
docker compose up --build
# then open the port shown in `docker compose ps`, e.g.:
# http://localhost:3000 · http://localhost:5000 · http://localhost:8080
Stop: Ctrl+C (or docker compose down in another terminal).

B) Run Node service (no Docker)
bash
Copy code
cd <path-to-node-service>
npm install
# If service reads PORT:
# (PowerShell)  $env:PORT="5003"
# (bash)        PORT=5003
npm start  # or: node server.js
C) Run Python service (no Docker)
bash
Copy code
python -m venv .venv
.\.venv\Scripts\Activate.ps1   # macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
# If app reads PORT:
$env:PORT="5003"
python app.py

## 🖼️ Week 3 — Success
<p align="center">
  <img src="./public/success.png" alt="Week 3 — success screenshot" width="760">
</p>

🔒 Security
Real secrets are ignored (see .gitignore).

Safe placeholders live in .env.example.

CI: Gitleaks scans every push/PR (badge above).

🗂️ Structure (example)
bash
Copy code
.
├─ src/ or services/         # app/service code
├─ docker-compose.yml        # optional
├─ .env.example              # safe example config
├─ README.md
└─ docs/
   └─ week3-success.png      # screenshot used in README
✍️ Author
Katie Barnes
GitHub: @KatieBarnes147
