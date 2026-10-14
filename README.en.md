<p align="center">
  <a href="README.md">🇷🇺 Русский</a> · <b>🇬🇧 English</b>
</p>

<p align="center">
  <img src="docs/images/posters/minimal.png" alt="boopi_mod REDUX — one mod manager, many worlds" width="100%">
</p>

<h1 align="center">boopi_mod <sup>REDUX</sup></h1>

<h3 align="center">Modding has never been this easy</h3>

<p align="center">
  <b>A mod manager for Fallout 4 in which you create — your own animations, scenarios, scenes and dialogues.<br>
  By hand or with AI help.</b>
</p>

<p align="center">
  <img alt="version 0.1.7 beta" src="https://img.shields.io/badge/version-0.1.7%20beta-3cff6b?style=flat-square">
  <a href="https://github.com/boopi-coder/boopi_mod/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/boopi-coder/boopi_mod?style=flat-square&label=%E2%AD%90%20stars&color=f2b705"></a>
  <img alt="Fallout 4 1.10.163 Old-Gen" src="https://img.shields.io/badge/Fallout%204-1.10.163%20Old--Gen-f2b705?style=flat-square">
  <img alt="Windows 10/11 x64" src="https://img.shields.io/badge/Windows-10%20%2F%2011%20x64-0078d4?style=flat-square">
  <a href="LICENSE.txt"><img alt="Freeware, all rights reserved" src="https://img.shields.io/badge/license-freeware%2C%20all%20rights%20reserved-8a8a8a?style=flat-square"></a>
  <a href="https://boosty.to/boopi_coder"><img alt="Boosty" src="https://img.shields.io/badge/Boosty-support-f15f2c?style=flat-square"></a>
  <img alt="18+" src="https://img.shields.io/badge/18%2B-adults%20only-b00020?style=flat-square">
</p>

<p align="center">
  <a href="https://github.com/boopi-coder/boopi_mod/releases/latest"><img alt="Download boopi_mod 0.1.7 beta" src="https://img.shields.io/badge/DOWNLOAD-boopi__mod%200.1.7%20beta%20for%20Windows-3cff6b?style=for-the-badge&labelColor=0d1210" height="54"></a>
  &nbsp;
  <a href="https://boosty.to/boopi_coder"><img alt="Support the author on Boosty" src="docs/images/support-button.png" height="54"></a>
</p>

<p align="center">
  <a href="#install-and-first-run">Install</a> ·
  <a href="#for-modders">For modders</a> ·
  <a href="#lullaby-the-new-story">The story</a> ·
  <a href="#faq">FAQ</a> ·
  <a href="#plans-skyrim-starfield-cyberpunk-2077-the-sims-4">Plans</a> ·
  <a href="instructions/en/README.md">Guides</a> ·
  <a href="https://github.com/boopi-coder/boopi_mod/issues/new">Report a problem</a> ·
  <a href="https://boosty.to/boopi_coder">Boosty</a>
</p>

