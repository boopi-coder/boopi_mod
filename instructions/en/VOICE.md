<p align="center"><img src="../../docs/images/banners/studio.jpg" alt="Voice in boopi_mod: voicing and speech recognition" width="100%"></p>

# <img src="../../docs/images/icons/voice.png" width="56" align="absmiddle"> Voice: voicing (TTS) and speech recognition (STT)

[🇷🇺 Русский](../VOICE.md) · 🇬🇧 English

[← All guides](README.md) · [← Project home page](../../README.en.md)

> [!NOTE]
> boopi_mod is first of all a **mod manager**: *"Modding has never been this easy."* Voice is a nice addition to what you create in
> it: dialogues in the app and in the game can **sound**, and you can **speak** into a microphone. Everything is optional and
> turned on at your wish.

> ### ⏱ In 1 minute
>
> - **Voicing (TTS)** decides who speaks the lines: online (Edge TTS, ElevenLabs, OpenAI, Higgs TTS 3) or local (XTTS-v2,
>   Silero, **Qwen3-TTS** and **Higgs TTS 3 on your graphics card** — one button, or on your own server). Qwen3-TTS
>   (Apache-2.0) is the recommended engine for "This PC" and for real-time replies.
> - An AI reply in the game sounds **at once**: the first syllables come within a fraction of a second while the rest is still
>   being voiced (2.4).
> - The lines of "Lullaby", Boopi Corp., the club and the Red Rocket can be heard **in Russian and in English** — voiced (2.8).
> - The easiest start is **Microsoft Edge TTS**: free, no key, Russian voices Dmitry and Svetlana.
> - Choose the provider: Settings → LLM providers → the "Text to speech (TTS)" block → **Use for voicing**.
> - **Speech recognition (STT)** — Settings → Voice: built in (faster-whisper) or OpenAI Whisper; in the game, hold **V**.
> - Local engines are not part of the app: they are installed by the **Install** button and work offline. XTTS-v2 and
>   Qwen3-TTS can **clone a voice**; Qwen3-TTS already has built-in voices that sound like the hero and the game's people (2.6).
>   Higgs TTS 3 clones too (2.7) — it has a research and non-commercial licence.
> - XTTS-v2 and Silero have **non-commercial** licences, so they are installed only after your explicit consent.
> - **Lip sync**: whatever is voiced — an AI reply in the game or a line of your studio mod — moves the speaker's lips with the
>   voice. It is boopi_mod's own: nothing to install, no `.lip` files to make.

## Contents

