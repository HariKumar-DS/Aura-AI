# Changelog

All notable changes to AURA AI are documented here.

---

## [v0.1.0] — 2026-05-08 — Initial Release

### Added
- Voice-controlled interface via Gemini TTS
- Live screen vision — AURA sees your screen
- WhatsApp automation via voice command
- Email sending via voice
- Web search integration
- Image generation from voice descriptions
- File management — open, move, delete, organize
- PDF open/close support
- YouTube & music playback by voice
- Live coding assistant
- PPT generation via voice
- Three modes: Assistant, Agent, Focus
- Electron desktop app with installer (.exe)
- React + TypeScript frontend
- Python backend with bridge server
- SQLite database for session history
- Secure API key storage

### Architecture
- `main.py` — entry point
- `aura_backend.py` — core AI brain
- `bridge_server.py` — frontend ↔ backend bridge
- `whatsapp.py` — WhatsApp automation
- `database.py` — session and history storage
- `security.py` — key isolation and secure storage
- `screen_debug/` — live screen capture system

---

## Upcoming

- [ ] macOS and Linux support
- [ ] Plugin system for custom automations
- [ ] Offline mode with local LLM fallback
- [ ] Memory — AURA remembers your preferences
- [ ] Multi-language support
