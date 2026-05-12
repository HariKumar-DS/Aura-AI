# Security Policy

## Supported Versions

| Version | Supported |
|---------|-----------|
| v0.1.x  | ✅ |

## Reporting a Vulnerability

If you find a security issue in AURA AI — especially related to API key handling, automation abuse, or privilege escalation — please **do not open a public issue**.

Email: *(add your email here)*

Include:
- Description of the vulnerability
- Steps to reproduce
- Potential impact

You'll get a response within 48 hours. If confirmed, a patch will be released promptly.

---

## Security Notes

- API keys are stored locally via `security.py` — never hardcoded
- `.env` is gitignored by default — never commit your keys
- WhatsApp and Email automations require explicit user voice confirmation
- Screen capture runs locally — no data is sent externally except to Gemini API