1. [Where voice is used](#1-where-voice-is-used)
2. [Voicing (TTS)](#2-voicing-tts)
3. [Voice cloning (XTTS-v2, Qwen3-TTS, Higgs TTS 3)](#3-voice-cloning-xtts-v2-qwen3-tts-higgs-tts-3)
4. [Speech recognition (STT)](#4-speech-recognition-stt)
5. [Troubleshooting](#5-troubleshooting)
6. [Other guides](#6-other-guides)

---

## 1. Where voice is used

Voice in boopi_mod is used in three places:

- **the chat with a character** in the app — the answers can be voiced;
- **the AI dialogue in the game** ([AI_DIALOGUE.md](AI_DIALOGUE.md)) — the person's answer sounds, and you can speak yourself by holding **V**;
- **the Script studio** — **Voice all** says every line of a dialogue with each speaker's voice, "Voice with AI" says one line
  ([SCRIPT_STUDIO.md](SCRIPT_STUDIO.md), the section about voicing lines).

Nothing heavy ships with the app: online services connect with a key, local engines are installed by a button into the folder
`%APPDATA%\BoopiMod\speech\` and work without a network.

---

## 2. Voicing (TTS)

Settings → LLM providers → the **"Text to speech (TTS)"** block. The provider that has **Use for voicing** set does the voicing.

### 2.1 Choose a provider

| Provider | Where it runs | What you need | Notes |
|---|---|---|---|
| **Microsoft Edge TTS** | online | nothing (no key), internet | Free, Russian voices Dmitry and Svetlana; speed is adjustable in percent. A good start |
| **ElevenLabs** | online | an API key | Voices and models come from your account (Multilingual v2, Turbo, Flash, v3); streaming output |
| **OpenAI TTS** | online | the same key as the OpenAI provider | Models gpt-4o-mini-tts, tts-1, tts-1-hd |
| **Qwen3-TTS** | locally on your NVIDIA card or on your own server | "This PC": "Install" (about 8.5 GB: the environment and the weights), an NVIDIA card with ~7 GB of free memory; your own server: its address | An open model (Apache-2.0). Built-in designed voices (our characters and voices that sound like the game's people) and **voice cloning** from a sample with its text; Russian, English and 8 more languages; on this PC a reply sounds in parts, at once (2.6). The recommended local engine |
| **Higgs TTS 3** | locally on your NVIDIA card, Boson cloud or your own server | "This PC": nothing (a ~12 GB card); a Boson AI key or your server's address | Preset voices and **voice cloning** from a sample with its text; about a hundred languages; on this PC a reply sounds in parts, at once (2.7). A research and non-commercial licence |
| **XTTS-v2** | local | "Install" (about 4.7 GB), accept the licence | The best quality and **voice cloning**; an NVIDIA graphics card (CUDA) is desirable |
| **Silero TTS** | local | "Install" (about 280 MB), accept the licence | Russian voices, light |

### 2.2 Connect it

1. For an online service paste the key (**Save key**; it is stored in Windows Credential Manager) and press **Check**. Edge TTS
   needs no key.

   <p align="center"><img src="../../docs/images/settings-providers.en.png" alt="Settings, providers: the LLM provider cards and the Text to speech block with ElevenLabs, OpenAI TTS and Microsoft Edge TTS" width="860"></p>

   *Settings → LLM providers: provider keys at the top, the "Text to speech (TTS)" block below. Microsoft Edge TTS is marked "In
   use" — it needs no key. The screenshot is in Russian.*

2. For a local engine press **Install**. The app creates the environment and downloads the model itself; progress is shown. For XTTS
   pick the graphics card ("Auto (CUDA if there is an NVIDIA card)", "CPU only", "Force CUDA") and tick the licence box.

   <p align="center"><img src="../../docs/images/settings-voice-tts.en.png" alt="Settings, voicing providers: XTTS-v2 and Silero TTS with Install buttons and the XTTS voices block" width="860"></p>

   *The local engines XTTS-v2 and Silero TTS: Install, the graphics card choice and the licence box for XTTS, the "XTTS
   voices (cloning)" block. The screenshot is in Russian.*

3. Pick the default voice for Russian and English and press **Listen**.
4. Tick **Use for voicing** — and this provider voices everyone.

> [!IMPORTANT]
> **Engine licences.** XTTS-v2 is distributed under the Coqui Public Model License, Silero under CC BY-NC-SA 4.0: both are
> **non-commercial**. That is why they are not in the archive and are installed only after your explicit consent; Edge TTS,
> Whisper and Qwen3-TTS (Apache-2.0, commercial use allowed) have no such restrictions.

### 2.3 A particular character's voice

Characters → the character → **Profile**: the voice card shows the fields of the chosen provider (ElevenLabs voice, OpenAI voice,
Edge voice, Silero speaker, XTTS speaker, Qwen3-TTS voice, Higgs voice). Choose and press **Listen** — the choice is saved in your layer of
edits. If nothing is chosen for the character, the default voice for the language from the provider settings is used (Qwen3-TTS
first looks for the voice that sounds like the character's game voice type, 2.6).

### 2.4 Voicing in the chat and in the game

- **The chat in the app:** the **Voice the replies** box above the input field (or Settings → Voice → "Voice the replies in the chat");
  a single reply can be voiced with the **Listen** button next to the character's name.
- **The AI dialogue in the game:** Settings → Dialogues → **Voice the replies**. The core gets the answer and voices it **in
  parts**: the first part (with Qwen3-TTS on this PC the first 0.24 s of speech; once the server is loaded, the first sound is
  ready about 0.45–0.5 s after the request; with Higgs TTS 3 on this PC a third of a second of speech, ready about 0.5–0.7 s
  after the reply) goes to the game at once and plays while the next ones are still being made;
  the game queues the parts back to back without a gap (not positional), each with its own lip movement from the very
  moment it starts (2.5). With other providers a part is a sentence: the first one plays while the rest are voiced.
- **WAV sample rate for the game** — 44100 Hz (like the game's lines) or 22050 Hz (half the size). Always mono, 16 bit — that is
  what the studio's voice build expects.

### 2.5 Lip sync

When a voiced line plays in the game, the lips of whoever says it move with the voice:

- **an AI reply** (the AI dialogue, also a free reply in the game's own wheel) — from the moment its sound starts;
- **a line of your studio mod** with a WAV recording (voiced by "Voice all", by "Voice with AI" or recorded by you) — when the
  line begins.

How it works — all of it boopi_mod's own, nothing to install or to make by hand:

1. boopi_mod listens to the recording: where the voice is loud or quiet, where it hisses (s, sh), which vowel it is (a, e, i, o, u
   by the voice's formants).
2. With the text of the line known, its letters (Russian or English) become mouth shapes — closed lips for m, b, p, the lower lip
   for f, v, round lips for o, u, a wide mouth for i, e, the tongue for t, d, l — spread over the time that is actually spoken. If the
   built-in speech recognition (faster-whisper) is installed, the studio also stores the time of every word next to the recording,
   and the words land exactly where they are said.
3. The sounds flow into each other as a living person's do: neighbouring shapes blend (the "t" of "two" is already round - the
   lips get ready for the "oo"), closed lips for m, b, p always meet, even on the briefest sound, and a sound said in an instant
   is only hinted - the mouth does not twitch. The jaw and the lips move at a natural speed, without jitter.
4. The face talks along: the line's emotion (an AI reply's - the one the AI chose; a studio line's - its "Face" field) comes with
   the line and leaves at its end; the loudest syllables lift the brows (an angry person knits them), the brows rise towards the
   end of a question, and the person blinks in the pauses between phrases. Where the face and the lips share the mouth (a smile
   and an "oo"), the lips win.
5. All of it is weights of the face's own morphs (jaw, lips, tongue, brows, lids, cheeks) thirty times a second; `BoopiUI.dll`
   plays them on the speaker's face in the game on top of the person's own expression and blinking.

The curves (how much the sounds blend, the speed of the lips, the emotions' faces, the blinks) live in
`data/speech/lipsync.yaml` - they can be tuned without programming.

> [!NOTE]
> A `.lip` file of your own (made in the Creation Kit or elsewhere) is still welcome but no longer needed: if one lies next to a
> recording, the game uses it instead. A ready **FUZ** carries its own lip sync. Only an **XWM** without a `.lip` keeps the lips still.

Switch it off: `Data\F4SE\Plugins\BoopiUI.ini` → `[Audio]` → `bLipSync=0`.

**A studio line's face.** A greeting, a reply and a hero's choice have a **"Face"** picker next to their voice: calm, warm,
happy, amused, flirty, shy, nervous, sad, angry, afraid, annoyed, suspicious, serious, surprised, disgusted. "From the text"
(the default) lets the face follow the line by itself: a question lifts the brows, so do the loud syllables. In the tree file
it is the line's `emotion:`. The face shows on lines with a WAV recording (our lip sync plays those).

### 2.6 Qwen3-TTS: your own model on this PC

**Qwen3-TTS** is an open voicing model by the Qwen team (the weights `Qwen/Qwen3-TTS-12Hz-1.7B-Base`). Its licence is
**Apache-2.0**: commercial use is allowed and there is no licence box to tick. It is **the recommended engine** for "This
PC" and for real-time replies; Higgs TTS 3 is also available (2.7). The model speaks **from a sample** — a short,
clean recording of a voice and its exact text. The same sample speaks Russian, English and eight more languages (German,
French, Spanish, Italian, Portuguese, Japanese, Korean, Chinese): Whisper understands the Russian made from those samples
almost without a mistake. There are no service preset voices and no emotion tags: a voice is always a sample.

The **Qwen3-TTS** card has two options:

- **This PC** (the default) — the model on your NVIDIA graphics card, **offline and without a key**. Press **Install**: the
  engine's environment (PyTorch with CUDA and the `qwen-tts` package) is set up, then the weights (~4.5 GB) are downloaded
  from Hugging Face. If you already have the weights (another program downloaded them), point to their folder when you
  install or later — **Take from the folder**: the files are hard-linked, not copied, and take no space a second time; a
  Hugging Face cache folder works too.
  The core starts the model's server by itself with the first line (loading takes ~5–15 s when the model's files were read
  from the disk recently; **Start** does it in advance) and stops it after 30 minutes of nothing to do and when the core
  exits. **Graphics cards**: "One card" (the one with the most free memory), "All cards" — a server on each card, the lines
  are shared between them — or the cards you pick. A server takes ~7 GB of video memory. Advanced → **Lines at once per
  card** is how many lines one server says at the same time: more is faster for the studio's bulk voicing but needs more
  memory.
- **Own server** — Qwen3-TTS on your computer or your network with an OpenAI-like `POST <address>/v1/audio/speech` that
  takes a voice sample (`ref_audio` + `ref_text`) and the language (`language`). Enter the address (for example
  `http://127.0.0.1:8095`) and press **Save address**; the model may stay empty (the server's own is used), a key only if
  the server asks for one (it is kept only in Windows Credential Manager).

The **Test** button really voices a short phrase, so you see at once that the model and the address are fine.

**Voices.** The Qwen3-TTS voice list has two kinds:

- **Designed voices** `designed:<name>` ship with the app (`data/speech/voices/designed`). They are our own characters (the
  Boopi synths, the club's and the Red Rocket's people, Nora, the core's voice, the story's new NPCs — 51 voices) and **33
  voices that sound like the game's people**: the hero (male and female), Nick Valentine, Piper, Codsworth, Preston, X6-88,
  Deacon, Virgil, Shaun, McDonough, Geneva and the rest. Each was made from a text description of the character with
  Qwen3-TTS VoiceDesign: a similar age, timbre, accent and attitude, but a voice of its own — **never made from the game's
  audio**. The descriptions are in `data/speech/voices/designed.yaml`.
- **Clones** `clone:<name>` are your own samples (section 3): your recording, or a sample cut from your own game for your
  personal use.

**Which voice speaks a person.** The voice picked in the studio; else the character card's "Qwen3-TTS voice"; else the
person's designed voice — the one their bundled lines are voiced with, or, when they have none, the voice that sounds like
their game voice type (the hero: of the hero's sex); else your own sample of their voice type; else the default voice
(`designed:nora`).

**Speed** (RTX 2080 Ti, approximate figures). An AI reply is voiced in parts: the first part is 3 audio frames (0.24 s of
speech); once the server is loaded, the first sound is ready about 0.45–0.5 s after the request, and the next parts are made
while it plays. The model's codec is causal, so a part never waits for what follows, and the card computes each frame of all
the server's lines as one pre-recorded pass. Bulk voicing in the studio: 16 lines at once per card, about 13–17 times faster
than real time.

> [!IMPORTANT]
> **The Qwen3-TTS licence.** The weights are open under Apache-2.0 — nothing to accept, commercial use allowed. Clone only the
> voices you have the right to. boopi_mod does not distribute the model: it is downloaded to your computer from Hugging Face.

### 2.7 Higgs TTS 3 (Boson AI)

**Higgs TTS 3** is Boson AI's voicing model: preset voices, **cloning from a sample** (a 5–30 second recording and, optionally,
its text — the voice comes out closer with it) and about a hundred languages. You may voice your own mods and characters with
it — under its licence and on your own responsibility. The **Higgs TTS 3** card has three options:

- **Boson cloud** — voicing goes through `api.boson.ai`. Paste your own Boson AI key and press **Save key**: it is kept only in
  Windows Credential Manager, never in a file. Preset voices: Oliver, Marcus, Jake, Chloe, Eleanor, Nora. It works under your
  own Boson terms (a new account first claims its trial credit).
- **Own server** — the open model `bosonai/higgs-tts-3-4b` on your computer or your network under **vLLM-Omni** or
  **SGLang-Omni** (an OpenAI-compatible `/v1/audio/speech`). Enter the address (for example `http://127.0.0.1:8095`) and press
  **Save address**; the model may stay empty (the server's own is used), a key only if the server asks for one. "How the voice
  sample is sent": `ref_audio` for vLLM-Omni (as Boson does), `references` for SGLang-Omni on the same computer (the sample goes
  into a temporary file the server reads itself).

- **This PC** — the open model on your NVIDIA graphics card, **offline and without a key**, like XTTS-v2. It needs a card
  with about 12 GB of video memory (a 22 GB 2080 Ti has room to spare). Tick the licence and press **Install**: the
  environment (~3.6 GB) is set up, then the weights `bosonai/higgs-tts-3-4b` (~9.3 GB) are downloaded. If you already have
  the weights (another program downloaded them), point to their folder — **Take from the folder**: the files are linked, not
  copied, and take no space a second time. The model's server starts by itself with the first line (loading takes ~0.5–2
  minutes; **Start** does it in advance) and stops after 30 minutes of nothing to do. **All GPUs** runs a server on each card
  and shares the lines between them (useful when the studio voices many lines); "lines at once per card" is how many lines
  one card says at the same time. Speed on an RTX 2080 Ti: one line faster than real time (~0.6–0.7 s of work per second of
  speech), an AI reply's first sound after ~0.5–0.7 s; many lines at once 7–9 times faster than real time per card.

The **Test** button really voices a short phrase, so you see at once that the key, address and model are fine. The default voice
for the language is in the list below; the clones `clone:<name>` are there too — the same samples XTTS and Qwen3-TTS use
(section 3). An AI reply's emotion (warm, sad, angry…) goes to Higgs as its own tag, and the voice carries that feeling.

> [!IMPORTANT]
> **The Higgs TTS 3 licence.** The open model is for research and non-commercial use only (Boson Higgs TTS 3 Research and
> Non-Commercial License). Clone only the voices you have the right to. The cloud API is under your own Boson terms. boopi_mod
> distributes none of it: the model and the key are yours.

### 2.8 "Lullaby" voiced

The lines of the boopi_mod dialogue trees — the "Lullaby" story, Boopi Corp., the Black Acorn club, the Red Rocket and the
story's new lines in the game's own quests — are voiced **in Russian and in English**. The recordings of both languages come in the story's content pack
("Lullaby" — the story, from 0.6.0) and go into the mod by themselves when it is built: in a Russian or English game those
lines sound and move the lips. An update of the pack replaces the recordings as a whole.

- **Every voice is designed** from a description of the character (2.6): our own characters have voices of their own, the
  hero (a take for each sex) and the game's people (Nick, Piper, Codsworth, Shaun, X6-88, Deacon, Virgil…) voices that sound
  like them. Nobody's recordings were cloned and no game audio was used. Who speaks with which voice is in
  `data/speech/voices/cast.yaml` and `designed.yaml`.
- Both languages were voiced locally with Qwen3-TTS. Every voice has two samples, English and **Russian**: the Russian
  one is designed from the same description as a native speaker's voice, with a natural Russian sample text, so the
  Russian lines have no accent (Whisper hears Russian at 0.97+ for every sample).
- When a line in a tree is changed, its recording no longer fits: the line is subtitled again until it is voiced again.

For authors: the voice bank is built by `scripts/voice_bank.py` for `--lang ru` or `--lang en`: `plan` → `say` (local
Qwen3-TTS servers) → `check` (Whisper in the line's language; bad takes are said again, up to 3 times) (for Russian it compares the sound - reduced vowels, devoicing, names in Latin letters are no error; the best take
of a line stays) → `bad` (the ones that stayed bad) → `finish` (xWMA and lips into `data/voice/<lang>`; the encoder from
`--encoder`, `OLDGENAI_XWMAENCODE` or the game folder); Russian lines with `say --native` (only from a voice's Russian
sample, `design_voices.py --lang ru`); `redo --voices <id>` voices a character again. A designed
voice: `scripts/design_voices.py --only <id>`. The story pack with the bank, to check: `python scripts/publish_content.py --build story`. The
details are in those scripts' docstrings.

---

## 3. Voice cloning (XTTS-v2, Qwen3-TTS, Higgs TTS 3)

All the "cloning" providers — **XTTS-v2**, **Qwen3-TTS** and **Higgs TTS 3** — speak with the voice of a sample
`clone:<name>`: a clean recording of speech **6–30 seconds** long (Qwen3-TTS takes up to 20 seconds of it). The samples are
shared by all of them and live in
`%APPDATA%\BoopiMod\speech\voices\<name>\`. There are three sources:

1. **By itself, in the studio.** When the studio voices the lines of a game NPC (Piper, Nick, Cait, a settler…) or of the hero
   with a cloning provider and there is no built-in voice that sounds like that person (Qwen3-TTS takes one first, 2.6), the
   sample is picked by itself: the speaker's voice type comes from the NPC record in your load order (for a boopi_mod
   character with a `game_voice_type` — from its card; for the hero — the player's voice of the hero's sex), a sample is cut
   from that type's lines in your game and kept — it is not cut again. Details in [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md),
   section 6.1.
2. **Cut from the game by hand.** In the "Voice samples" block enter an **NPC voice type** (for example `NPCMNickValentine`) and
   press **Cut from the game**.
3. **Your own recording.** Enter a voice name and press **Upload a recording (WAV)…**; for Qwen3-TTS type what the recording
   says, word for word (**Save text**) — the voice comes out closer with it; for Higgs it is optional.

How a sample is cut: lines of that type of 2–17 seconds each are taken from the game's voice archives until about 15 seconds
(at most 30) are there. When the game's strings have the subtitles of these lines, only lines with a clean text (no stage
directions) are taken and the text of each is kept next to it — Qwen3-TTS and Higgs get it together with the sample. The game's sound
is decoded by an installed XTTS-v2, or without it by the Creation Kit's `xWMAEncode.exe` (`Tools\Audio` in the game folder).
Whether a sample is "with text" or "no text" shows in the list.

To make a character always speak with a clone, put the XTTS speaker or the Qwen3-TTS / Higgs voice `clone:<name>` in the
voice card; if the character has a `game_voice_type`, Qwen3-TTS picks the designed voice that sounds like that type by itself,
and XTTS and Higgs the clone.

> [!WARNING]
> Clone only the voices you have the right to. The game's lines are used as a sample for personal use on your computer; they are
> not copied into the distribution. The samples stay in `%APPDATA%\BoopiMod\speech\voices` and never go into the mod you build.

---

## 4. Speech recognition (STT)

Settings → Voice → the **"Speech recognition"** block.

<p align="center"><img src="../../docs/images/settings-voice-stt.en.png" alt="Settings, the Voice tab: voicing, the speech recognition choice, the Whisper model, language and mode" width="860"></p>

*Settings → Voice: the WAV sample rate, voicing in the chat and the "Speech recognition" block — built in, OpenAI Whisper or off. The
screenshot is in Russian.*

### 4.1 Options

| Option | Notes |
|---|---|
| **Built in: faster-whisper + Silero VAD** | Runs on the CPU (int8), no network. Needs an engine and a model — the **Install** button (about 280 MB), downloaded once |
| **OpenAI Whisper (online)** | Needs an OpenAI key; the recording goes to the service |
| **Off** | Voice input does not work |

### 4.2 Parameters

- **Whisper model:** `tiny` (≈75 MB, the lightest, Russian is weaker), `base` (≈145 MB, a sensible minimum), `small` (≈480 MB, more
  accurate and heavier).
- **Spoken language:** Russian or English.
- **Mode:** "Push to talk" — the microphone listens while the key is held; "Always listen (Silero VAD)" — phrases are
  picked out by themselves. In the game the push-to-talk mode works.
- **Test the microphone → Record 5 seconds:** the app records a few seconds and shows what was recognised. The microphone is
  opened only for that time.

### 4.3 Voice input in the game

Hold **V** (the key can be changed in `Data\F4SE\Plugins\BoopiUI.ini`, `iPushToTalk` — a Windows key code), speak and release.
The text appears in the input line; **Enter** sends it (`bAutoSend=1` sends at once). The recording lasts up to 30 seconds
(`iMaxSeconds`).

> [!TIP]
> Press "Record 5 seconds" in the app first: it quickly shows whether the app sees your microphone.

---

## 5. Troubleshooting

| What you see | What to do |
|---|---|
| "The engine is not installed" | Press "Install" on the provider (or on recognition) |
| "The voice or model is not downloaded" | Download a Silero or a Whisper model in the provider block |
| "You need to accept the licence terms" | Tick the XTTS or Silero terms box and repeat the install |
| "The provider's API key is not set" | Paste the provider's key and press "Save key" |
| Qwen3-TTS: "Nothing answers at this Qwen3-TTS server address" / "no /v1/audio/speech" | Start your server and check the address: just `http://host:port` |
| Qwen3-TTS "This PC": "The Qwen3-TTS weights are not on this PC yet" | In the Qwen3-TTS card press "Download" or "Take from the folder" with weights you already have |
| Qwen3-TTS "This PC": "did not start" | Close programs that hold video memory (games, other neural networks) and press Start; the log is `logs\speech-qwen-gpu*.log` |
| Qwen3-TTS "This PC": "needs an NVIDIA graphics card with about 7 GB of free video memory" | Free some video memory, or use Edge TTS, XTTS-v2 or your own Qwen3-TTS server on another computer |
| Higgs: "Nothing answers at this Higgs server address" / "no /v1/audio/speech" | Start your server (vLLM-Omni, SGLang-Omni) and check the address: just `http://host:port` |
| Higgs "This PC": "did not start" | Close programs that hold video memory (games, other neural networks) and press Start; the log is `logs\speech-higgs-gpu*.log` |
| Higgs "This PC": "needs an NVIDIA graphics card with about 12 GB" | The model does not fit on this card — use Qwen3-TTS, Edge TTS, XTTS-v2 or the cloud |
| Higgs: "Boson refused the request for payment reasons" | Claim the trial credit or top up at boson.ai |
| "This voice has no sample" / "needs XTTS-v2 or xWMAEncode" | Cut a sample from the game or upload your own recording; cutting needs XTTS-v2 or the Creation Kit (`Tools\Audio\xwmaencode.exe`) |
| "Speech recognition is off" | Settings → Voice: choose built-in recognition or OpenAI Whisper |
| No sound in the game | Settings → Dialogues → "Voice the replies"; in `BoopiUI.ini` `bPlayReply=1`; check "Listen" on the provider |
| The voice plays but the lips stay still | `BoopiUI.ini` `bLipSync=1`; a studio line needs a WAV recording and "To the game" after it was voiced; `BoopiUI.log` says `face: ... speaks` when a track plays |
| V records nothing | Settings → Voice: is recognition installed, "Test the microphone"; "No microphone found" — choose the default recording device in Windows |
| Little disk space | Settings → Disk: speech engines and models can be deleted and installed again |

The messages above are paraphrased from the app's Russian interface.

Installs run through the app's job manager: progress is visible in the provider block, and on failure the reason is shown in the
same place. Speech data lives in `%APPDATA%\BoopiMod\speech\` (engine environments, models, cloned voices).

> [!TIP]
> **Feedback wanted — report problems and ideas, we'll fix them.** Open an issue at
> [github.com/boopi-coder/boopi_mod/issues/new](https://github.com/boopi-coder/boopi_mod/issues/new) and attach fresh logs from
> `%APPDATA%\BoopiMod\logs\`.

---

## 6. Other guides

| Guide | What it is about |
|---|---|
| [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md) | Script studio: your own dialogues, voicing lines, your own mod |
| [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md) | Importing animations and your own scenes in the G.A.M. editor |
| [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) | Animations in mods: gesture and scene, camera, calling from dialogues and scripts |
| [AI_DIALOGUE.md](AI_DIALOGUE.md) | AI dialogue in the game |
| [VOICE.md](VOICE.md) | Voicing (TTS) and speech recognition (STT) (you are here) |

[← All guides](README.md) · [← Project home page](../../README.en.md)
