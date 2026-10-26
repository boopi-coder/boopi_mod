<p align="center">
  <a href="README.md">🇷🇺 Русский</a> · <b>🇬🇧 English</b>
</p>

<p align="center">
  <img src="docs/images/posters/minimal.png" alt="boopi_mod REDUX" width="100%">
</p>

<h1 align="center">boopi_mod <sup>REDUX</sup></h1>

<p align="center">
  <b>A mod manager for Fallout 4, with tools to make your own animations, dialogues, scenes and textures.<br>
  By hand or with AI help.</b>
</p>

<p align="center">
  <img alt="version 0.2.5 beta" src="https://img.shields.io/badge/version-0.2.5%20beta-3cff6b?style=flat-square">
  <a href="https://github.com/boopi-coder/boopi_mod/stargazers"><img alt="GitHub stars" src="https://img.shields.io/github/stars/boopi-coder/boopi_mod?style=flat-square&label=%E2%AD%90%20stars&color=f2b705"></a>
  <img alt="Fallout 4: Old-Gen · Next-Gen · Anniversary" src="https://img.shields.io/badge/Fallout%204-Old--Gen%20%C2%B7%20Next--Gen%20%C2%B7%20Anniversary-f2b705?style=flat-square">
  <img alt="Skyrim SE / AE: beta" src="https://img.shields.io/badge/Skyrim%20SE%20%2F%20AE-beta-6f8fa8?style=flat-square">
  <img alt="Windows 10/11 x64" src="https://img.shields.io/badge/Windows-10%20%2F%2011%20x64-0078d4?style=flat-square">
  <a href="LICENSE.txt"><img alt="Freeware, all rights reserved" src="https://img.shields.io/badge/license-freeware%2C%20all%20rights%20reserved-8a8a8a?style=flat-square"></a>
  <a href="https://boosty.to/boopi_coder"><img alt="Boosty" src="https://img.shields.io/badge/Boosty-support-f15f2c?style=flat-square"></a>
  <a href="https://www.donationalerts.com/r/boopi_coder"><img alt="DonationAlerts" src="https://img.shields.io/badge/donate-server%20fund-f57d07?style=flat-square"></a>
  <img alt="18+" src="https://img.shields.io/badge/18%2B-adults%20only-b00020?style=flat-square">
</p>

<p align="center">
  <a href="https://github.com/boopi-coder/boopi_mod/releases/latest"><img alt="Download boopi_mod 0.2.5 beta" src="https://img.shields.io/badge/DOWNLOAD-boopi__mod%200.2.5%20beta%20for%20Windows-3cff6b?style=for-the-badge&labelColor=0d1210" height="54"></a>
  &nbsp;
  <a href="https://boosty.to/boopi_coder"><img alt="Support the author on Boosty" src="docs/images/support-button.png" height="54"></a>
</p>

<p align="center">
  <a href="#install-and-first-run">Install</a> ·
  <a href="#for-modders">For modders</a> ·
  <a href="#lullaby-the-new-story">The story</a> ·
  <a href="#faq">FAQ</a> ·
  <a href="#whats-coming">What's coming</a> ·
  <a href="instructions/en/README.md">Guides</a> ·
  <a href="https://github.com/boopi-coder/boopi_mod/issues/new">Report a problem</a> ·
  <a href="https://boosty.to/boopi_coder">Boosty</a>
</p>

