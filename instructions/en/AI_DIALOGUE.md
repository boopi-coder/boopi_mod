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
> - In the **game's own dialogues** (quests, Codsworth, Preston, traders, settlers) press **T** and answer in your own words:
>   the AI picks the matching reply of the wheel and the quest goes on as written.
> - Honest limits: no lip sync; a free line in the game's own dialogue does not move the story — only the game's replies do.

## Contents

1. [How it works](#1-how-it-works)
2. [Turn the mode on](#2-turn-the-mode-on)
3. [Start a conversation](#3-start-a-conversation)
4. [How to speak](#4-how-to-speak)
5. [In the game's own dialogues](#5-in-the-games-own-dialogues)
6. [What the person knows](#6-what-the-person-knows)
7. [What the AI can do](#7-what-the-ai-can-do)
8. [What the AI cannot do](#8-what-the-ai-cannot-do)
9. [Limits of the first version](#9-limits-of-the-first-version)
10. [For modders: check a dialogue in AI mode](#10-for-modders-check-a-dialogue-in-ai-mode)
11. [Troubleshooting](#11-troubleshooting)
12. [Other guides](#12-other-guides)

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
| **AI in vanilla dialogues** | **off** / **pick a reply** (default) / **pick a reply and free lines** — your own line in the game's own wheel ([section 5](#5-in-the-games-own-dialogues)) |

### Step 5. The game

The game must be launched through F4SE, and the `BoopiUI.dll` plugin must be installed (the base pack and "OldGenAI — in-game plugin"
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

People with dialogue of their own (the Rocket's bartender, the club staff, the HQ synths, characters with script studio trees)
have **"Say your own…"** in the first wheel of their talk, next to the authored lines. If **E** opens the game's own talk (a
quest, a trader), press **H** in front of the person: the Life wheel opens with the same option.

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
| A ready-made line | Under the line there are 2–4 ideas; **↑/↓** pick one, **Tab** or the digits (while the line is empty) put it in |
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
| `iOwnLine` | "in your own words": in the game's own wheel — your answer; with no menu — a free talk with the person in front (default T = 84) |
| `bPauseWhileTyping` | pause the world while you type |
| `bSuggestions` | reply ideas |
| `bAutoSend` | send the recognised voice at once, without waiting for Enter |
| `bPlayReply` | play the voiced reply (`1` — yes) |
| `sLanguage` | language |
| `iMaxChars` | the length limit of a line (default 400, from 20 to 600) |
| `bSubtitles` | show the reply as a subtitle (the `[HUD]` section) |

---

## 5. In the game's own dialogues

The game's own quest and everyday talks — Codsworth and Preston in the story, Daisy, traders, settlers, DLC people — use their
own wheel: "Yes / No / Sarcastic / Question". In AI mode you can answer in such a wheel in your own words.

1. While the game's wheel is open, press **T**. A line **"In your own words — Name"** appears at the bottom (in the game:
   «Своими словами — Имя»), with the replies the game offers right now under it.
2. Type or say (holding **V**) what you want to answer and press **Enter**.
3. The AI works out which of the replies you mean and picks it — exactly as if you had pressed its key. The screen shows
   **"» reply"**, and the quest goes on just as the game's authors wrote it: the same voice, the same consequences.
4. If none of the replies fits:
   - with **"Pick a reply"** the game says that none fits («Ни один вариант не подходит») — say it differently or choose yourself;
   - with **"Pick a reply and free lines"** the person answers you in character, changing nothing in the story, and the wheel
     stays open.
5. **Esc** — back to the replies: choose as usual.

| Rule | How it works |
|---|---|
| Only what you could press is picked | the AI names just a number from the list of replies the wheel shows; an empty, hidden or unavailable reply is never picked |
| A free line changes nothing | no items, no quest stages, no flags: only the game's own replies move the story |
| The wheel changed meanwhile | the reply is not pressed; the game says «Вариант не выбран: колесо уже другое» ("no reply chosen: the wheel has changed") |
| A reply as it is | type a reply's text (or take it with **Tab**/a digit from the ideas under the line) — it is picked at once, without asking the AI |

The setting is Settings → Dialogues → **AI in vanilla dialogues**: **off**, **pick a reply** (default) or **pick a reply and free
lines**. In the Vanilla mode it is always off: the game does not read the wheel and the AI is never called. The T key is changed in
`BoopiUI.ini` (`iOwnLine`).

> [!TIP]
> You can talk freely with **anyone** in the game, not only the characters of our trees: the same **T** key, with someone in front
> of you and no menu open, starts a free conversation at once — with a settler, a trader, a robot, a DLC person. With a child it
> is ordinary talk only: flirting and anything romantic are always closed. The wheel with **"Say your own…"** still opens on **E**
> (for those without a greeting of their own) and **H**. The AI knows what the game reports about the person (see the next
> section).

---

## 6. What the person knows

Every answer is assembled from what the core has (not from the model's "general knowledge"):

- **Themselves:** the character card, their character and manner of speech; for people from mods — the `ai` block written by the
  author of the tree. For anyone else in the game (a settler, a trader, a raider, a DLC person) — what the game reports: race,
  factions, trade, voice, where they are now.
- **You:** name, sex, looks, level, **S.P.E.C.I.A.L.**, persuasion skill, karma, reputation and fame in this place.
- **The two of you:** the relationship stage, disposition, trust, attraction, the memory of earlier talks (it is written when a
  conversation ends).
- **The story:** started story missions — the stage, the journal entry, what this person is supposed to touch on; story flags.
  And the game's own quests the person is part of right now: the name, the journal entry at this stage and the objectives up to
  it — the texts come from the game's own files (in its language); the AI does not see objectives of later stages.
- **Place and time:** where you are, what time it is, who is nearby.

What the game does not report, the core does not invent.

---

## 7. What the AI can do

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

## 8. What the AI cannot do

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

## 9. Limits of the first version

> [!WARNING]
> This is the first version, and here is honestly what it does not have yet:
>
> - No **lip sync**: the line goes as a subtitle and as voice, but the lips do not move.
> - In the **game's own dialogues** the AI only picks one of the game's replies (or answers without changing anything): it has
>   no outcomes of its own there — items, stages, flags; the story goes on through the game's replies.
> - The AI sees a quest's objectives by the quest's stage (as in the journal), not by the game's own marks: now and then it may
>   know one objective more or less than the Pip-Boy shows.
> - The answer takes a few seconds (network and model); the voice a little longer (speech synthesis).
> - Every line is a request to your AI provider: that is tokens and possibly money; lines and data about the hero and the character
>   go to the provider (a local Ollama model keeps everything on the machine).

---

## 10. For modders: check a dialogue in AI mode

In the Script studio, the **AI dialogue** card of every person has the **Check in AI mode** button — a test chat with the tree as it
is in the editor right now (saved or not), in a save of its own. You pick the kind of talk, the hero, the stage between you, the
level, the caps and the flags that are already set, and talk: below the answers you see which goals and actions fired and what
the core refused. It is the fastest way to see how your `ai` block changes a person's behaviour without starting the game.

<p align="center"><img src="../../docs/images/studio-ai-test-chat.en.png" alt="Script studio: the AI mode test chat with goals and flags under the answers" width="860"></p>

*The "AI mode" test chat: on the left the state (flags, "Start again"), on the right the conversation; under an answer you see the
goals, achievements and flags that fired. The screenshot is in Russian.*

Details — [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md).

---

## 11. Troubleshooting

- **There is no "Say your own…" option.** The "AI" mode is off (Settings → Dialogues), or `BoopiUI.dll`/`BoopiCorp.esp` is not
  installed (check in **Mods**), or the game was launched without F4SE.
- **T does nothing in the game's wheel.** Are the "AI" mode and "AI in vanilla dialogues" on? The game rereads the setting every
  few seconds. The replies must be visible: while the person says their opening line the wheel may still be closed.
- **«Вариант не выбран: колесо уже другое» ("no reply chosen: the wheel has changed").** The talk went on while the AI was
  thinking. Choose yourself or press T again.
- **"No model key is set".** Settings → LLM providers and Routing → Dialogue.
- **"The conversation is lost (the core restarted)".** Start the conversation again.
- **No voice.** Turn on "Voice the replies" and check the voice provider ([VOICE.md](VOICE.md)); in `BoopiUI.ini` set
  `bPlayReply=1`.
- **V does not record.** There is no microphone or speech recognition is not installed; the key can be changed in `BoopiUI.ini`.
- **I write in Russian but Latin letters appear.** Switch the Windows keyboard layout (the input line reads the one that is on
  now). While the line is open, key presses go into it and not into the game's commands: it is a window of its own.

**Logs:**
- the core — `%APPDATA%\BoopiMod\logs\`;
- the plugin — `Documents\My Games\Fallout4\F4SE\BoopiUI.log` (more detail with `bDebug=1`).

> [!TIP]
> **Feedback wanted — report problems and ideas, we'll fix them.** Open an issue at
> [github.com/boopi-coder/boopi_mod/issues/new](https://github.com/boopi-coder/boopi_mod/issues/new) and attach fresh logs.

---

## 12. Other guides

| Guide | What it is about |
|---|---|
| [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md) | Script studio: your own dialogues, the `ai` block, checking in AI mode, voicing, your own mod |
| [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md) | Importing animations and your own scenes in the G.A.M. editor |
| [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) | Animations in mods: gesture and scene, camera, calling from dialogues and scripts |
| [AI_DIALOGUE.md](AI_DIALOGUE.md) | AI dialogue in the game (you are here) |
| [VOICE.md](VOICE.md) | Voicing (TTS) and speech recognition (STT) |

[← All guides](README.md) · [← Project home page](../../README.en.md)
