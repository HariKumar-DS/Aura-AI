# Architecture

AURA AI is a three-layer system: a React frontend, a Python backend, and a system automation layer — all connected by a WebSocket bridge.

---

## System Overview

```
┌─────────────────────────────────────┐
│         React Frontend              │
│   (UI, voice input, mode toggle)    │
└──────────────┬──────────────────────┘
               │ WebSocket
┌──────────────▼──────────────────────┐
│         Python Backend              │
│  aura_backend.py — the AI brain     │
│  bridge_server.py — WS server       │
└──┬──────────┬──────────┬────────────┘
   │          │          │
   ▼          ▼          ▼
Gemini     System     Database
API        Control    (SQLite)
(TTS +     (files,    (history,
 Vision +   apps,      sessions)
 Reasoning) WhatsApp,
            Email)
               │
┌──────────────▼──────────────────────┐
│         Electron Shell              │
│   (packages everything as a         │
│    native Windows desktop app)      │
└─────────────────────────────────────┘
```

---

## Components

### `main.py`
Entry point. Starts the Python backend and launches the Electron shell.

### `aura_backend.py`
The core AI brain. Receives voice input, determines intent, calls the appropriate tool (Gemini, system, web, etc.), and sends the response back through the bridge.

### `bridge_server.py`
WebSocket server that connects the React frontend to the Python backend. Handles message routing in real time.

### `whatsapp.py`
WhatsApp automation module. Sends messages via voice trigger.

### `database.py`
SQLite-based storage for conversation history and session state.

### `security.py`
Handles API key isolation. Keys are never hardcoded — always loaded from `.env` and stored securely at runtime.

### `screen_debug/`
Live screen capture module. Takes periodic screenshots and sends them to Gemini Vision so AURA can understand what's currently on screen.

---

## Data Flow — Voice Command

```
User speaks
    → Browser microphone captures audio
    → React sends audio/text to bridge_server.py
    → aura_backend.py processes intent
    → Calls Gemini API (reasoning + TTS)
    → Executes system action if needed
    → Sends response audio + text back to React
    → User hears AURA's voice response
```

---

## Frontend Stack

| Tool | Role |
|------|------|
| React + TypeScript | UI components |
| Vite | Build tool |
| Electron | Desktop shell / packaging |
| Web Speech API | Voice input capture |