> [!WARNING]
> **This is a beta (0.2.5).** There may be bugs. Please report bugs and ideas in the
> [issues](https://github.com/boopi-coder/boopi_mod/issues/new/choose). The template tells you what to attach. I read everything.

---

**boopi_mod** is a Windows app and a set of game plugins for **Fallout 4**: Old-Gen 1.10.163, Next-Gen 1.10.980 / 1.10.984
and Anniversary 1.11.191 / 1.11.221 / 1.11.240 (what is checked in the game: see [limitations](#limitations)). The app
installs mods and sorts the load order. It has an animation editor, a dialogue studio, and an editor for textures and 3D
objects. In the game it adds relationships with NPCs, free talk with NPCs through AI, and a new main story, voiced in
Russian and English. Skyrim SE / AE has a [beta](#skyrim-se--ae-beta): G.A.M. scenes play there too.

## What's inside

<table>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#mod-manager"><img src="docs/images/icons/mods.png" width="72" alt=""></a><br>
      <b><a href="#mod-manager">Mod manager</a></b><br>
      <sub>Base pack in one click, install with rollback, Nexus inside the app</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#mod-manager"><img src="docs/images/icons/load-order.png" width="72" alt=""></a><br>
      <b><a href="#mod-manager">Load order</a></b><br>
      <sub>Shows the plan first, then applies it; AI can explain it</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#gam-animations"><img src="docs/images/icons/gam.png" width="72" alt=""></a><br>
      <b><a href="#gam-animations">G.A.M.: your animations</a></b><br>
      <sub>3D editor, AI animator, sounds on the timeline, scenes in the game</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#gam-animations"><img src="docs/images/icons/import.png" width="72" alt=""></a><br>
      <b><a href="#gam-animations">Animation import</a></b><br>
      <sub>HKX and idles from Fallout 4 mods, Skyrim SE, OAR</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#script-studio"><img src="docs/images/icons/studio.png" width="72" alt=""></a><br>
      <b><a href="#script-studio">Script Studio</a></b><br>
      <sub>Dialogues, scenes, triggers, voice, your own <code>.ogmod</code> mod</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#ai-help-and-ai-dialogue"><img src="docs/images/icons/ai-dialogue.png" width="72" alt=""></a><br>
      <b><a href="#ai-help-and-ai-dialogue">AI help and AI dialogue</a></b><br>
      <sub>An assistant in the tools and free talk in the game</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#life-relationships-and-the-world"><img src="docs/images/icons/life.png" width="72" alt=""></a><br>
      <b><a href="#life-relationships-and-the-world">"Life"</a></b><br>
      <sub>Relationships, reputation, law, dates, 27 characters with memory</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#lullaby-the-new-story"><img src="docs/images/icons/lullaby.png" width="72" alt=""></a><br>
      <b><a href="#lullaby-the-new-story">"Lullaby"</a></b><br>
      <sub>A detective story: 18 missions, 13 side quests, 9 endings, voiced in two languages</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#voice"><img src="docs/images/icons/voice.png" width="72" alt=""></a><br>
      <b><a href="#voice">Voice</a></b><br>
      <sub>Text-to-speech, real-time voice for AI replies, lip sync, speech recognition</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#graphics"><img src="docs/images/icons/graphics.png" width="72" alt=""></a><br>
      <b><a href="#graphics">Graphics presets</a></b><br>
      <sub>12 presets and a recommendation for your PC</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#oldgen-os-on-the-pip-boy"><img src="docs/images/icons/oldgen-os.png" width="72" alt=""></a><br>
      <b><a href="#oldgen-os-on-the-pip-boy">OldGen OS</a></b><br>
      <sub>A Pip-Boy app: people, reputation, dossiers, achievements</sub>
    </td>
    <td width="33%" align="center" valign="top">
      <a href="#content-rules"><img src="docs/images/icons/safety.png" width="72" alt=""></a><br>
      <b><a href="#content-rules">Content rules</a></b><br>
      <sub>The 18+ rules are built into the core, not into settings</sub>
    </td>
  </tr>
  <tr>
    <td width="33%" align="center" valign="top">
      <a href="#forge-3d-objects-and-textures"><img src="docs/images/icons/forge.png" width="72" alt=""></a><br>
      <b><a href="#forge-3d-objects-and-textures">F.O.R.G.E.</a></b><br>
      <sub>The game's 3D objects and textures: recolour, weapons from parts, your own models</sub>
    </td>
    <td width="33%"></td>
    <td width="33%"></td>
  </tr>
</table>

## What's new

<p align="center"><img src="docs/images/banners/whats-new.jpg" alt="What's new" width="100%"></p>

**0.2.5** — the animation menu in the game: look at a person and hold "=" — a scene for yourself, for them, for two NPCs
or for you both; our mods install as BA2 archives instead of loose files in Data and come out of the game without a trace
(from Windows "Apps" too); an FPS cap; quest markers; save names, Red Rocket and the synth factory fixed; civil companions
sit when asked; launch through MO2; your own Piper and XTTS. [0.2.5 notes](docs/release/v0.2.5.md).

**0.2.4** — move from Mod Organizer 2 and Vortex in a couple of clicks (and export back to MO2); any mod can be
switched off; FOMOD installers; installs check compatibility (F4SE plugins made for another game version, missing
masters); a smarter load order (overlapping records, limits, the LOOT list); MCM on Anniversary only on 1.11.240.
[0.2.4 notes](docs/release/v0.2.4.md).

**0.2.3** — fixes for Next-Gen and Anniversary: Home shows when our mods are not in the game, and one button installs
them; after a game reinstall the mods install again (the menu logo comes back); the latest UFO4P, MCM, High FPS Physics Fix
and Buffout 4 AE in the base pack; the voiced Boopi Corp. installs much faster.
[0.2.3 notes](docs/release/v0.2.3.md).

**0.2.2** — support for Next-Gen 1.10.980 / 1.10.984 and Anniversary 1.11.191 / 1.11.221 / 1.11.240: one build of our
plugins, everything on, checked in the game on 1.11.191. "Lullaby" is fully voiced in Russian and English, with a voice of
its own for every character. An AI reply is spoken in parts while it is written; a new local engine, Qwen3-TTS. The
Skyrim SE / AE beta is checked in the game. F.O.R.G.E. can recolour a texture inside the app. The pre-launch check finds a
broken `Fallout4.ini` and MO2 profiles, and "Copy logs for a report" puts the logs into one zip.
[0.2.2 notes](docs/release/v0.2.2.md).

**0.2.1** — the start of "Lullaby" after the pod works again (the S.P.E.C.I.A.L. screen, controls, sound). Updates are
checked at start and every 30 minutes, and the "What's new" window installs them with one button. G.A.M. and F.O.R.G.E.
fill the whole window, and you can drag the panel borders.
[0.2.1 notes](docs/release/v0.2.1.md).

**0.2.0** — F.O.R.G.E. gets weapons from parts, recolouring for one item or one person, a map generator, and your own 3D
models in the game. G.A.M. gets ready poses, a new timeline, and fitting a couple to the actors' height. Lip sync with facial
expression. A beta for Skyrim SE. [0.2.0 notes](docs/release/v0.2.0.md).

<details>
<summary><b>Older versions</b></summary>

- [0.1.9](docs/release/v0.1.9.md) — F.O.R.G.E., sounds on the timeline, AI polish for animations, lip sync, game and language choice.
- [0.1.8](docs/release/v0.1.8.md) — AI in the game's own dialogues, talk to anyone, "Lullaby" playable to every ending.
- [0.1.7](docs/release/v0.1.7.md) — undo and redo in G.A.M., "▶ In game", triggers and the dialogue player.
- [0.1.6](docs/release/v0.1.6.md) — animation import from Fallout 4, Skyrim SE and OAR.
- [0.1.5](docs/release/v0.1.5.md) — community mods from [boopi.site](https://boopi.site) and publishing from the Studio.
- [0.1.4](docs/release/v0.1.4.md) — our mods update separately from the app.
- [0.1.3](docs/release/v0.1.3.md) — fixes and a new license.
- [0.1.2](docs/release/v0.1.2.md) — new descriptions and screenshots.
- [0.1.1](docs/release/v0.1.1.md) — app updates in one click.
- [0.1.0](docs/release/v0.1.0.md) — the first public beta.

</details>

---

## Mod manager

<p align="center"><img src="docs/images/banners/mods.jpg" alt="Mod manager" width="100%"></p>

<table>
  <tr>
    <td width="50%"><img src="docs/images/mods-base-pack.en.png" alt="The base modding pack and installed mods"></td>
    <td width="50%"><img src="docs/images/mods-load-order.en.png" alt="Installed mods and the plugin load order"></td>
  </tr>
</table>

- **Base pack in one click:** F4SE, Address Library, Buffout 4 NG, UFO4P in your game's language, High FPS Physics Fix, MCM,
  Baka ScrapHeap. They install in dependency order, and every file is checked by SHA-256.
- **For your game version.** The app detects the edition (Old-Gen, Next-Gen, Anniversary). On Next-Gen and Anniversary the
  pack offers the F4SE and Address Library files from Nexus for your exact version; you download them with your own Nexus
  account.
- **Pre-launch check:** the game version, F4SE, the Address Library, the required mods. It finds a `Fallout4.ini` without
  the game's archive lists and Mod Organizer 2 profiles with their own INIs, and it can restore the default INI.
- **Our own parts** install with the same pack. They are built on your PC from your own game files: the game plugin,
  G.A.M., boopi_hud, "G.A.M.: gestures", "OldGen: the new story", "Boopi Corp.: Gen 4 synths".
- **Rollback.** Mods are installed with hard links and a journal. When you remove a mod, the original files come back byte
  for byte.
- **Moving over from Mod Organizer 2 and Vortex.** The app finds their Fallout 4 mods by itself and offers "Move them here":
  the mods come enabled and disabled as they were, with the same winners of shared files and the same plugin order; files
  are not copied (the same files on disk), MO2 and Vortex keep working. "Undo the move" puts everything back. "Export to
  MO2" is the way back (and Vortex takes mods over from MO2 itself).
- **Any mod can be switched off** - its files leave the game (whatever it covered comes back), its priority and plugins
  stay; switching it on puts everything back.
- You can drop zip, 7z and rar archives onto the window. A Nexus Mods window is built into the app; no API key is needed.
- **Load order:** "Sort" shows the plan first and applies it only after that. "Sort with AI" also explains each plugin.

## G.A.M.: animations

<p align="center"><img src="docs/images/banners/gam.jpg" alt="G.A.M." width="100%"></p>

**G.A.M.** is our animation engine and editor. In the game the `GAM.dll` plugin plays the scenes, the same as in the editor.

<p align="center"><img src="docs/images/gam-editor-ik-ai.en.png" alt="The G.A.M. editor: IK handles, lighting and the AI animator's log" width="880"></p>

- **3D editor:** timeline, bones, IK handles on hands, feet and head, lighting. Several actors, creatures, furniture and
  props.
- **AI animator:** describe a scene in one sentence ("they embrace and sway"), and it builds the scene step by step. You can
  fix the result by hand.
- **Ready poses** without an AI key: standing, on a chair, kneeling, crouching, on the floor, lying.
- **Checks before you start the game:** arms through the body, twisted wrists, a body inside furniture, sliding feet. A
  motion score from 0 to 100: jerks, balance, shaking contacts. A model that can see images can also check a storyboard.
- **AI polish** with one button: smooth motion, arcs, weight shifts, breathing, a loop without a seam. Contacts stay in place.
- **Editing:** undo and redo, several keys at once, mirror, stretch time, copy a pose to another actor, key values as
  numbers, grid and angle step, fullscreen.
- **Hand polish:** a curve editor, "Ghosts" of nearby frames, trails, before/after compare (key **B**), speed 0.25×–2×.
- **Role height** 0.5–1.5. In the game (G.A.M. 0.6.1) a couple is fitted to the actors' real height: places and hands.
- **Sounds on the timeline** (wav, ogg, mp3, flac, m4a) play in the game from the actor's position. 22 sounds are included.
  Needs G.A.M. 0.5.0.
- **▶ In game:** the scene plays at once in your running game. No install, no restart.
- **Scene events:** a sound, a line, an expression, an outfit change, a quest stage, your own events. Face and camera tracks.
- **Library:** search, folders, favourites, version history. Previews as GIF, WebM or PNG.
- **Import:** HKX and idles from Fallout 4 mods, OAR gaits and Skyrim SE animations are moved onto the Fallout 4 skeleton and
  become scenes. Creature and robot clips go onto their own skeletons. Import runs in the background, and you can stop it.
  The rights to the animations stay with their authors.
- **Other games:** you can save a scene for [Skyrim SE / AE](#skyrim-se--ae-beta) and install it there.
- G.A.M. scenes are used in dialogues, scripts and "Life".

<p align="center"><img src="docs/images/gam-library-import.en.png" alt="The scene library and pack import" width="560"></p>

<p align="center"><sub>The scene library (here: the game's own animations, filtered by tag) and import</sub></p>

Guides: [import and the editor](instructions/en/ANIMATION_IMPORT.md) · [animations in dialogues and scripts](instructions/en/ANIMATION_GUIDE.md).

## F.O.R.G.E.: 3D objects and textures

**F.O.R.G.E.** shows the game's 3D objects with their textures. You can recolour objects, build weapons from parts, and put
your own model into the game.

<p align="center"><img src="docs/images/forge-3d-catalog.en.webp" alt="F.O.R.G.E.: the game catalog and a dress in 3D with its real textures" width="880"></p>

- **Catalog:** furniture, items, weapons, clothing, people and creatures, with names in your language. Search by name,
  editor id, form id and model path. Filter by plugin.
- **3D view** with the real textures. Click a part to select it, or hide it. Clothes are shown on the G.A.M. skeleton; hair
  and armour show in their palette colour.
- **Weapons from parts:** any weapon variant and any parts from your load order. There is a first-person view.
- **Recolouring:** "Save as PNG", edit it in any image editor, "New picture…" (or the app reads the changed PNG by itself).
  The app converts the picture to the game's format and keeps the original's format, mips and size.
- **Who it changes:** everywhere, this material only, this outfit only, this person only, or this person's skin only. The
  records for an outfit or a person go into a small plugin, `BoopiForge.esp`.
- **Recolour in the app:** hue, saturation, darker or lighter, with a preview on the model. It always starts from the
  game's texture, not from an earlier recolour.
- **Map generator:** makes normal, gloss, cavity and glow maps from the main texture.
- **"My textures"** install as a mod through the journal and come out byte for byte. Install them with the game closed.
- **Texture packs `.ogmod`** hold only your pictures. Install them by drag and drop or from boopi.site.
- **Texture mod import:** drop a folder or a .zip with `Textures\…` inside. Before install you see which textures replace
  the game's.
- **"My objects":** an OBJ, glTF or GLB file becomes a static object. The app writes the NIF, materials, textures and
  collision itself. The object appears in the workshop menu ("Decorations"/"Furniture") and can be placed with
  `player.placeatme`.
- **Export:** a UV template, OBJ or GLB, a PNG snapshot.

<table>
  <tr>
    <td width="50%"><img src="docs/images/forge-person.en.png" alt="This person only: an item changes on one character"></td>
    <td width="50%"><img src="docs/images/forge-object.en.png" alt="Your own model into the game: the preview and the My objects tab"></td>
  </tr>
  <tr>
    <td width="50%"><img src="docs/images/forge-3d-retexture.en.webp" alt="Recolouring: a new texture in live preview"></td>
    <td width="50%"><img src="docs/images/forge-3d-import.en.webp" alt="Texture mod import: what fits your game"></td>
  </tr>
</table>

Guide: [instructions/en/FORGE.md](instructions/en/FORGE.md).

## Skyrim SE / AE: beta

You choose Skyrim Special Edition in "Settings → Games & theme".

- F.O.R.G.E. and G.A.M. read Skyrim archives (BSA, SE and LE). In Skyrim, F.O.R.G.E. only shows models and textures for now.
- G.A.M. scenes are moved onto the skeleton from your game.
- **GAM for Skyrim** is an SKSE64 plugin (SE 1.5.97, AE 1.6.x). It plays G.A.M. scenes from the console (`gam list`,
  `gam play <scene>`, `gam stop`) and from Papyrus. Install it with a button in "Settings → Games & theme" or in G.A.M. →
  "Other games". Download SKSE64 and Address Library yourself.
- **Checked in the game** on Skyrim AE 1.6.1170 with SKSE64 2.2.6: scenes on the player and on NPCs, pair scenes too (a
  hug, a handshake).
- You can set the game folder by hand. The app checks SKSE64 and the Address Library for your exact game version and gives
  links to them. If `Skyrim.ini` has no list of the game's archives, the app tells you.
- The plugin has no scene events, sounds, props or camera yet. The mod manager and the Script Studio work with Fallout 4
  only.

## Script Studio

<p align="center"><img src="docs/images/banners/studio.jpg" alt="Script Studio" width="100%"></p>

<table>
  <tr>
    <td width="50%"><img src="docs/images/studio-tree-builder.en.png" alt="The dialogue tree builder and the AI-dialogue section"></td>
    <td width="50%"><img src="docs/images/studio-tree-map.en.png" alt="The dialogue tree map: nodes and branches"></td>
  </tr>
</table>

In the Studio you make dialogues, scenes and your own mods. No programming and no Creation Kit.

- **Dialogue trees** in forms or YAML: lines, conditions (SPECIAL, relationship, flags, items, time), outcomes, gestures and
  G.A.M. scenes.
- **Branch map and checker.** The checker takes you straight to the mistake. Copy and paste nodes, **Ctrl+F**, rename with
  all references, versions with a diff.
- **Dialogue player:** click through your dialogue in the app. No build, no game.
- **Triggers:** entering a place, a time, a timer, a quest stage, a kill, an item. Actions: a message, a talk, a scene, a
  reward, a flag, moving something, a faction change, and more.
- **Dialogues for the game's and DLC characters** (Daisy, Vadim, settlers): your tree opens first in their normal talk. You
  can also add your own line to the wheel of a real game conversation.
- **Lines from the game itself:** a character says a vanilla line in their own voice.
- **Voice** from your recordings or a synthetic voice, with lip sync and a facial emotion. "🎙 Voice all" voices the whole
  file and shows the cost first for paid providers. Papyrus stubs are there if you need your own script.
- **"+ Story"** gives you a ready dialogue with two triggers to start from.
- **"Check in AI mode"** lets you talk to your dialogue the way the AI will play it.
- **Your mod as one `.ogmod`** with requirements. Another player drops the file onto the boopi_mod window, and everything
  installs and uninstalls together. You can publish the mod on boopi.site from the Studio.

Guide: [instructions/en/SCRIPT_STUDIO.md](instructions/en/SCRIPT_STUDIO.md).

## AI help and AI dialogue

<p align="center"><img src="docs/images/banners/ai-dialogue.jpg" alt="AI dialogue" width="100%"></p>

AI is optional. The mod manager, the Studio, G.A.M. and graphics work without it.

**In the tools,** AI writes a dialogue branch from a description, builds a scene from a sentence, and sorts the load order.

**In the game,** the "Progressive AI dialogue" mode adds "Say your own…" to the wheel. You type (Russian or English keyboard
layout) or hold **V** and speak. The character answers in character, with voice and a subtitle. They know who you are, what
happened between you, your S.P.E.C.I.A.L. and the story so far. A talk can lead to a date or to intimacy, if the character
wants it too.

<p align="center"><img src="docs/images/ingame-ai-hud.jpg" alt="In game: Piper Wright's reply as a subtitle and the relationship card" width="880"></p>
<table>
  <tr>
    <td width="50%"><img src="docs/images/ingame-ai-input.jpg" alt="The in-game input line: Russian text and ready-made replies"></td>
    <td width="50%"><img src="docs/images/ingame-ai-reply.jpg" alt="The character's answer and suggestions for the next line"></td>
  </tr>
</table>

- **The AI only asks; the core checks.** The AI can give an item, move a quest forward or start a scene, but only what this
  character's dialogue allows. It cannot break your game.
- **Memory:** characters remember past talks.
- **The game's own dialogues:** on an open wheel, press **T** and type what you want to say. The AI picks the matching
  answer on the wheel, and the quest goes on as designed. If no answer fits, the character answers in character. The "AI
  in vanilla dialogues" setting: off / pick the answer / pick the answer and free lines.
- **Talk to anyone:** press **T** in front of any person, robot or DLC character.
- **Outcomes** (flags, items, quest stages, gestures) happen in the game. HUD widgets are on **F10**.
- **Models:** OpenRouter, DeepSeek or OpenAI with your own key, or a local model with Ollama, LM Studio or any
  OpenAI-compatible server. A local model needs no key and no internet. Models of about 27B are enough for a conversation.
- **Your own trees** work in AI mode too: in the Studio you write who the character is and where the talk should go.

Voices and lip sync are in the [Voice](#voice) section. Guide: [instructions/en/AI_DIALOGUE.md](instructions/en/AI_DIALOGUE.md).

## "Life": relationships and the world

<table>
  <tr>
    <td width="50%"><img src="docs/images/characters-chat.en.png" alt="Chat with a character in the app"></td>
    <td width="50%"><img src="docs/images/life-people-reputation.en.png" alt="The Life page: people, reputation, achievements"></td>
  </tr>
</table>

Every NPC has their own attitude to you: affinity, trust and attraction. It changes with what you say, do and give.

- **Flirting and dates** in real places: a table at the club, a walk, a room for the night.
- **A night together** is a scene on our engine. Mood, relationship, drinks and the moment all count. They can say no.
- **Couple, proposal, wedding.** Partners live their own lives and get jealous.
- **Faction reputation, law, bounties.** Guards remember crimes. Settlers can be kidnapped.
- **Jobs for caps** and **diseases** (cold, flu, fever, poisoning, radiation sickness). Settlement doctors treat diseases
  and addiction.
- **Choose what defeat means:** death, captivity or a "bad ending".
- **27 key characters** with a backstory and memory. You can chat with them in the app before the game, edit their cards,
  or create your own.

## Boopi Corp. and the Black Acorn

- **The Black Acorn night club** near Diamond City: a bar, the singer Stella (you can win her over), a dance floor, a VIP
  room and rooms upstairs.
- **The Boopi Corp. HQ** with Gen 4 synths. Each one has her own job and story.
- **The Red Rocket** is now a bar for settlers.
- About a hundred people in these places are busy: they dance, drink, play cards, wash glasses, work at terminals. When you
  talk to someone, their scene stops.
- Even without animation packs, the waitresses walk around, guests have "standing" props (coffee, a paper, a cigarette), and
  from 19:00 to 01:00 idle people move around the hall. In the Red Rocket the card players sit at two tables.
- The system for pair scenes (cards, a dance, a talk at a table) is ready and tested in the game. The pair scenes
  themselves and the full life of these places come with our animation packs.
- "Life" dates and part of the ["Lullaby"](#lullaby-the-new-story) story happen here.

## "Lullaby": the new story

<p align="center"><img src="docs/images/banners/story.jpg" alt="Lullaby" width="100%"></p>

<p align="center"><img src="docs/images/in-game-main-menu.png" alt="The Fallout 4 main menu with boopi_mod" width="640"></p>

A new main story that replaces the vanilla one. It is a detective story.

- You are the second sleeper of Vault 111, in pod K-1. You are not Nora's spouse. The OldGenAI core wakes you sixteen days
  after Nora left to find her son. You need to find out who you are and who woke you.
- Four acts, 18 main missions, 13 side quests, 9 endings. The ending depends on your choices and your reputation.
- About 20–25 hours for the main story, 30+ with side quests. There is an evidence board, a cipher, mini-games and romance.
- **The whole story is voiced**, in Russian and English: about 46,000 lines, with a voice of its own for every character
  (see [Voice](#voice)).
- You play Vault 114, Fort Hagen, Kellogg's memory and the Glowing Sea yourself, as part of the new story. Other quests,
  companions, factions, settlements and DLC stay.

> [!NOTE]
> A **new game** is recommended for the story. "Life", chat and AI dialogue also work with old saves.

## Voice

<table>
  <tr>
    <td width="50%"><img src="docs/images/settings-voice-tts.en.png" alt="Text-to-speech providers: local engines and voice cloning"></td>
    <td width="50%"><img src="docs/images/settings-voice-stt.en.png" alt="Speech recognition and text-to-speech"></td>
  </tr>
</table>

- **"Lullaby" voicing** in Russian and English: about 24,000 Russian and 22,600 English lines, about 56 hours. It is part
  of the story pack and installs with it.
- **A voice of its own for every character:** 84 voices, designed from character descriptions with a local model. The hero
  has a voice for each sex. The game's people (Nick, Piper, Preston, Codsworth and others) sound similar, but the voices are
  new, not copies.
- **AI replies in real time:** a reply is spoken in parts while it is written, and the lips follow each part. On a loaded
  local engine the first sound comes in about half a second.
- **Text-to-speech engines:** Microsoft Edge TTS (works at once, no key), ElevenLabs, OpenAI TTS, Qwen3-TTS, Higgs TTS 3,
  XTTS-v2 and Silero. Qwen3-TTS, XTTS-v2 and Silero run locally; Qwen3-TTS runs on your NVIDIA GPU, one server per card.
- **Voice cloning** (Qwen3-TTS, XTTS-v2, Higgs TTS 3) from the game's own lines or from your recordings. A sample can be a
  single WAV file in `%APPDATA%\BoopiMod\speech\voices`. In the Studio, game characters get a sample of their own voice
  automatically.
- **Lip sync** is calculated from the recording itself. The face shows the line's emotion and blinks.
- **Speech recognition:** faster-whisper locally, or OpenAI Whisper. In the game: push-to-talk on **V**.
- The game's subtitles show in the right code page.
- Large engines install with a button. You accept the XTTS and Silero licences (non-commercial) yourself; Qwen3-TTS has
  the open Apache-2.0 licence.

Guide: [instructions/en/VOICE.md](instructions/en/VOICE.md).

## Graphics

<p align="center"><img src="docs/images/graphics-presets.en.png" alt="Graphics presets: PC detection and the recommended preset" width="880"></p>

12 presets, from integrated graphics at 720p and the Steam Deck to an RTX 4090 at 4K. The app checks your hardware and marks
the preset that fits. When you apply a preset, the app edits the game's INI files and makes backups.

## OldGen OS on the Pip-Boy

An app on the Pip-Boy (key **H** when nobody is in front of you): people, reputation and karma, dossiers, health, and 71
achievements (15 hidden).

## Content rules

The project has adult content (**18+**). The rules are built into the core. Settings and AI answers cannot change them:
romance and intimacy only between adults and with consent; no coercion; **a child never takes part in such scenes, under any
setting**.

## Limitations

- **In-game AI dialogue is a beta.** While a reply is spoken, the input line is hidden.
- **Lip sync:** one emotion per line. XWM voice without a `.lip` file does not move the lips.
- **Living places:** pair scenes wait for our animation packs. Guests do not come and go. After you start a talk, the scene
  can take up to ~8 s to finish.
- **Skyrim SE / AE is a beta** (see [above](#skyrim-se--ae-beta)). Papyrus calls were not checked in the game, and Special
  Edition 1.5.97 was not checked. Other games are not playable yet.
- **Role height:** the seat height is not fitted.
- **F.O.R.G.E.:** your own model is only a static object, with a box collision. No weapon paint swaps and no blending of the
  generated relief with the original yet. Items from level lists cannot be used for "this person only".
- **Your dialogues on game characters:** if a story quest of the game holds the character (for example Cassie or Kent), the
  quest goes first.
- **Fallout 4 versions.**
  - **Old-Gen 1.10.163.** Release 0.2.2 was not checked in an Old-Gen game: I do not have that version on my PC right now.
    The Old-Gen build of our plugins is made from the same code and passes the tests.
  - **Anniversary 1.11.191** is checked in the game: our menus, the text line and the HUD, lip sync and the face, "Life",
    the story start, G.A.M. scenes (pair scenes too), gestures, the scene camera and sounds, the main-menu logo. Not yet
    checked in the game: G.A.M. gaits and furniture scenes (they need the animation packs) and the Boopi icon on the
    Pip-Boy map.
  - **Next-Gen 1.10.980 / 1.10.984 and Anniversary 1.11.221 / 1.11.240:** the same code, everything on, not yet checked in
    the game. The plugin log marks those features as "new on this version". Safe mode, `[NextGen] bSafeMode=1` in
    `BoopiUI.ini` / `GAM.ini`, turns off what was not yet checked in the game on your version. The Anniversary addresses
    come from a second library (LucaDotGit/CommonLibF4), spot-checked against F4SE 0.7.7.
  - If the game crashes or something does not work, press "Settings → About → Diagnostics → Copy logs for a report" and
    attach the zip to your report.
  - **Buffout 4** is offered on every version: NG on Old-Gen and Next-Gen, AE on Anniversary. UFO4P and High FPS Physics
    Fix too. **MCM** on Anniversary is offered for 1.11.240 only: its "1.11.240" build runs on that version alone, and F4SE
    disables it on 1.11.191 / 1.11.221. Baka ScrapHeap is for Old-Gen only.
  - Anniversary 1.11.137 / 1.11.159 / 1.11.169: **our game plugins do not run** (no library has their addresses); F4SE
    will not load them. Update the game to 1.11.240.
  - F4SE 0.7.x and the Address Library for Next-Gen and Anniversary come from Nexus, through your own account. The app
    offers the right files, and the pre-launch check names them.
  - The Steam and GOG versions of the game are not tested.
- **The story** is a first edition. Its world and mini-games will get better. The voicing was checked in the game and by
  speech recognition: if a line sounds wrong, please tell me. After changing the game's language, reinstall our mods.
- **Release files are not code-signed**, so SmartScreen may warn you. Check the SHA-256.
- **Qwen3-TTS "This PC"** takes about 8.5 GB and needs an NVIDIA GPU with about 7 GB of free memory. **XTTS-v2** is about
  4.7 GB; an NVIDIA GPU is recommended.
- Windows only.

The limitations of this release are in the [0.2.2 notes](docs/release/v0.2.2.md#known-limitations).

---

## Install and first run

<p align="center"><img src="docs/images/banners/install.jpg" alt="Install" width="100%"></p>

### What you need


| What | Needed |
|---|---|
| System | Windows 10 (22H2) or 11, x64; WebView2 (part of Windows 11 and of an updated Windows 10) |
| Game | A legal copy of **Fallout 4**: Old-Gen 1.10.163, Next-Gen 1.10.980 / 1.10.984 or Anniversary 1.11.191 / 1.11.221 / 1.11.240 (1.11.191 is checked in the game, see [limitations](#limitations)). Anniversary 1.11.137 … 1.11.169 — without our game plugins, update the game |
| F4SE | Required, **not included**. Old-Gen: the app downloads it from the author's page when you press the button. Next-Gen and Anniversary: the app offers the right file on Nexus, and you download it with your own account |
| AI (optional) | An API key (OpenRouter, DeepSeek, OpenAI) **or** a local model (Ollama, LM Studio, any OpenAI-compatible server) |
| Internet | To install mods, and for the AI provider and online voices |
| Disk space | A few GB for the mod cache, about 1 GB of it for the story voicing. Optional: Qwen3-TTS about 8.5 GB, XTTS-v2 about 5 GB |

### Step 0. Download and unpack

1. Download **`boopi_mod-0.2.5-win-x64.zip`** from [Releases](https://github.com/boopi-coder/boopi_mod/releases/latest)
   and compare its SHA-256 with `SHA256SUMS.txt` from the same release. For 0.2.5:
   `9ba1eecdf97687201621a150c5d42394f8d1b3844a6a021b6fb4b2ce3314cea7`.
2. Unpack to a **short path**, for example `C:\Games\boopi_mod`. Windows does not run programs with a path longer than 260
   characters.
3. Run **`boopi_mod.exe`** and choose your language and game.
4. On the Dashboard press **"Download and install"** (our mods from [boopi.site](https://boopi.site), ≈ 1.2 GB with the story
   voicing, checked by SHA-256), then **"Restart the core"**. After that the mods update on their own.

> [!WARNING]
> The release files are not code-signed, so Windows SmartScreen may show a warning. Download only from the releases page and
> check the hash.

### Step 1. Dashboard

<p align="center"><img src="docs/images/dashboard.en.png" alt="Dashboard: the game is found, F4SE is installed, next steps" width="860"></p>

The app should find the game by itself: path, version, edition (Old-Gen, Next-Gen or Anniversary), F4SE status. At the top right the core
shows "online". The "Next steps" block shows what is left to do.

### Step 2. Game path (if the game was not found)

<p align="center"><img src="docs/images/settings-game.en.png" alt="Settings → Game: the Fallout 4 path" width="860"></p>

**Settings → Game** → the folder with `Fallout4.exe` → **"Check"** → **"Save"**. A folder you set by hand wins over
auto-detection.

### Step 3. Mods → "Base pack"

<p align="center"><img src="docs/images/mods-base-pack.en.png" alt="Mods: the base modding pack" width="860"></p>

Open **Mods** and install the base pack. Files from Nexus Mods need an account. Without Premium, press "Slow download" in the
Nexus window inside the app. Installed mods are listed on the right; you can remove any of them.

### Step 4. AI provider key (optional)

<p align="center"><img src="docs/images/settings-providers.en.png" alt="Settings → LLM providers: API keys and voice" width="860"></p>

**Settings → LLM providers** → paste the API key → **"Save key"** → **"Check"**. The **"Routing"** tab sets which model does
what. The key is kept in the Windows Credential Manager and is not shown again. A local model needs no key; the list has
ready entries for it.

### Step 5. Dialogue mode

<p align="center"><img src="docs/images/settings-dialogue-mode.en.png" alt="Settings → Dialogues: the Progressive AI dialogue mode" width="860"></p>

**Settings → Dialogues** → **"Progressive AI dialogue"** or "Vanilla". Answer length, voice and line suggestions are here
too.

### Step 6. Hero, graphics and "Play"

<p align="center"><img src="docs/images/install-play.en.png" alt="Dashboard: the Play button" width="640"></p>

1. **Hero:** the name and sex come from your latest save. Fill in the look and backstory; the characters will see them.
2. **Graphics → "Apply recommended"** (edits the game's INI files and makes backups).
3. **"Play"** starts the game through F4SE. AI dialogue and "Life" work at once; the story needs a new game.

### Where to find files

| What | Where |
|---|---|
| App logs | `%APPDATA%\BoopiMod\logs\` (`app.log`, `core.log`, `all.log`, `errors.log`) |
| Data and settings | `%APPDATA%\BoopiMod\` |
| Buffout 4 NG crash logs | `Documents\My Games\Fallout4\F4SE\crash-*.log` |
| API keys | Windows Credential Manager, service `BoopiMod` |

### "The core file is missing" or your antivirus complains

What the messages on the "Core is not responding" screen mean: [Guides → If the core does not respond](instructions/en/README.md#if-the-core-does-not-respond).

1. Most likely your antivirus moved `core\oldgenai-core.exe` to quarantine. This is a false alarm: the core is an unsigned
   Python program, and some antiviruses flag such programs by pattern.
2. Check the archive's SHA-256 (PowerShell: `Get-FileHash .\boopi_mod-0.2.5-win-x64.zip`). For 0.2.5:
   `9ba1eecdf97687201621a150c5d42394f8d1b3844a6a021b6fb4b2ce3314cea7`.
3. Restore the file from quarantine or add the boopi_mod folder to the exclusions, then unpack the archive again.
4. Unpack to a normal folder (not Program Files) and do not run the app from inside the zip.
5. Tell me your antivirus and the name of the detection, and I will report the false positive.

<details>
<summary><b>If something went wrong</b></summary>

- **Your game version is not in the list.** The app warns you but does not block the launch. What works on which version:
  see [limitations](#limitations).
- **`boopi_mod.exe` does not start.** Check that the path is short and WebView2 is installed. SmartScreen: "More info" →
  "Run anyway", after you check the SHA-256.
- **The AI is silent.** "Settings → LLM providers" → "Check". Check the key's balance, the "Dialogue" route and the mode on
  the "Dialogues" tab.
- **No voice.** "Settings → Voice" → pick a provider. Edge TTS needs the internet.
- **The game crashes.** "Settings → About → Diagnostics → Copy logs for a report" puts the logs of F4SE, our plugins and
  the crash reports into one zip (keys and personal paths are masked). Attach it to your report.

**Still not working?** [Open an issue](https://github.com/boopi-coder/boopi_mod/issues/new) with the app version, the steps
and the zip from "Copy logs for a report".

</details>

**What the app installs:** F4SE for Old-Gen and Buffout 4 NG from their authors' GitHub; F4SE for Next-Gen and
Anniversary, Address Library, UFO4P, High FPS Physics Fix, MCM, Baka ScrapHeap from the authors' Nexus Mods pages. The app builds our own plugins (`BoopiCorp.esp`, `OldGenStory.esp`,
posters, `boopi_hud`) and F4SE plugins (`OldGenAI.dll`, `BoopiUI.dll`, `GAM.dll`) and puts them into the game. All files are
checked by hash.

### Updates

The app checks for updates at every start and then every 30 minutes. You cannot turn this off. A banner on the Dashboard
tells you about a new version, and the "What's new" window installs updates with one button. To get an email for each
release, click **Watch → Custom → Releases** on GitHub.

---

## For modders

<p align="center"><img src="docs/images/banners/modders.jpg" alt="For modders" width="100%"></p>

| Guide | What it covers |
|---|---|
| [SCRIPT_STUDIO.md](instructions/en/SCRIPT_STUDIO.md) | Script Studio: dialogues, branches off the game, the AI block, voice, your own `.ogmod` mod |
| [ANIMATION_IMPORT.md](instructions/en/ANIMATION_IMPORT.md) | Animation import and the G.A.M. scene editor |
| [ANIMATION_GUIDE.md](instructions/en/ANIMATION_GUIDE.md) | Animations in dialogues and scripts: gestures, scenes, camera |
| [AI_DIALOGUE.md](instructions/en/AI_DIALOGUE.md) | AI dialogue: what the player sees, what the AI can and cannot do |
| [VOICE.md](instructions/en/VOICE.md) | Text-to-speech, speech recognition, voice cloning, lip sync |
| [FORGE.md](instructions/en/FORGE.md) | F.O.R.G.E.: catalog, recolouring, map generator, "My textures", texture packs, "My objects" |

All the guides are also [in Russian](instructions/README.md).

## FAQ

<details>
<summary><b>Are Next-Gen / Anniversary supported?</b></summary>

Yes. Next-Gen 1.10.980 / 1.10.984 and Anniversary 1.11.191 / 1.11.221 / 1.11.240 get one build of our plugins, with
everything on. Anniversary 1.11.191 is checked in the game: the same works as on Old-Gen, except G.A.M. gaits and furniture
scenes, not yet tried. On the other versions, please report problems. Anniversary 1.11.137 … 1.11.169 get no game plugins
of ours: update the game. Details are in
[limitations](#limitations). The app also reads Next-Gen and Anniversary BA2 archives and warns you if such an archive
goes into an Old-Gen game.
</details>

<details>
<summary><b>Do I need AI?</b></summary>

No. The mod manager, the Studio, G.A.M. and graphics work without AI. AI is needed for the assistant, AI dialogue and cloud
voices.
</details>

<details>
<summary><b>What about my old saves?</b></summary>

"Life", chat and AI dialogue work with old saves. The story needs a new game. Back up your `Saves` folder before you add or
remove plugins in the middle of a playthrough.
</details>

<details>
<summary><b>What goes to the internet, and where are my keys?</b></summary>

There is no telemetry. Dialogue lines and the hero's and character's data go to the AI provider you chose (OpenRouter,
DeepSeek, OpenAI). Text for voice goes to Edge TTS, ElevenLabs or OpenAI if you chose them. With a local model (Ollama,
LM Studio) and local Qwen3-TTS, XTTS, Silero and Whisper, nothing leaves your PC. The update check sends small requests to github.com
and boopi.site at start and every 30 minutes, with no data about you; it cannot be turned off. API keys are kept in the
Windows Credential Manager (service `BoopiMod`), not in files.
</details>

<details>
<summary><b>Is it safe for my game?</b></summary>

Mods install through a journal with full rollback. The journal is saved with a backup copy. Before launch the app checks
the game version, F4SE, the Address Library, the required mods and `Fallout4.ini`.
</details>

<details>
<summary><b>Can I share mods I make?</b></summary>

Yes. Mods you make in boopi_mod from your own work belong to you (see `NOTICE.txt`). Respect the rights of the authors of
anything you include.
</details>

<details>
<summary><b>Does the AI work in the game's normal quest dialogues?</b></summary>

Yes. On an open wheel, press **T** and type what you want to say. The AI picks an answer on the wheel, and the quest goes on
as designed. More in [AI dialogue](#ai-help-and-ai-dialogue).
</details>

<details>
<summary><b>Do the lips move on AI replies?</b></summary>

Yes, and on voiced Studio lines too. The lips are calculated from the recording (and from the text, if there is one). The
switch is `BoopiUI.ini [Audio] bLipSync`.
</details>

<details>
<summary><b>Is "Lullaby" voiced?</b></summary>

Yes, fully, in Russian and English. The voicing is part of the story pack (about 1 GB) and installs by itself. The voice
language is the language of your game. More in [Voice](#voice).
</details>

<details>
<summary><b>Can I put my own 3D model into the game?</b></summary>

Yes, as a static decoration: an OBJ, glTF or GLB through F.O.R.G.E. → "To the game as an object". You cannot sit on it or
put it in your inventory. More in [F.O.R.G.E.](#forge-3d-objects-and-textures).
</details>

<details>
<summary><b>Can I play other games?</b></summary>

Fully, only Fallout 4. Skyrim SE / AE has a [beta](#skyrim-se--ae-beta). I do not promise dates for other games.
</details>

<details>
<summary><b>Where do I report a bug or an idea?</b></summary>

In the [issues](https://github.com/boopi-coder/boopi_mod/issues/new): the app version, the steps and the zip from "Settings →
About → Diagnostics → Copy logs for a report". Questions from [Boosty](https://boosty.to/boopi_coder) supporters are answered first.
</details>

## What's coming

**Next release:**

- **The first animation pack**, after my hand polish.

**After that, no dates:**

- In-game checks on Next-Gen and the other Anniversary versions.
- Our other animation packs, including adult scenes made in G.A.M. With them the pair scenes of the places will work.
- Animation import and export in HKX, FBX, glTF and BVH. Animation from a video and a pose from a picture.
- F.O.R.G.E.: weapon paint swaps, blending a generated map with the original, exact collision and materials for your own
  objects.
- G.A.M.: build an animation pack in the editor, seat height fitted to the actor's height.
- Skyrim: scene events, sounds and props.
- NPCs talking to each other.

**Later:** group talks, side quests made by the AI, longer memory, more "Lullaby" and more of the club, a FOMOD installer and
mod profiles. Then other games: Cyberpunk 2077, Skyrim, Starfield, The Sims 4. What comes first depends on interest in the
project: [stars on GitHub](https://github.com/boopi-coder/boopi_mod/stargazers),
[your requests](https://github.com/boopi-coder/boopi_mod/issues/new/choose) and support.

## Support the author

boopi_mod is free and made by one person.

<table>
  <tr>
    <td align="center" width="50%" valign="top">
      <h3>🧡 Boosty subscription</h3>
      <a href="https://boosty.to/boopi_coder"><img alt="Support the author on Boosty" src="docs/images/support-button.png" width="300"></a><br><br>
      Regular support pays for development time: animation packs, F.O.R.G.E., all Fallout 4 versions, other games.
      Questions from Boosty are answered <b>first</b>.<br><br>
      <a href="https://boosty.to/boopi_coder"><b>boosty.to/boopi_coder</b></a>
    </td>
    <td align="center" width="50%" valign="top">
      <h3>💸 One-time donation for the server</h3>
      <a href="https://www.donationalerts.com/r/boopi_coder"><img alt="QR: donate via DonationAlerts" src="docs/images/crypto/qr-donationalerts.png" width="170"></a><br><br>
      For the <b>server</b>: updates, the mod catalog and packs on boopi.site. Card and other methods, no sign-up.<br><br>
      <a href="https://www.donationalerts.com/r/boopi_coder"><b>donationalerts.com/r/boopi_coder</b></a>
    </td>
  </tr>
</table>

## License

- boopi_mod is **freeware, all rights reserved.** You may use it for free and share the original archive with credit to the
  author. You may **not** sell it, change it, share changed versions or reverse-engineer it. Full text:
  [`LICENSE.txt`](LICENSE.txt); third-party components: [`NOTICE.txt`](NOTICE.txt). Mods you make with boopi_mod are yours.
- An unofficial project, not affiliated with Bethesda Softworks / ZeniMax Media. **Fallout** is a trademark of its owners.
  You need your own copy of the game.
- **In the archive:** 7-Zip (LGPL, unmodified, 7-zip.org); texconv from DirectXTex (Microsoft, MIT); CommonLibF4, fmt,
  spdlog, rsm-mmio (MIT) and boost-stl-interfaces (BSL-1.0) in our F4SE plugins; React, three.js, Tauri (MIT / Apache-2.0);
  IBM Plex fonts (SIL OFL 1.1); the core's Python libraries under their own licences.
- **Not in the archive, you download them:** F4SE, Buffout 4 NG, Address Library, UFO4P, High FPS Physics Fix, MCM, Baka
  ScrapHeap (their authors forbid or limit redistribution; the app only helps you download them from the official pages).
  XTTS-v2 (Coqui Public Model License) and Silero (CC BY-NC-SA 4.0) install on request, after you accept their terms.
  Qwen3-TTS (Apache-2.0) installs on request.
- Author: **boopi-coder** — [github.com/boopi-coder](https://github.com/boopi-coder).
