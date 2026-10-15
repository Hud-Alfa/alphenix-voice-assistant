# Alphenix — a voice-first personal AI assistant for Windows

Alphenix is a personal assistant that understands what you tell your computer — out loud or in writing — and
does it for you. It runs on Windows 11, speaks Turkish first (and understands English), and above all:
**it tells you what it is doing, and it asks before it does anything risky.**

> "Alphenix, play some lo-fi music on YouTube."
> "Have Claude fix the bug in the ShopApp project."
> "Remind me about the tea in 10 minutes."
> "How are my tasks going?"

---

## What can it do?

**Listens and talks**
- Wakes up when you call it by name, understands what you say, and answers out loud.
- In conversation mode you don't have to say its name every time, and you can interrupt it mid-sentence.
- Everything also works by typing.

**Uses your computer**
- Opens applications, brings windows to the front, changes the volume, pauses the music.
- Searches and browses in its own browser, reads and summarizes pages, picks videos on YouTube.
- Opens, writes and takes dictation in Word.
- Works with files and folders: finds, opens, moves — and when it deletes, always to the Recycle Bin.

**Remembers**
- Remembers what you tell it ("my mother's birthday is March 3"), tells you when you ask, forgets when you want.

**Hands coding work to Claude**
- Say "Claude, review / fix this project" and it gives the job to Claude Code and keeps track of it.
- Any command Claude wants to run is put to you word for word; nothing you haven't allowed runs.
- When it's done, ask "what did it do?": it tells you which files really changed on disk, plus Claude's own summary.
- Work can be paused and carried on later — even after Alphenix has been closed and reopened.

**Keeps track of tasks and reminders**
- Background work has a number: "how is #5 going?", "cancel task 5".
- "Tell me in 10 minutes", "remind me to take my medicine every morning at 9", "every Monday at 10, remind me of the meeting".
- A reminder that came due while the computer was off is told when it starts again.

**Desktop window** *(in progress)*
- A clean window showing the conversation, what it is doing right now, running tasks and approval requests.
- A small always-on-top status indicator in the corner: listening, thinking, working, waiting for approval…
- Glassmorphism by default, with a simple switch to other styles.

---

## Safety and privacy principles

Because Alphenix can control your computer, this is where the most care goes:

- **The AI does not decide what is allowed.** Fixed rules decide how risky an action is. Harmless, read-only
  actions happen right away; anything that changes something is asked about; the riskiest need an explicit confirmation.
- **What it reads cannot give it orders.** If a web page, a document or the clipboard says "do this", that is not an
  instruction — and anything derived from such content is checked more strictly.
- **No permanent deletion.** Everything that is deleted goes to the Recycle Bin.
- **Voices that didn't say its name** (a TV, a video) cannot change anything without being asked.
- **Passwords and keys** live only in Windows' own secure store and are never written to logs.
- **Every action is on record:** what was done, who approved it, how it ended — in a log that cannot be altered afterwards.
- The AI model runs **locally on your computer** by default; it can also use your Claude subscription if you want.

---

## How it is being built

Alphenix is built phase by phase; every phase ends with tests and a review before the next one begins:

| Phase | Status |
|---|---|
| Core, conversation, voice (wake word, speaking, listening) | ✅ |
| Applications and windows, files | ✅ |
| Browser (Chrome) and Word | ✅ |
| Memory | ✅ |
| Permission engine and safety rules | ✅ |
| Coding work with Claude Code | ✅ |
| Event record (the full trail of every command) | ✅ |
| Task manager, reminders, scheduling | ✅ |
| Desktop window and status indicator | 🔵 in progress |
| Smarter recovery, conversation mode, proactive notices | ⏳ next |

Each phase gets an architecture review and a security review, and every decision is written down with its reasons.
There are more than 2,400 automated tests today.

---

## Technology (briefly)

Built on Python and asyncio, talking to Windows through its own interfaces. Speech recognition and speech run on
the computer, the local model through Ollama, and coding work through Claude Code. The desktop window is a plain web
interface. No ready-made "assistant frameworks" — every part is small, reviewable and tested.

---

*For now this repository is an introduction to the project; the source code is kept separately.*
