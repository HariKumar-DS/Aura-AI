# AGENTS.md

Guidelines for AI coding agents working on AURA AI.

---

## Project Structure

```
aura-ai/
├── main.py                  # Entry point
├── aura_backend.py          # Core AI brain
├── bridge_server.py         # Frontend ↔ backend bridge
├── whatsapp.py              # WhatsApp automation
├── database.py              # Session history (SQLite)
├── security.py              # API key isolation
├── screen_debug/            # Live screen capture
├── components/              # React components
├── services/                # Frontend services
├── electron/                # Electron shell
└── docs/                    # Documentation
```

---

## Key Rules

- **Never hardcode API keys** — always use `.env` via `security.py`
- **Voice commands are case-insensitive** — normalize before matching
- **All automations must be reversible** — don't delete files permanently without confirmation
- **Screen capture is local only** — only send to Gemini API, never elsewhere
- **Test voice paths** before merging — automation bugs are hard to catch otherwise

---

## Running Locally

```bash
pip install -r requirements.txt
npm install
cp .env.example .env
python main.py
```

---

## Backend Entry Points

| File | Purpose |
|------|---------|
| `main.py` | Start AURA — launches backend + Electron |
| `aura_backend.py` | Process voice input, call Gemini, execute tools |
| `bridge_server.py` | WebSocket bridge between Python and React |
| `whatsapp.py` | WhatsApp message automation |

---

## Adding a New Voice Command

1. Add intent pattern in `aura_backend.py`
2. Map it to an action function
3. Handle the response via `bridge_server.py`
4. Update `docs/AUTOMATION.md` with the new command example
