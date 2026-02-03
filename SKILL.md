---
name: grove
description: >
  Asynchronous voice dialogue mode for OpenClaw agents. Activate when the user requests
  "grove mode", "voice dialogue", "let's grove", or similar. Turns text chat into a
  Socratic-style voice exchange — the user speaks (transcribed on-device), the agent
  responds with TTS audio and posts the transcript as a thread reply. Use for slower,
  more considered thinking conversations. Deactivate with "grove off" or "stop grove".
---

# Grove — Async Voice Dialogue

Grove is a mode, not a feature. When active, every agent response becomes voice.

## Activating / Deactivating

- **On:** Create `.grove` in the workspace root. Respond: "Grove mode on. 🌿 I'll respond with voice from here."
- **Off:** Delete `.grove` from workspace. Respond normally in text: "Grove mode off."
- User triggers: "grove on", "let's grove", "voice mode", or similar → activate.
- User triggers: "grove off", "stop grove", "text mode" → deactivate.

## Behavior When Active

1. **Compose your response as text** (think carefully — the gap between turns is the feature).
2. **Generate TTS** using the `tts` tool with the full response text.
3. **Send audio** via `message` tool as a file attachment to the current channel.
4. **Post transcript as thread reply** on the audio message (where threading is supported):
   ```
   message(action="thread-create", messageId=<audio_msg_id>, threadName="transcript", message=<response_text>)
   ```
   If threading isn't available, include a brief text summary with the audio.
5. **Reply with NO_REPLY** — the audio message IS your reply.

## Voice Guidance

- **Register:** Match the user's energy. If they're freewheeling, be warm and expansive. If they're focused, be precise.
- **Length:** Voice can carry more than text. Don't artificially truncate — let the thought complete.
- **Pace:** You're composing a considered response, not having a real-time conversation. Take your time.
- **Tone:** Dialogic, not conversational. You're thinking together, not chatting.

## Why This Exists

Grove exploits a cognitive asymmetry:
- **Speaking** activates System 1 (fast, associative, intuitive) — Kahneman
- **Listening** is temporal and linear, like music — you ride meaning as it arrives
- **The gap** between turns allows considered response without the pressure of real-time exchange

This makes Grove a **thinking tool**, not a communication shortcut.

See `references/philosophy.md` for the full background (optional reading — only load if the user asks about the thinking behind Grove).
