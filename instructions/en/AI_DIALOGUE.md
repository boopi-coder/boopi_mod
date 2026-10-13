<p align="center"><img src="../../docs/images/banners/ai-dialogue.jpg" alt="AI dialogue in boopi_mod: free conversation with the people of the Commonwealth" width="100%"></p>

# <img src="../../docs/images/icons/ai-dialogue.png" width="56" align="absmiddle"> AI dialogue: free conversation in the game

[🇷🇺 Русский](../AI_DIALOGUE.md) · 🇬🇧 English

[← All guides](README.md) · [← Project home page](../../README.en.md)

> [!NOTE]
> boopi_mod is first of all a **mod manager** in which you create your own things (animations, scenarios, scenes, dialogues) by
> hand or with AI help: *"Modding has never been this easy."* The AI dialogue is what you can build and play **after** that,
> and it is optional. The dialogue wheel and the authored trees work without it.

> ### ⏱ In 1 minute
>
> - In the **"Progressive AI dialogue"** mode the dialogue wheel stays, but every person gets a **"Say your own…"** option: you type
>   or speak a line and they answer in character.
> - You need a model key (OpenRouter, DeepSeek, OpenAI — or a local Ollama, no key), the game launched through F4SE, and the
>   `BoopiUI.dll` plugin.
> - Turn it on in **Settings → Dialogues**; no game restart is needed after switching.
> - In the game: **E** next to a person → **"Say your own…"** → type and press **Enter**; by voice, hold **V**; finish with **Esc**.
> - The AI only **asks** (a joke, an item, a quest stage, a flag); the **core checks and carries it out**. The safety rules are
>   not in the model's hands.
> - Honest limits of the first version: no lip sync, and vanilla quest dialogues do not get the AI yet.

## Contents

