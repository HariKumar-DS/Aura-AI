# Automation

AURA AI can automate virtually anything you do with your keyboard and mouse. Here's a full reference.

---

## Communication

### WhatsApp
```
"Send a WhatsApp to [name] — [message]"
"Message Rahul on WhatsApp — I'll be 20 minutes late"
"WhatsApp Mom that I reached home"
```

### Email
```
"Email [person] about [topic]"
"Send an email to my manager with the subject Project Update"
"Reply to the last email from Priya"
```

---

## File Management

```
"Open my Downloads folder"
"Move all PDFs from Desktop to Documents"
"Delete the file called report_draft.docx"
"Rename the folder Projects to Work 2026"
"Show me all files modified today"
```

---

## Apps & System

```
"Open Chrome"
"Close Spotify"
"Take a screenshot"
"Lock the screen"
"Open Task Manager"
"Adjust volume to 50 percent"
```

---

## Web & Search

```
"Search for the best Python libraries for data science"
"What's the weather in Mumbai?"
"Open YouTube"
"Find the GitHub page for FastAPI"
```

---

## Entertainment

```
"Play Kesariya on YouTube"
"Play lo-fi hip hop music"
"Open Netflix"
"Pause the video"
```

---

## Creation

```
"Generate an image of a sunset over mountains"
"Create a 5-slide presentation about renewable energy"
"Write a Python script that reads a CSV and plots a graph"
"Make a PDF report summarizing this folder"
```

---

## Coding Assistant

```
"Write a function to reverse a linked list in Python"
"Explain what this error means: [error text]"
"Refactor this function to be more readable"
"Add comments to this code"
```

---

## Live Screen Vision

```
"What's on my screen right now?"
"Read the text in this window"
"What does this error say?"
"Summarize what's open"
```

AURA uses Gemini Vision to analyze your screen in real time and respond contextually.

---

## Notes

- All destructive actions (delete, move) will ask for confirmation by default
- Disable confirmation in `.env` with `CONFIRM_ACTIONS=false` (not recommended)
- WhatsApp automation requires WhatsApp Web to be open in a browser