> [!WARNING]
> **This is a beta (0.1.7).** Expect rough edges and bugs — please report them so I can fix them quickly:
> [open an issue](https://github.com/boopi-coder/boopi_mod/issues/new/choose) (the template tells you what to attach) — I read everything.
> **Feedback on problems and ideas is very welcome — we'll sort it out.**

---

**boopi_mod** is a desktop app plus a set of game plugins for **Fallout 4 (1.10.163, Old-Gen)**. First of all it is a **mod
manager**: it installs and runs your mods, prepares the game and puts the load order straight. But above all **you create
here**: draw animations in a 3D editor, write scenarios, scenes and dialogues in the studio, voice them and hand them to
friends as a single file. You can do it by hand — or let an AI assistant take over the routine. And then you can **play**
what you built: free-form conversations with the people of the Wasteland, "Life", voice and the new detective story
"Lullaby".

## What is inside

<table>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#mod-manager"><img src="docs/images/icons/mods.png" width="72" alt=""></a><br>
      <b><a href="#mod-manager">Mod manager</a></b><br>
      <sub>Base pack in one click, install with rollback, Nexus inside the app</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#mod-manager"><img src="docs/images/icons/load-order.png" width="72" alt=""></a><br>
      <b><a href="#mod-manager">Smart load order</a></b><br>
      <sub>"Sort" shows the plan, "Sort with AI" explains it too</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#gam-create-and-import-animations"><img src="docs/images/icons/gam.png" width="72" alt=""></a><br>
      <b><a href="#gam-create-and-import-animations">G.A.M.: your own animations</a></b><br>
      <sub>3D editor with IK handles, an AI animator, scenes play in the game</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#gam-create-and-import-animations"><img src="docs/images/icons/import.png" width="72" alt=""></a><br>
      <b><a href="#gam-create-and-import-animations">Animation import</a></b><br>
      <sub>Fallout 4 HKX animations and mod idles, Skyrim SE and OAR — into your editor</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#script-studio-dialogues-scenes-and-your-own-mod"><img src="docs/images/icons/studio.png" width="72" alt=""></a><br>
      <b><a href="#script-studio-dialogues-scenes-and-your-own-mod">Script Studio</a></b><br>
      <sub>Dialogues, scenes, branches off the game's wheels, voice, your own <code>.ogmod</code></sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#ai-help-and-ai-dialogue"><img src="docs/images/icons/ai-dialogue.png" width="72" alt=""></a><br>
      <b><a href="#ai-help-and-ai-dialogue">AI help and AI dialogue</a></b><br>
      <sub>An assistant in every tool and free conversation in the game</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#life-and-living-people"><img src="docs/images/icons/life.png" width="72" alt=""></a><br>
      <b><a href="#life-and-living-people">"Life" and living people</a></b><br>
      <sub>Relationships, reputation, law, dates, 27 characters with memory</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#lullaby-the-new-story"><img src="docs/images/icons/lullaby.png" width="72" alt=""></a><br>
      <b><a href="#lullaby-the-new-story">"Lullaby"</a></b><br>
      <sub>A detective story: 18 missions, 13 side quests, 9 endings</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#voice-speech-synthesis-and-recognition"><img src="docs/images/icons/voice.png" width="72" alt=""></a><br>
      <b><a href="#voice-speech-synthesis-and-recognition">Voice</a></b><br>
      <sub>Text-to-speech, voice cloning, speech recognition, push-to-talk</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#graphics-for-your-pc"><img src="docs/images/icons/graphics.png" width="72" alt=""></a><br>
      <b><a href="#graphics-for-your-pc">Graphics presets</a></b><br>
      <sub>12 presets and a recommendation for your PC</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#oldgen-os-on-the-pip-boy"><img src="docs/images/icons/oldgen-os.png" width="72" alt=""></a><br>
      <b><a href="#oldgen-os-on-the-pip-boy">OldGen OS</a></b><br>
      <sub>An app on the Pip-Boy: people, reputation, dossier, 57 achievements</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#safety-is-built-in"><img src="docs/images/icons/safety.png" width="72" alt=""></a><br>
      <b><a href="#safety-is-built-in">Safety</a></b><br>
      <sub>Content rules live in the core, not in a setting</sub>
    </td>
  </tr>
</table>

## What no other mod had

| | Vanilla | Other tools | **boopi_mod** |
|---|---|---|---|
| Installing mods and load order | by hand | managers (MO2, Vortex): you arrange the order | base pack in one click, journal and rollback, smart sorting and **AI sort** |
| Your own animation | no | external 3D packages, converters, hand-built files | a **3D editor inside** with IK handles and an AI animator |
| Importing ready-made animations (Fallout 4 HKX animations and mod idles, Skyrim) | no | by hand, through converters | "drop it, it plays", retargeted onto the Fallout 4 skeleton |
| Your own dialogues and scenes | Creation Kit | CK, Papyrus scripts | **Script Studio**, no programming, branches right on the game's wheel |
| AI help while creating | no | no | an AI assistant drafts a dialogue branch and builds a scene; the "Check in AI mode" chat |
| Sharing your mod | an archive and instructions | an archive and instructions | **a single `.ogmod` file**: installs in one click and is removed as one |
| Free conversation with NPCs | a wheel of lines | separate AI mods: talk only | in the game, with **real outcomes** (an item, a quest, a scene) validated by the core |
| Install rollback | no | partial | a journal: removing restores the files byte for byte |
| Story | the original | — | a new detective story, "Lullaby", with the vanilla game woven in |

> [!NOTE]
> The comparison is general: other tools have strengths of their own, and boopi_mod has its [0.1.0 limitations](#honest-limitations).

## What is new

<p align="center"><img src="docs/images/banners/whats-new.jpg" alt="What is new" width="100%"></p>

**0.1.7** — G.A.M.: undo and redo, key editing, mirror, full screen, face and camera, "▶ In game", scene events in the game, a library with search and previews, a sharper AI animator; Studio: triggers for your own stories, "+ Story", the dialogue player; Studio mods install from the boopi.site catalog with requirements. [0.1.7 notes](docs/release/v0.1.7.md).

**0.1.6** — animation import from Fallout 4 mods, Skyrim SE and OAR gaits, Life scenes through G.A.M., updated guides. [0.1.6 notes](docs/release/v0.1.6.md).

**0.1.5** — community mods from [boopi.site](https://boopi.site) right in the app, the boopi.site account and publishing your own mods from the Studio to moderation. [0.1.5 notes](docs/release/v0.1.5.md).

**0.1.4** — our mods download in the app from [boopi.site](https://boopi.site) and update separately from it; fixed the face editor after waking up. [0.1.4 notes](docs/release/v0.1.4.md).

**0.1.3** — fixes and an updated license: the app is freeware, all rights reserved. [0.1.3 notes](docs/release/v0.1.3.md).

**0.1.2** — the component "G.A.M. — animation manager" was removed at the request of a rights holder; installing 0.1.2
removes it from your game automatically. [0.1.2 notes](docs/release/v0.1.2.md).

**0.1.1** — in-app updates: at startup the app finds a new version by itself, and the "Download and install" button
installs it in one click (with a checksum check and a rollback if anything goes wrong). [0.1.1 notes](docs/release/v0.1.1.md).

**0.1.0** — the first public beta: a mod manager with a base pack, G.A.M. with a 3D editor and animation import, Script Studio with
`.ogmod` export, AI dialogue in the game, "Life", voice, 12 graphics presets and the story "Lullaby". The limitations are
[below](#honest-limitations) and in the [release notes](docs/release/v0.1.0.md#known-limitations).

---

## Mod manager

<p align="center"><img src="docs/images/banners/mods.jpg" alt="Mod manager" width="100%"></p>

<table>
  <tr>
    <td width="50%"><img src="docs/images/mods-base-pack.en.png" alt="The base modding pack and installed mods"></td>
    <td width="50%"><img src="docs/images/mods-load-order.en.png" alt="Installed mods and the plugin load order"></td>
  </tr>
</table>

- **The base pack in one click:** F4SE, Address Library, Buffout 4 NG, the Unofficial Patch (UFO4P) in your game's
  language, High FPS Physics Fix, MCM, Baka ScrapHeap. Ordered by dependencies, SHA-256 verified.
- **Our own parts** install with the same pack and are built **on your machine from your own game files**: the in-game
  plugin, **"G.A.M. — the animation engine"**, **boopi_hud** (an interface extension), "G.A.M.: gestures", "OldGen: the new story",
  "Boopi Corp.: Gen 4 synths".
- **Install with a journal and full rollback.** Mods are installed with hard links; removing restores the original files
  byte for byte. zip / 7z / rar archives by drag and drop; a Nexus Mods window inside the app (no API key needed).
- **Smart load order.** "Sort" first **shows the plan** without changing anything, and only then applies it;
  "Sort with AI" does the same with an explanation for every plugin.

Details: [Install and first run](#install-and-first-run).

## G.A.M.: create and import animations

<p align="center"><img src="docs/images/banners/gam.jpg" alt="G.A.M." width="100%"></p>

**G.A.M.** is our own animation engine and editor: it plays scenes in the game with its own plugin, `GAM.dll`.

<p align="center"><img src="docs/images/gam-editor-ik-ai.en.png" alt="The G.A.M. editor: IK handles, lighting and the AI animator's log" width="880"></p>

- **A 3D editor:** timeline, bones, the Rotate / Move / Character / Heading tools, **IK handles** on hands, feet and head,
  lighting, camera, several actors, creatures and furniture, a key optimiser. What you see in the editor is what plays in
  the game.
- **The AI animator:** "make him wave in greeting" — and the model builds the scene; the log shows every step, and you can
  refine the result by hand.
- **Animation import.** Animation packs you have installed: Fallout 4 animation mods (HKX, idles), **OAR** gait sets and
  **Skyrim SE** animations — they are retargeted onto the Fallout 4 skeleton and become tagged scenes you can edit in
  G.A.M. Rights to imported animations stay with their authors.
- **Scenes work everywhere:** in dialogues and scripts (gestures, scenes, camera) and in "Life".

<p align="center"><img src="docs/images/gam-library-import.en.png" alt="The scene library and pack import" width="560"></p>

<p align="center"><sub>The scene library (here: the game's own animations imported from «Fallout 4 — Data», filtered by tag) and one-click import</sub></p>

Guides: [import and the editor](instructions/en/ANIMATION_IMPORT.md) · [animations in dialogues and scripts](instructions/en/ANIMATION_GUIDE.md).

## Script Studio: dialogues, scenes and your own mod

<p align="center"><img src="docs/images/banners/studio.jpg" alt="Script Studio" width="100%"></p>

<table>
  <tr>
    <td width="50%"><img src="docs/images/studio-tree-builder.en.png" alt="The dialogue tree builder and the AI-dialogue section"></td>
    <td width="50%"><img src="docs/images/studio-tree-map.en.png" alt="The dialogue tree map: nodes and branches"></td>
  </tr>
</table>

- **Dialogues and scenes without programming:** trees in forms or YAML, a branch map, a checker that jumps to the error,
  gestures and G.A.M. scenes right inside the lines.
- **Branches off the game's wheels:** take a real Fallout 4 conversation and add your own line to its wheel.
- **Voice** with your own recordings or synthesis, with lip sync; Papyrus stubs for those who need a script.
- **Your own mod as one `.ogmod` file:** another player drags it into the boopi_mod window — dialogues, voice and G.A.M.
  scenes install together and are removed together.
- **AI helps:** it drafts a branch from a description, and the **"Check in AI mode"** button opens a test chat that shows which
  goals and flags fired — before you even start the game.

Guide: [instructions/en/SCRIPT_STUDIO.md](instructions/en/SCRIPT_STUDIO.md).

## AI help and AI dialogue

<p align="center"><img src="docs/images/banners/ai-dialogue.jpg" alt="AI dialogue" width="100%"></p>

AI in boopi_mod is a **modder's assistant** and, separately, a **way to play**. Either way it is your choice: you can skip
AI altogether, and the mod manager, the studio, G.A.M. and graphics work without it.

**Help while creating.** A dialogue branch from a description, a scene from a sentence, load order sorted "with AI",
your trees checked in the test chat. An API key — OpenRouter, DeepSeek, OpenAI — or a local Ollama; keys live in the Windows
Credential Manager.

**Free conversation in the game.** In the **"Progressive AI dialogue"** mode the wheel stays, but it gains a **"Say your
own…"** entry: you type (Russian or English layout) or speak by holding **V**.

<p align="center"><img src="docs/images/ingame-ai-hud.jpg" alt="In game: Piper's reply as a subtitle and the relationship card" width="880"></p>
<table>
  <tr>
    <td width="50%"><img src="docs/images/ingame-ai-input.jpg" alt="The in-game input line: Russian text and ready-made replies"></td>
    <td width="50%"><img src="docs/images/ingame-ai-reply.jpg" alt="The character's answer and suggestions for the next line"></td>
  </tr>
</table>

- The person knows who they are, what happened between you, your **S.P.E.C.I.A.L.**, level, karma and the story so far —
  and answers in character, with a subtitle and a voice. HUD widgets on **F10**.
- **The outcomes are real.** The AI only *asks*; the core *validates and executes*: it may hand over an item, set a quest
  stage or a story flag, start a scene — but only what that person's authored dialogue offers, and only when the talk has
  really got there.
- **A modder's own trees** get the AI mode too: the "AI dialogue" section of the studio says who the person is and where
  the conversation should lead.

Guide: [instructions/en/AI_DIALOGUE.md](instructions/en/AI_DIALOGUE.md).

## Life and living people

<table>
  <tr>
    <td width="50%"><img src="docs/images/characters-chat.en.png" alt="Chat with a character in the app"></td>
    <td width="50%"><img src="docs/images/life-people-reputation.en.png" alt="The Life page: people, reputation, achievements"></td>
  </tr>
</table>

- **27 key characters** with lore, personality and memory: talk to them right in the app (chat with voice) — even before
  you start the game. You can edit their cards and create your own.
- **"Life"** is one coherent system: a relationship with every NPC (affinity, trust, attraction),
  reputation with factions, law and wanted levels, dates, a night together, jealousy, shift work, weddings, diseases,
  settler abductions. Defeat is your choice: death as in the vanilla game, captivity or a "bad ending".

## "Lullaby": the new story

<p align="center"><img src="docs/images/banners/story.jpg" alt="Lullaby" width="100%"></p>

<p align="center"><img src="docs/images/in-game-main-menu.png" alt="The Fallout 4 main menu with boopi_mod" width="640"></p>

*For two hundred and ten years a machine kept you in a secret capsule. You were woken a year early, because someone came
for you. To understand who you are you must find those who came, and remember the morning you asked to forget.*

- **You are the second sleeper of Vault 111.** Pod **K-1** — not the one Nora climbed out of, and you are not her
  spouse. The OldGenAI core wakes you at **09:44**, while Nora left **sixteen days ago** to find her son. You know neither
  who you are nor who woke you.
- **Boopi Corp.** The headquarters, its Gen 4 synths, the Black Acorn night club and the Red Rocket bar — living places with
  their own people and dialogues. The core looks after you the way it was taught to, and that care can be suffocating.
- **"Case K-1" is a detective story.** Who am I? Who woke me? Why am I being hunted? An evidence board, a cipher,
  mini-games; every truth you find asks a more frightening question. And the answer to the last one may not be what you
  expect: **you may not be who you think you are.**
- **Four acts, 18 main missions, 13 side quests, 9 endings.** The ending is decided not by the last button but by your whole
  road: your decisions and your reputation with people, factions and the core. There is one truly good ending, one truly bad
  one, and seven in between.
- **The vanilla game is woven in, not thrown out.** The best vanilla quests — Vault 114, Fort Hagen, Kellogg's memory, the
  Glowing Sea — you play **yourself**, inside the new line, while Nora's path is told to you by the people you meet. All other
  side quests, companions, factions, settlements and DLC stay available.

> [!NOTE]
> A **new game** is recommended for the story; "Life", chat and AI dialogue also work with existing saves.

## Voice: speech synthesis and recognition

<table>
  <tr>
    <td width="50%"><img src="docs/images/settings-voice-tts.en.png" alt="Text-to-speech providers: local engines and voice cloning"></td>
    <td width="50%"><img src="docs/images/settings-voice-stt.en.png" alt="Speech recognition and text-to-speech"></td>
  </tr>
</table>

- **Text-to-speech (TTS):** online — Microsoft Edge TTS (no key), ElevenLabs, OpenAI; local — Piper, XTTS-v2, Silero.
- **Voice cloning** (XTTS-v2): a clone is made from the game's own lines by an NPC's voice type, or from your recordings.
- **Speech recognition (STT):** the built-in faster-whisper (runs on the CPU) or OpenAI Whisper; in the game —
  push-to-talk on **V**.
- The heavy engines are not part of the app: they install on a button, and the XTTS and Silero licences (non-commercial)
  are accepted explicitly.

Guide: [instructions/en/VOICE.md](instructions/en/VOICE.md).

## Graphics for your PC

<p align="center"><img src="docs/images/graphics-presets.en.png" alt="Graphics presets: PC detection and the recommended preset" width="880"></p>

- **12 ready presets** (from integrated 720p graphics and the Steam Deck to an RTX 4090 at 4K and an ultrawide monitor).
- The app detects your GPU, screen, RAM and CPU and marks the **"Recommended for your PC"** preset; applying it edits the
  game's INI files and makes backups.

## OldGen OS on the Pip-Boy

**OldGen OS** is an app on the Pip-Boy (press **H** with nobody in front of you): people, reputation and karma, a dossier,
health and **57 achievements**.

## Safety is built in

The project contains adult content (**18+**). The content rules are collected in a single core module and cannot be bypassed
by settings or by a model's answer: romance and intimacy only between adults and by consent; coercion is closed for everyone;
**a child never takes part in such scenes under any setting**. Every request for flirting, romance or intimacy is checked by
the core itself, whatever the AI says.

## Honest limitations

- **The in-game AI dialogue is a first version.** There is no **lip sync** yet (a reply arrives as a subtitle and a voice;
  the lips do not move). **Vanilla quest dialogues** do not get the AI mode yet — only our trees, modders' trees and the
  wheel with the "Say your own…" entry; the vanilla part comes in the next release.
- **Next-Gen / Anniversary (1.10.98x, 1.11.x) are not supported.** The target is 1.10.163 (Old-Gen); Steam and GOG have
  not been tested.
- **This is a beta:** expect rough edges and bugs — [report them](https://github.com/boopi-coder/boopi_mod/issues/new/choose) and I'll fix them quickly.
- The story is the first public edition: its world and mini-games will be refined; a **new game** is better for the story.
- The release files are **not code-signed**: SmartScreen may warn about an unknown publisher — verify the SHA-256.
- The local speech engines are large (XTTS-v2 is about 4.7 GB, an NVIDIA GPU is recommended) and install on a button.
- Windows only.

The full list is in the [release notes](docs/release/v0.1.0.md#known-limitations).

---

## Install and first run

<p align="center"><img src="docs/images/banners/install.jpg" alt="Install" width="100%"></p>

### What you need

| What | Needed |
|---|---|
| System | Windows 10 (22H2) or 11, x64; WebView2 (present in Windows 11 and in an up-to-date Windows 10) |
| Game | A legitimate **Fallout 4 version 1.10.163 (Old-Gen)** |
| F4SE | Required, **not included**: the app downloads it from the author's official page on your button |
| AI (optional) | An API key of one provider (OpenRouter, DeepSeek, OpenAI) **or** a local Ollama. Without AI the mod manager, the studio, G.A.M. and graphics work |
| Internet | For installing mods, the AI provider and online voice |
| Disk space | A few GB for the mod cache; the local XTTS-v2 is about 5 GB more (optional) |

### Step 0. Download and unpack

1. Download **`boopi_mod-0.1.7-win-x64.zip`** from the [Releases](https://github.com/boopi-coder/boopi_mod/releases/latest)
   page and compare its SHA-256 with `SHA256SUMS.txt` from the same release.
2. Unpack to a **short path** such as `C:\Games\boopi_mod` (not into "Downloads" or deep folders: Windows will not run
   programs whose path is longer than 260 characters).
3. Run **`boopi_mod.exe`** — the app starts the core by itself.
4. On the Dashboard press **"Download and install"**: the app downloads our mods from [boopi.site](https://boopi.site)
   (≈ 215 MB; the catalog is signed and files are checked by SHA-256), then **"Restart the core"**. From then on the
   mods update on their own, separately from the app.

> [!WARNING]
> The release files are not code-signed, so Windows SmartScreen may show a warning. Download only from the releases page and
> verify the hash.

### Step 1. Dashboard: is everything found

<p align="center"><img src="docs/images/dashboard.en.png" alt="Dashboard: the game is found, F4SE is installed, next steps" width="860"></p>

The **Dashboard** opens. The game should be found on its own: the path, version **1.10.163**, the Old-Gen edition, the F4SE
status. At the top right the core shows "online". Below, "Next steps": the app itself tells you what is left to do.

### Step 2. The game path (if it was not found)

<p align="center"><img src="docs/images/settings-game.en.png" alt="Settings → Game: the Fallout 4 path" width="860"></p>

If the game is not found (for example a copy without a registry entry), open **Settings → Game**, enter the folder that holds
`Fallout4.exe`, press **"Check"**, then **"Save"**. A folder you set by hand beats auto-detection.

### Step 3. Mods → "Base pack"

<p align="center"><img src="docs/images/mods-base-pack.en.png" alt="Mods: the base modding pack" width="860"></p>

Open **Mods** and press the install button of the base pack: F4SE, Address Library, Buffout 4 NG, UFO4P, High FPS Physics
Fix, MCM, Baka ScrapHeap and our own parts. What comes from Nexus Mods needs your account: with Premium the links are direct,
without it use the "Slow download" button in the Nexus window inside the app. Everything installed is listed on the right;
any mod can be removed.

### Step 4. An AI provider key (optional)

<p align="center"><img src="docs/images/settings-providers.en.png" alt="Settings → LLM providers: API keys and voice" width="860"></p>

For AI dialogue and the AI assistant: **Settings → LLM providers** → paste the API key → **"Save key"** → **"Check"**. The key
is kept in the Windows Credential Manager and is never shown again. Which model answers for what is set on the **"Routing"**
tab. Without a key, skip this step: the mod manager, the studio, G.A.M. and graphics work anyway. A local Ollama needs no key.

### Step 5. Dialogue mode

<p align="center"><img src="docs/images/settings-dialogue-mode.en.png" alt="Settings → Dialogues: the Progressive AI dialogue mode" width="860"></p>

**Settings → Dialogues** → the **"Progressive AI dialogue"** mode (or "Vanilla" if you do not want AI in conversations).
The answer length, voice and line suggestions are here too.

### Step 6. Hero, graphics and "Play"

<p align="center"><img src="docs/images/install-play.en.png" alt="Dashboard: the Play button" width="640"></p>

1. **Hero** — the name and sex come from your latest save; fill in the appearance and backstory: the characters will see them.
2. **Graphics → "Apply recommended"** (edits the game's INI files and makes backups).
3. Press **"Play"** — the game starts through F4SE. AI dialogue and "Life" work at once, the story from a new game.

<details>
<summary><b>If something went wrong (click to expand)</b></summary>

- **The game is not found.** "Settings → Game" → enter the folder with `Fallout4.exe`.
- **The game version is not 1.10.163.** The app warns you; launch is not blocked, but it is not guaranteed to work.
  Next-Gen and Anniversary are not supported.
- **`boopi_mod.exe` does not start.** Check the path (short, no deep folders) and that WebView2 is present. SmartScreen:
  "More info" → "Run anyway" — after verifying the SHA-256.
- **A Nexus mod will not download.** An account is required; without Premium use "Slow download" in the Nexus window inside the app.
- **The AI is silent.** "Settings → LLM providers" → "Check" on your provider; check the key's balance, the "Dialogue" route on
  the "Routing" tab and the mode on the "Dialogues" tab.
- **No voice.** "Settings → Voice": pick a voice provider; Edge TTS needs no key but needs the internet.
- **The game crashes on start.** Open the Buffout 4 NG crash log (folder `Documents\My Games\Fallout4\F4SE`, files
  `crash-*.log`) and attach it to your report.
- **App logs:** `%APPDATA%\BoopiMod\logs\` (`app.log`, `core.log`, `all.log`, `errors.log`). Data and settings:
  `%APPDATA%\BoopiMod\`.

**Did not help?** [Open an issue](https://github.com/boopi-coder/boopi_mod/issues/new): the app version, the steps, the
`all.log` file and the F4SE crash log. Write about any problems and ideas — we will sort them out.

</details>

**What the app installs itself** (on your button, with hash checks): F4SE and Buffout 4 NG — from their authors' GitHub;
Address Library, UFO4P, High FPS Physics Fix, MCM, Baka ScrapHeap — from the authors' Nexus Mods pages. Our own plugins
(`BoopiCorp.esp`, `OldGenStory.esp`, posters, `boopi_hud`) and F4SE plugins (`OldGenAI.dll`, `BoopiUI.dll`, `GAM.dll`) are
built by the app and placed into the game for you.

### Updates

At startup (at most once a day) the app checks whether a new version is out and shows a **"New version available"** banner
on the Dashboard with a "Download" button. You can turn the check off in the settings. To hear about releases even without
the app, click **Watch → Custom → Releases** on GitHub and you'll get an email for every new version.

---

## For modders

<p align="center"><img src="docs/images/banners/modders.jpg" alt="For modders" width="100%"></p>

Everything the app does can be extended — without programming and without other people's tools. What you can build:

- **Your own animation** — in the G.A.M. 3D editor with IK handles, or in words through the AI animator; import animations from
  mods you have installed.
- **Your own conversation** — a dialogue tree with branching, gestures and scenes; a branch off the game's wheel; voice and lip sync.
- **Your own scene** — actors, movement, camera, tags so that "Life", dialogues and other mods can find it.
- **Your own mod as a single `.ogmod`** that others install in one click, and **your own AI dialogues** — checked in the test chat.

| Guide | What it covers |
|---|---|
| [SCRIPT_STUDIO.md](instructions/en/SCRIPT_STUDIO.md) | Script Studio: dialogue trees, branches off the game, the AI block, voice, your own `.ogmod` mod |
| [ANIMATION_IMPORT.md](instructions/en/ANIMATION_IMPORT.md) | Animation import and the G.A.M. scene editor |
| [ANIMATION_GUIDE.md](instructions/en/ANIMATION_GUIDE.md) | Animations in dialogues and scripts: gestures, scenes, camera, contexts |
| [AI_DIALOGUE.md](instructions/en/AI_DIALOGUE.md) | The AI dialogue mode: what the player sees, what the AI can and cannot do |
| [VOICE.md](instructions/en/VOICE.md) | Text-to-speech and speech recognition: providers and voice cloning |

All the guides also exist [in Russian](instructions/README.md).

## FAQ

<details>
<summary><b>Are Next-Gen / Anniversary (1.10.98x, 1.11.x) supported?</b></summary>

Not yet. The target is **1.10.163 (Old-Gen)**, on which the F4SE plugins are stable. The app warns you if the game version is
different; launch is not blocked, but it is not guaranteed to work. The Steam and GOG editions have not been tested.
</details>

<details>
<summary><b>Do I need AI to use the program?</b></summary>

No. The mod manager, Script Studio, the G.A.M. editor and import, and the graphics presets work without AI. AI is needed for
the assistant, AI dialogue in the game and (optionally) cloud voice.
</details>

<details>
<summary><b>What happens to my old saves?</b></summary>

"Life", chat and AI dialogue do not need a new game, but the story "Lullaby" and the new places are built for a **new game**.
Adding and removing plugins mid-playthrough is the usual risk of any mods: back up your `Saves` folder.
</details>

<details>
<summary><b>What goes to the internet and where are my keys?</b></summary>

There is no telemetry. Dialogue lines and the hero's and character's data go to **the AI provider you chose** (OpenRouter,
DeepSeek, OpenAI; the text to be spoken goes to Microsoft Edge TTS or ElevenLabs/OpenAI if you chose them). If you want
nothing to leave your PC, use a local Ollama and local Piper / Whisper. The update check is one request to github.com a day,
with no data about you; it can be turned off in the settings. API keys are kept in the **Windows Credential
Manager** (service `BoopiMod`) and are never written to files.
</details>

<details>
<summary><b>Is it safe for my game?</b></summary>

Mods install through a journal with full rollback; before launch the app checks the game version, F4SE and the required mods.
The content rules are collected in a single core module: romance and intimacy only between adults and by consent; coercion is
closed for everyone; a child never takes part in such scenes under any setting; the AI cannot bypass any of this.
</details>

<details>
<summary><b>May I share the mods I make?</b></summary>

Yes. Mods you create with boopi_mod (dialogue trees, scenes, voice lines and `.ogmod` packages made from your own work)
belong to you (see `NOTICE.txt`). Respect the rights of the authors of anything you include.
</details>

<details>
<summary><b>Why does AI dialogue have no lip sync yet?</b></summary>

This is the first version: a reply arrives as a subtitle and a voice, but the lips do not move yet. Vanilla quest dialogues
will get the AI mode in the next release.
</details>

<details>
<summary><b>I found a bug or have an idea — where do I write?</b></summary>

In this repository's [issues](https://github.com/boopi-coder/boopi_mod/issues/new): the app version, the steps, the file
`%APPDATA%\BoopiMod\logs\all.log` and the F4SE crash log help sort it out fast. **Feedback wanted — report problems and
ideas, we'll fix them.**

🧡 **Questions and requests posted on [Boosty](https://boosty.to/boopi_coder) are handled first.**
</details>

## Plans: Skyrim, Starfield, Cyberpunk 2077, The Sims 4

Planned: boopi_mod for other games — **Skyrim**, **Starfield**, **Cyberpunk 2077** and **The Sims 4** — the same mod
manager and the same creation of animations, scenes and dialogues by hand or with AI. What comes first and when depends on
**interest in the project, support and stars on GitHub**:

- ⭐ [Star the repo](https://github.com/boopi-coder/boopi_mod/stargazers) — the best way to show the project is wanted;
- 💬 [tell me](https://github.com/boopi-coder/boopi_mod/issues/new/choose) which game you want most;
- 🧡 [support on Boosty](https://boosty.to/boopi_coder) — it directly speeds up the work.

## Feedback

> **This is the first beta — feedback wanted: report problems and ideas, I'll fix them quickly.**
> [Report a problem or suggest an idea](https://github.com/boopi-coder/boopi_mod/issues/new/choose) · for a bug attach the
> app version, `%APPDATA%\BoopiMod\logs\all.log`, the F4SE crash log and the steps to reproduce.

## Support the author

<p align="center">
  <a href="https://boosty.to/boopi_coder"><img alt="Support the author on Boosty" src="docs/images/support-button.png" width="360"></a>
</p>

boopi_mod is made by one person. If the project is useful to you, support it on **[Boosty](https://boosty.to/boopi_coder)**: it
directly pays for development time (Next-Gen support, AI in vanilla dialogues, lip sync, new scenes and presets).
Questions and requests posted on Boosty are handled **first**.

### ₿ Crypto

<table>
  <tr>
    <td align="center" width="50%">
      <img alt="Bitcoin" src="https://img.shields.io/badge/Bitcoin-BTC-f7931a?style=for-the-badge&logo=bitcoin&logoColor=white"><br>
      <sub>Bitcoin network</sub><br><br>
      <img alt="QR Bitcoin" src="docs/images/crypto/qr-btc.png" width="170"><br><br>
      <code>bc1qw082qflzsw7qzpe6ghtv8uj4cga83ehqfxyx6a</code>
    </td>
    <td align="center" width="50%">
      <img alt="Ethereum" src="https://img.shields.io/badge/Ethereum-ETH-627eea?style=for-the-badge&logo=ethereum&logoColor=white"><br>
      <sub>Ethereum network (ERC-20)</sub><br><br>
      <img alt="QR Ethereum" src="docs/images/crypto/qr-eth.png" width="170"><br><br>
      <code>0x69a6Ccd27143F077EBC822f4Af8F8e8dB6371543</code>
    </td>
  </tr>
</table>

Copy an address with the button on the right of the block below:

**Bitcoin (BTC)**

```
bc1qw082qflzsw7qzpe6ghtv8uj4cga83ehqfxyx6a
```

**Ethereum (ETH, ERC-20)**

```
0x69a6Ccd27143F077EBC822f4Af8F8e8dB6371543
```

> [!NOTE]
> Send only on the matching network: BTC to the Bitcoin address, ETH and ERC-20 tokens to the Ethereum address. A transfer on another network may be lost. Thank you for the support! 🧡

## License and credits

- boopi_mod is **freeware, all rights reserved.** You may use it free of charge and share the original archive, credited to
  the author. You may **not** sell it, modify it, distribute modified versions or reverse-engineer it. Full text:
  [`LICENSE.txt`](LICENSE.txt); third-party components: [`NOTICE.txt`](NOTICE.txt). Mods you create with boopi_mod are yours.
- boopi_mod is an unofficial project and is not affiliated with Bethesda Softworks / ZeniMax Media. **Fallout** is a trademark
  of its owners. You need your own copy of the game.
- **Third-party components in the archive:** 7-Zip (LGPL, unmodified, 7-zip.org); texconv from DirectXTex (Microsoft, MIT);
  CommonLibF4, fmt, spdlog, rsm-mmio (MIT) and boost-stl-interfaces (BSL-1.0) inside our F4SE plugins; React, three.js, Tauri
  (MIT / Apache-2.0); IBM Plex fonts (SIL OFL 1.1); the core's Python libraries under their own licences.
- **Not in the archive and downloaded by you:** F4SE, Buffout 4 NG, Address Library, UFO4P, High FPS Physics Fix, MCM, Baka
  ScrapHeap (their authors forbid or restrict redistribution — the app only helps you download from the official sources).
  The speech engines XTTS-v2 (Coqui Public Model License) and Silero (CC BY-NC-SA 4.0) install on request, with the terms accepted.
- Author: **boopi-coder** — [github.com/boopi-coder](https://github.com/boopi-coder).