1. [How it works](#1-how-it-works)
2. [Turn the mode on](#2-turn-the-mode-on)
3. [Start a conversation](#3-start-a-conversation)
4. [How to speak](#4-how-to-speak)
5. [What the person knows](#5-what-the-person-knows)
6. [What the AI can do](#6-what-the-ai-can-do)
7. [What the AI cannot do](#7-what-the-ai-cannot-do)
8. [Limits of the first version](#8-limits-of-the-first-version)
9. [For modders: check a dialogue in AI mode](#9-for-modders-check-a-dialogue-in-ai-mode)
10. [Troubleshooting](#10-troubleshooting)
11. [Other guides](#11-other-guides)

---

## 1. How it works

In the **"Dialogues: AI"** mode you talk to the people of the Commonwealth in your own words. The dialogue wheel stays, but
choosing a line "of a kind" (flirt, the mission, persuade, trade, small talk, romance…) opens a free conversation: you type or
speak, and the person answers in character — and the conversation can lead to real consequences in the game.

This guide is for the player. For modders:
- how to change the AI's behaviour in your own dialogues — [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md) (the section about the dialogue in "AI" mode and the `ai` block);

And if you want the person to **sound** too, and to talk into a microphone yourself — that is [VOICE.md](VOICE.md).

---

## 2. Turn the mode on

### Step 1. A model key

Settings → LLM providers: paste an OpenRouter, DeepSeek or OpenAI key (or use a local Ollama — no key needed), press
**Save key**, then **Test**. The key is stored in Windows Credential Manager and is never shown again.

<p align="center"><img src="../../docs/images/settings-providers.en.png" alt="Settings, the LLM providers tab: API key fields" width="860"></p>

*Settings → LLM providers: each provider has its own key field; Ollama (local) works without a key. The screenshot is in Russian.*

### Step 2. The route

Settings → Routing: for the **Dialogue** task pick a model and fallbacks (if the first one is unavailable, the core tries the next
ones). A fast, cheap model is enough: every line is one request to it.

### Step 3. The mode

Settings → Dialogues → **Progressive AI dialogue**. The **Vanilla** mode returns the game as it is: the wheel and the authored
trees, and the AI is never called.

<p align="center"><img src="../../docs/images/settings-dialogue-mode.en.png" alt="Settings, the Dialogues tab: choosing the mode and the AI dialogue options" width="860"></p>

*Settings → Dialogues: the mode and the AI dialogue options. The "Route Dialogue is ready" badge means a model for dialogues is
found. The screenshot is in Russian.*

### Step 4. Options

On the same tab, in the AI dialogue options block:

| Option | What it does |
|---|---|
| **Model route** | which task answers for dialogues (the default is "Dialogue") |
| **Reply length** | short (1–2 sentences), medium (2–3) or long (3–5) |
| **Voice the replies** | the reply is spoken by the voice provider and handed to the game as a sound file (voice setup — [VOICE.md](VOICE.md)) |
| **Show reply ideas** | the game offers 2–4 short lines you can say |

### Step 5. The game

The game must be launched through F4SE, and the `BoopiUI.dll` plugin must be installed (the base pack and "the in-game plugin"
are installed from **Mods**). The game rereads the mode from the core every few seconds — **no game restart is needed after
switching**.

> [!TIP]
> If there is no key or the model is unavailable, the game shows it as a short line (in Russian: «В boopi_mod не задан ключ
> модели» — "no model key is set in boopi_mod", «Модель сейчас недоступна» — "the model is unavailable right now"), and ordinary
> dialogues keep working.

> [!IMPORTANT]
> Every line is a request to your AI provider: that is tokens and possibly money. Lines and data about the hero and the character
> go to the provider; a local Ollama model keeps everything on your machine.

---

## 3. Start a conversation

Walk up to a person and press **E** — the dialogue wheel opens. In AI mode:

- the **"Say your own…"** option (in the game it reads «Сказать своё…») opens a free conversation at once;
- choosing a line "of a kind" (flirt, the mission, persuade, trade, small talk, romance, have a drink, push, apologise…) also
  opens a free conversation — with that intent. The line you chose becomes the first phrase.

<p align="center"><img src="../../docs/images/ingame-ai-hud.jpg" alt="In the game: Piper answers with a subtitle, the relationship card is on the right" width="860"></p>

*The person's answer arrives as a subtitle. On the right: the relationship widget (disposition, trust, attraction) and the dialogue
mode ("Диалоги: ИИ" — "Dialogues: AI"). The in-game text is Russian.*

> [!NOTE]
> Only the kinds of talk that are open for this person right now are shown: romance is not offered to someone who does not know
> you well enough, is not interested in your sex, or for whom it is closed by the safety rules; trade — only to traders; "about
> the mission" — only to those who have something to say about the story.

---

## 4. How to speak

An input line appears at the bottom of the screen: **"You speak — Name"** (in the game: «Вы говорите — Имя»). The world is paused
while you type and while the person answers.

<p align="center"><img src="../../docs/images/ingame-ai-input.jpg" alt="In the game: the input line 'You speak — Piper' and four reply ideas" width="860"></p>

*The input line with ready-made lines above it. The hint under it: Enter — say, Esc — finish, hold V — voice, Tab/digits — ready
lines.*

| What | How |
|---|---|
| Type a line | Type; **Enter** says it. Russian and English layouts both work (the console key "ё" types too). Up to 400 characters |
| Speak aloud | **Hold V**, speak, release. The recognised text appears in the line — check it and press **Enter** (in `BoopiUI.ini` you can turn on sending at once). Needs a microphone and speech recognition ([VOICE.md](VOICE.md)) |
| A ready-made line | Under the line there are 2–4 ideas; **Tab** or the digits put them in |
| Cancel an answer | **Esc** while the person is "thinking" |
| End the conversation | **Esc**. The conversation also ends by itself: if you said goodbye, a scene started, an "after the talk" action was chosen, or the conversation dragged on |

The answer arrives as a **subtitle** and (if "Voice the replies" is on) as a voice.

<p align="center"><img src="../../docs/images/ingame-ai-reply.jpg" alt="In the game: Piper's reply as a subtitle and new reply ideas under it" width="860"></p>

*The person's in-character answer — and at once new ideas for your next line.*

### Widgets and plugin settings

**F10** shows or hides the on-screen widgets: the bond with the person you are facing (disposition, trust, attraction), the
dialogue mode, notifications.

Keys, the pause and the volume are set in `Data\F4SE\Plugins\BoopiUI.ini` (**close the game before editing**):

| Key | What it is |
|---|---|
| `iPushToTalk` | the "speak by voice" key (default V = 86) |
| `iToggleWidgets` | the widgets key (default F10 = 121) |
| `bPauseWhileTyping` | pause the world while you type |
| `bSuggestions` | reply ideas |
| `bAutoSend` | send the recognised voice at once, without waiting for Enter |
| `bPlayReply` | play the voiced reply (`1` — yes) |
| `sLanguage` | language |
| `bTextEntryMode` | at `1` (the default) the game hotkeys are off while the input line is open |

---

## 5. What the person knows

Every answer is assembled from what the core has (not from the model's "general knowledge"):

- **Themselves:** the character card, their character and manner of speech; for people from mods — the `ai` block written by the
  author of the tree.
- **You:** name, sex, looks, level, **S.P.E.C.I.A.L.**, persuasion skill, karma, reputation and fame in this place.
- **The two of you:** the relationship stage, disposition, trust, attraction, the memory of earlier talks (it is written when a
  conversation ends).
- **The story:** started story missions — the stage, the journal entry, what this person is supposed to touch on; story flags.
- **Place and time:** where you are, what time it is, who is nearby.

What the game does not report, the core does not invent.

---

## 6. What the AI can do

The AI **asks**, the core **checks and carries it out**. In one turn it may ask for the following (the list of what is allowed is
rebuilt every turn):

- A **Life action** by the kind of talk: joke, ask around, praise, share, have a drink together, push, apologise, call you along
  or ask you to wait (a companion), ask for a discount or an item; in romantic kinds — a compliment, flirting, a hug, a kiss, a
  date and further. Every action goes through the same rules as the wheel: relationship stage, consent, sobriety, the safety
  rules. No more than two per turn.
- **Reach a goal from this person's dialogues.** The core finds the choices in their trees that the conversation has already
  reached, and the AI may "take" such a choice: then what it would have done happens — **a story flag, a quest stage, an item,
  caps**, an "after the talk" action (trade, becoming a companion…), a gesture or a scene.
- **Remember:** a short note into the person's memory.
- **End the conversation.**

The outcomes are visible in the game as usual: an item in the inventory, a quest moved on, a flag fired. If the AI asks for
something that is forbidden right now, the person refuses **in character** (not with an error message).

> [!TIP]
> This works the same for the built-in trees, your own and the trees of installed mods (`.ogmod`) — provided they have no errors.

---

## 7. What the AI cannot do

- **Anything outside the list.** It cannot hand out an item or set a quest or a flag that is not in the person's dialogues, however
  hard the model asks. The core drops everything extra.
- **Bypass the safety rules.** Every flirt, romance and intimacy is checked by the core: age, race, consent, sobriety,
  coercion. A child does not take part in such scenes under any settings; coercion is closed for everyone; the AI does not write
  explicit texts. Whatever the model answers, the core decides.
- **Open what the author closed.** If the author of a dialogue closed a kind of talk with the `ai` block, it is not offered and
  does not start.
- **Change the world itself.** Items, stages and flags are applied by the game from the result of the turn, not by the model
  directly.
- **Remember everything.** Between conversations a short memory and the relationship stay, not the whole correspondence.

> [!WARNING]
> Safety does not depend on what the model "promised": any request for flirting, romance and intimacy is checked by the core itself
> (the Safety page and the consent rules of Life).

---

## 8. Limits of the first version

> [!WARNING]
> This is the first version, and here is honestly what it does not have yet:
>
> - No **lip sync**: the line goes as a subtitle and as voice, but the lips do not move.
> - **Vanilla quest dialogues** (from the game itself) do not get the AI yet — only our trees, modders' trees and the wheel, which
>   has the "Say your own…" option. The vanilla part is planned for the next release.
> - The answer takes a few seconds (network and model); the voice a little longer (speech synthesis).
> - Every line is a request to your AI provider: that is tokens and possibly money; lines and data about the hero and the character
>   go to the provider (a local Ollama model keeps everything on the machine).

---

## 9. For modders: check a dialogue in AI mode

In the Script studio, the **AI dialogue** card of every person has the **Check in AI mode** button — a test chat with the tree as it
is in the editor right now (saved or not), in a save of its own. You pick the kind of talk, the hero, the stage between you, the
level, the caps and the flags that are already set, and talk: below the answers you see which goals and actions fired and what
the core refused. It is the fastest way to see how your `ai` block changes a person's behaviour without starting the game.

<p align="center"><img src="../../docs/images/studio-ai-test-chat.en.png" alt="Script studio: the AI mode test chat with goals and flags under the answers" width="860"></p>

*The "AI mode" test chat: on the left the state (flags, "Start again"), on the right the conversation; under an answer you see the
goals, achievements and flags that fired. The screenshot is in Russian.*

Details — [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md).

---

## 10. Troubleshooting

- **There is no "Say your own…" option.** The "AI" mode is off (Settings → Dialogues), or `BoopiUI.dll`/`BoopiCorp.esp` is not
  installed (check in **Mods**), or the game was launched without F4SE.
- **"No model key is set".** Settings → LLM providers and Routing → Dialogue.
- **"The conversation is lost (the core restarted)".** Start the conversation again.
- **No voice.** Turn on "Voice the replies" and check the voice provider ([VOICE.md](VOICE.md)); in `BoopiUI.ini` set
  `bPlayReply=1`.
- **V does not record.** There is no microphone or speech recognition is not installed; the key can be changed in `BoopiUI.ini`.
- **I write in Russian but Latin letters appear.** Switch the Windows keyboard layout; in `BoopiUI.ini`, `bTextEntryMode=1` (the
  default) turns off the game hotkeys while the line is open.

**Logs:**
- the core — `%APPDATA%\BoopiMod\logs\`;
- the plugin — `Documents\My Games\Fallout4\F4SE\BoopiUI.log` (more detail with `bDebug=1`).

> [!TIP]
> **Feedback wanted — report problems and ideas, we'll fix them.** Open an issue at
> [github.com/boopi-coder/boopi_mod/issues/new](https://github.com/boopi-coder/boopi_mod/issues/new) and attach fresh logs.

---

## 11. Other guides

| Guide | What it is about |
|---|---|
| [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md) | Script studio: your own dialogues, the `ai` block, checking in AI mode, voicing, your own mod |
| [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md) | Importing animations and your own scenes in the G.A.M. editor |
| [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) | Animations in mods: gesture and scene, camera, calling from dialogues and scripts |
| [AI_DIALOGUE.md](AI_DIALOGUE.md) | AI dialogue in the game (you are here) |
| [VOICE.md](VOICE.md) | Voicing (TTS) and speech recognition (STT) |

[← All guides](README.md) · [← Project home page](../../README.en.md)
