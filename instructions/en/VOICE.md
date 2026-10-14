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
> - **Voicing (TTS)** decides who speaks the lines: online (Edge TTS, ElevenLabs, OpenAI) or local (XTTS-v2, Silero).
> - The easiest start is **Microsoft Edge TTS**: free, no key, Russian voices Dmitry and Svetlana.
> - Choose the provider: Settings → LLM providers → the "Text to speech (TTS)" block → **Use for voicing**.
> - **Speech recognition (STT)** — Settings → Voice: built in (faster-whisper) or OpenAI Whisper; in the game, hold **V**.
> - Local engines are not part of the app: they are installed by the **Install** button and work offline. XTTS-v2 can
>   **clone a voice**.
> - XTTS-v2 and Silero have **non-commercial** licences, so they are installed only after your explicit consent.

## Contents

1. [Where voice is used](#1-where-voice-is-used)
2. [Voicing (TTS)](#2-voicing-tts)
3. [Voice cloning (XTTS-v2)](#3-voice-cloning-xtts-v2)
4. [Speech recognition (STT)](#4-speech-recognition-stt)
5. [Troubleshooting](#5-troubleshooting)
6. [Other guides](#6-other-guides)

---

## 1. Where voice is used

Voice in boopi_mod is used in three places:

- **the chat with a character** in the app — the answers can be voiced;
- **the AI dialogue in the game** ([AI_DIALOGUE.md](AI_DIALOGUE.md)) — the person's answer sounds, and you can speak yourself by holding **V**;
- **the Script studio** — "Voice with AI" records the lines for your own dialogues ([SCRIPT_STUDIO.md](SCRIPT_STUDIO.md), the section
  about voicing lines).

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
> **non-commercial**. That is why they are not in the archive and are installed only after your explicit consent; Edge TTS
> and Whisper have no such restrictions.

### 2.3 A particular character's voice

Characters → the character → **Profile**: the voice card shows the fields of the chosen provider (ElevenLabs voice, OpenAI voice,
Edge voice, Silero speaker, XTTS speaker). Choose and press **Listen** — the choice is saved in your layer of
edits. If nothing is chosen for the character, the default voice for the language from the provider settings is used.

### 2.4 Voicing in the chat and in the game

- **The chat in the app:** the **Voice the replies** box above the input field (or Settings → Voice → "Voice the replies in the chat");
  a single reply can be voiced with the **Listen** button next to the character's name.
- **The AI dialogue in the game:** Settings → Dialogues → **Voice the replies**. The core gets the answer, synthesises a WAV and
  hands it to the game, which plays it (not positional, no lip sync).
- **WAV sample rate for the game** — 44100 Hz (like the game's lines) or 22050 Hz (half the size). Always mono, 16 bit — that is
  what the studio's voice build expects.

---

## 3. Voice cloning (XTTS-v2)

A clone is made from a clean recording of speech **6–30 seconds** long. There are two sources:

1. **Cut from the game.** In the XTTS block enter an **NPC voice type** (for example `NPCMNickValentine`) and press **Cut from the
   game**: the app finds the lines of this type in the game's voice archives, cuts and decodes several of them and saves them under
   this name. Needs XTTS installed and the game found.
2. **Your own recording.** Enter a voice name and press **Upload a recording (WAV)…**.

Finished clones are listed below. To make a character speak with a clone, put the XTTS speaker `clone:<name>` in the voice card; if
the character has a `game_voice_type`, the clone is picked up by itself.

> [!WARNING]
> Clone only the voices you have the right to. The game's lines are used as a sample for personal use on your computer; they are
> not copied into the distribution.

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
| "Speech recognition is off" | Settings → Voice: choose built-in recognition or OpenAI Whisper |
| No sound in the game | Settings → Dialogues → "Voice the replies"; in `BoopiUI.ini` `bPlayReply=1`; check "Listen" on the provider |
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
