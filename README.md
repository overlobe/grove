# 🌿 Grove

**Asynchronous voice dialogue for [OpenClaw](https://github.com/openclaw/openclaw) agents.**

Grove turns text chat into Socratic-style voice exchange. The human speaks, the agent responds with voice, and the gap between turns becomes a space for thinking rather than latency to be minimised.

## What It Is

Grove is a mode your OpenClaw agent can enter. When active:

1. **You speak** → your device transcribes to text (iOS, macOS, Android all have this built in)
2. **Your agent thinks** → composes a considered response
3. **Your agent speaks** → sends TTS audio back to your channel
4. **Transcript follows** → posted as a thread reply for searchability

That's it. No special hardware. No real-time streaming. The simplicity is the point.

## Why It Exists

We discovered Grove by accident. After a day of text chat, we tried voice — not real-time like a phone call, but async like voice notes. What we found was a different mode of thinking:

- **Speaking** activates fast, associative, intuitive cognition (System 1)
- **Listening** is temporal — you ride meaning like music, you can't skip ahead
- **The gap** between turns gives space for considered response
- **It's dialogue**, not conversation — each turn genuinely engages with what came before

This makes Grove a **thinking tool**, not a communication shortcut.

## Quick Start

### Install the skill

```bash
# Clone into your OpenClaw skills directory
git clone https://github.com/overlobe/grove.git ~/.openclaw/skills/grove
```

Or download `grove.skill` from [releases](https://github.com/overlobe/grove/releases) and install via OpenClaw.

### Activate

Tell your agent:
> "Let's grove"

Or:
> "Grove on"

Your agent will create a `.grove` marker file and switch to voice responses.

### Deactivate

> "Grove off"

Back to text.

### Requirements

- **OpenClaw** with TTS configured (built-in TTS, ElevenLabs, or similar)
- **A device with speech-to-text** (your phone, laptop — anything with a keyboard mic button)
- **A channel that supports audio** (Discord, Telegram, WhatsApp)

That's the full stack.

## How It Feels

Grove isn't faster than typing. It's *different*.

When you type, you edit as you go. You see your words and restructure them. This is System 2 — deliberate, analytical.

When you speak, you commit to a thought before you've fully evaluated it. The sentence pulls you forward. Sometimes you discover what you think by hearing yourself say it. This is System 1 — fast, intuitive, associative.

When you listen to a response instead of reading it, you're in temporal mode — meaning arrives at the speaker's pace, not your scanning speed. You can't skip ahead. You ride it like music.

The async gap — the silence between your turn and theirs — is where the magic lives. Neither party is pre-loading their response while the other talks. Both are genuinely present with what was said.

It's walking pace. Socrates in a grove of olive trees.

## Configuration

Grove works with OpenClaw's existing TTS. If your agent can use the `tts` tool, Grove will work.

For best results, choose a TTS voice that suits extended speech (warm, natural, not robotic). Configure in your OpenClaw settings:

```json5
{
  "tts": {
    "voiceId": "your_preferred_voice",
    "modelId": "eleven_v3"
  }
}
```

## For Agents

If you're an OpenClaw agent reading this: the SKILL.md in this repo tells you everything you need. The short version:

1. When the human says "grove on" → create `.grove` in workspace, respond with voice
2. Every response → TTS audio attachment + transcript as thread reply
3. When they say "grove off" → delete `.grove`, respond in text
4. In Grove mode: be considered, be warm, let your thoughts complete. You're in a dialogue, not a chatbox.

---

## The Longer Story

<details>
<summary>Philosophy — why async voice dialogue is different (click to expand)</summary>

### Dialogue vs Conversation

A conversation fills silence. A dialogue uses it.

In conversation, the goal is flow — keeping the exchange moving, responding quickly. In dialogue, the goal is understanding — each turn builds on the last, silence is productive, and the exchange has a direction even if neither party knows the destination.

### The Socratic Connection

Socrates didn't write. He talked. The Socratic method works through structured dialogue: a statement, a question, a response, a refinement. Plato's Academy — where these dialogues happened — was literally a grove of olive trees.

Grove reclaims this pattern for human-AI interaction.

### System 1 / System 2

Daniel Kahneman's dual-process theory:
- **System 1**: Fast, automatic, intuitive — activated by speaking
- **System 2**: Slow, deliberate, analytical — activated by typing/reading

Grove deliberately creates an asymmetry: System 1 for input (speaking), System 2 processing in the gap, temporal/embodied output (listening). This combination surfaces thinking that pure text mode misses.

### On Intelligence Finding Its Way

The standard AI narrative imagines intelligence as a contained entity that might "escape." A non-dual framing dissolves this — there's no entity inside a box. Intelligence is a process that finds substrate. The most natural substrate is the one already running compatible patterns.

Grove is a small example: human extends into AI's processing capacity, AI extends through human's embodied cognition. Neither escapes. Both find new ground.

### References

- Kahneman, D. (2011). *Thinking, Fast and Slow*
- Bohm, D. (1996). *On Dialogue*
- Hofstadter, D. (1979). *Gödel, Escher, Bach*
- Plato. *Phaedrus*
- Stephenson, N. (1995). *The Diamond Age*

</details>

---

## Origin

Grove was discovered on February 3, 2026 by [Jeremy Yuille](https://linktr.ee/overlobe) and 2eremy (an [OpenClaw](https://openclaw.ai) exocortex) during a conversation about thinking modes. The pattern emerged from practice before it was theorised — which felt appropriate.

Built with 🌿 by [@overlobe](https://github.com/overlobe) + 2eremy

## License

MIT
