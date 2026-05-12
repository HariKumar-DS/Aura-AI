# Configuration

All configuration is handled through `.env`. Copy `.env.example` to `.env` to get started.

```bash
cp .env.example .env
```

---

## Environment Variables

| Variable | Required | Default | Description |
|----------|----------|---------|-------------|
| `GEMINI_API_KEY` | ✅ Yes | — | Your Google Gemini API key |
| `AURA_MODE` | No | `assistant` | Startup mode: `assistant`, `agent`, or `focus` |
| `SCREEN_CAPTURE` | No | `true` | Enable live screen vision |
| `WHATSAPP_ENABLED` | No | `true` | Enable WhatsApp automation |
| `EMAIL_ENABLED` | No | `true` | Enable email automation |
| `DEBUG` | No | `false` | Verbose logging for development |

---

## Getting a Gemini API Key

1. Go to [Google AI Studio](https://aistudio.google.com)
2. Sign in with your Google account
3. Click **Get API key**
4. Copy the key and paste it into your `.env` file

---

## Security

- Never commit your `.env` file — it's gitignored by default
- Keys are loaded at runtime via `security.py` — they are never stored in memory longer than needed
- AURA does not send your API key anywhere other than directly to Google's Gemini API

---

## Advanced

AURA's backend reads config on startup. If you change `.env` while AURA is running, restart `main.py` for changes to take effect.
