<p align="center"><img src="../../docs/images/banners/modders.jpg" alt="boopi_mod guides" width="100%"></p>

# <img src="../../docs/images/icons/mods.png" width="56" align="absmiddle"> boopi_mod guides

[🇷🇺 Русский](../README.md) · 🇬🇧 English · [← Back to the main page](../../README.en.md)

> **Modding has never been this easy.** boopi_mod is first of all a mod manager in which you **create**: your own animations,
> scenarios, scenes and dialogues — by hand or with AI help. These guides take you from the first minute to your own mod
> that you can share as a single file.

> [!WARNING]
> **This is a beta (0.2.5):** expect rough edges and bugs — please report them so I can fix them quickly. Feedback on
> problems and ideas is very welcome. [Open an issue](https://github.com/boopi-coder/boopi_mod/issues/new/choose)

## Where to start

| I want to… | Read |
|---|---|
| install and launch | [Install and first run](../../README.en.md#install-and-first-run) |
| choose the app's language | On the very first start the app asks for it (Русский / English; your Windows language is preselected) — later it changes in Settings → Language |
| choose the game and the theme | After the language the app asks for the game — see [Other games](#other-games); later Settings → Games & theme |
| make my own dialogue, scene, mod | [Script Studio](SCRIPT_STUDIO.md) |
| check a dialogue without starting the game | [«▶ Try the dialogue»](SCRIPT_STUDIO.md#31-play-try-a-conversation-without-the-game) |
| publish my mod to boopi.site | [Publish to boopi.site](SCRIPT_STUDIO.md#97-publish-to-boopisite) |
| import animations or draw my own | [Animation import and the G.A.M. editor](ANIMATION_IMPORT.md) |
| my own story: a world event → a talk, a scene, a quest | [Studio triggers](SCRIPT_STUDIO.md#12-triggers-your-own-story), quickest: [«+ Story» and the ready example](SCRIPT_STUDIO.md#128--story-and-the-ready-example) |
| call animations from dialogues and scripts | [Animations in mods](ANIMATION_GUIDE.md) |
| repaint a thing, clothes, furniture — your own textures | [F.O.R.G.E. — 3D objects and textures](FORGE.md) |
| free conversation with people in the game | [AI dialogue](AI_DIALOGUE.md) |
| voice and voice input | [Voice](VOICE.md) |
| remove boopi_mod from the game (or what is left after deleting it by hand) | [Removing boopi_mod](REMOVE.md) |

## Other games

boopi_mod is becoming a studio for several games. **Fallout 4 is available now**, and everything in these guides is for it.
**Skyrim Special Edition is a beta**: its BSA archives are read, its skeleton comes from the game itself, and G.A.M.
scenes convert to it and play in the game through our SKSE plugin **GAM for Skyrim**. Next, in order: **Starfield**,
**Cyberpunk 2077** and **The Sims 4**. On the first start, after the language, the app asks for the game: Fallout 4 and
Skyrim (beta) can be chosen, the others say "coming soon". Settings → Games & theme shows which games are on your computer
and what each one still needs, and changes the **theme**: every game has its own colour scheme (Fallout 4's green terminal
is the default), and you can turn on any of them now.

**Fallout 4 versions.** Everything in the guides is tested on **1.10.163 (Old-Gen)**; on **Anniversary 1.11.191** the
Papyrus bridge, Life, the AI dialogue with the text line and lip sync, the HUD and G.A.M.'s scenes are tested in the game.
Next-Gen (1.10.980 / 1.10.984) and Anniversary 1.11.221 / 1.11.240 get the same build with everything on: if something does
not work, please send us the logs from `Documents\My Games\Fallout4\F4SE`; `[NextGen] bSafeMode=1` in `BoopiUI.ini` / `GAM.ini`
turns off what was not yet checked on your version. 1.11.137 … 1.11.169 get no in-game plugins of ours — update the game. The
pre-launch check tells you which F4SE and Address Library your version needs.

Animations move between games: in the G.A.M. editor, **Other games** saves a scene for the Skyrim skeleton (or for the
shared canonical rig) and brings a scene of another game back. A pose looks the same on the other body, and a round trip
loses nothing. Details: [Animation import and the G.A.M. editor](ANIMATION_IMPORT.md).

### Skyrim (beta)

What works:
- **Archives.** boopi_mod reads the game's archives itself (Special Edition and Legendary Edition BSA), no other tools.
  With Skyrim chosen in Games & theme, F.O.R.G.E. shows Skyrim's models and textures (viewing only for now).
- **Skeleton.** Settings → Games & theme → Skyrim (beta) → Read the skeleton from the game takes `skeleton.nif` from your
  game (a skeleton mod installed as a loose file wins over the archive). Scenes convert onto this skeleton.
- **The in-game player.** **GAM for Skyrim** is our SKSE plugin. It drives the character's bones from a G.A.M. scene
  itself, like GAM.dll in Fallout 4: no HKX files and no behaviour graphs are needed.

How to set it up:
1. Install **SKSE64** and **Address Library for SKSE plugins** yourself from their official pages (boopi_mod does not
   ship other authors' files). SKSE64 must match your game version exactly: the Skyrim panel in Settings names the file
   (`skse64_1_6_1170.dll` for 1.6.1170, which is SKSE64 2.2.6 from the archive of builds on the SKSE site). If Skyrim
   is in an unusual folder, set it there too (Game folder).
2. Settings → Games & theme → Skyrim (beta) → Install GAM for Skyrim. Only our files go into the game's `Data`
   (`SKSE\Plugins\GAMSkyrim.dll`, `Scripts\GAMSkyrim.pex`); Remove our files takes them out again.
3. In G.A.M., open a scene → Other games → Skyrim Special Edition → **Install into Skyrim**.
4. In the game open the console (`~`), select a character (a click or `prid`) and type `gam play <scene>`, by name
   (`gam play wave`) or by id in quotes (`gam play "boopi/wave"`; without quotes the console reads `/` as a division).
   With nobody selected a scene of one plays on you; a scene of two takes you and the selected character. More commands: `gam list` (the scenes), `gam stop`, `gam stopall`, `gam reload` (read the scenes
   again without leaving the game). From Papyrus scripts: `GAMSkyrim.PlayOn(akActor, "boopi/<scene>")`.

> [!WARNING]
> This is a beta. Checked in the game on Skyrim Anniversary Edition 1.6.1170 with SKSE64 2.2.6: a gesture and a dance on
> you and on an NPC, a hug and a handshake for two. If Skyrim crashes when it loads any world (even without mods), look at
> the Skyrim panel: most often your `Skyrim.ini` lists none of the game's archives. If something behaves oddly, send
> `Documents\My Games\Skyrim Special Edition\SKSE\GAMSkyrim.log`. The mod manager, launching the game and Script Studio
> still work for Fallout 4 only.

## All guides

<table>
  <tr>
    <td width="72" align="center"><img src="../../docs/images/icons/studio.png" width="64" alt=""></td>
    <td><b><a href="SCRIPT_STUDIO.md">Script Studio</a></b> · <a href="../SCRIPT_STUDIO.md">RU</a><br>
    Your own dialogues, lines from the game and branches off its wheels, voice with lip sync, "Try the dialogue" without the game
    and file versions, "Build and check", your own mod (<code>.ogmod</code>), installing someone else's and publishing to
    boopi.site, animations in lines, triggers of your own story ("+ Story" and a ready example), Papyrus, the AI assistant and
    "Check in AI mode".</td>
  </tr>
  <tr>
    <td align="center"><img src="../../docs/images/icons/import.png" width="64" alt=""></td>
    <td><b><a href="ANIMATION_IMPORT.md">Animation import and the G.A.M. editor</a></b> · <a href="../ANIMATION_IMPORT.md">RU</a><br>
    Fallout 4 mods, Skyrim animations, OAR gaits, "drop it — it plays", your own scenes in the 3D editor: the
    Rotate / Move / Character / Heading tools, IK handles, lighting, a scene's face and camera, the AI animator, the scene library.</td>
  </tr>
  <tr>
    <td align="center"><img src="../../docs/images/icons/gam.png" width="64" alt=""></td>
    <td><b><a href="ANIMATION_GUIDE.md">Animations in G.A.M. mods</a></b> · <a href="../ANIMATION_GUIDE.md">RU</a><br>
    A gesture and a scene, scene events, the camera, calling from scripts, dialogues and "Life", scene files, a mod for the manager,
    checking in the game, safety.</td>
  </tr>
  <tr>
    <td align="center"><img src="../../docs/images/icons/forge.png" width="64" alt=""></td>
    <td><b><a href="FORGE.md">F.O.R.G.E. — 3D objects and textures</a></b> · <a href="../FORGE.md">RU</a><br>
    Any 3D object of your game with its textures: a catalog with the game's names, the 3D view, texture slots, «Save as PNG»,
    a new picture → DDS with mipmaps and a live preview, «My textures» in the game through the journal, a <code>.ogmod</code>
    texture pack, your own OBJ / glTF / NIF models.</td>
  </tr>
  <tr>
    <td align="center"><img src="../../docs/images/icons/ai-dialogue.png" width="64" alt=""></td>
    <td><b><a href="AI_DIALOGUE.md">AI dialogue</a></b> · <a href="../AI_DIALOGUE.md">RU</a><br>
    The "Progressive AI dialogue" mode: how to switch it on, "Say your own…", keyboard input (Russian included), voice on
    <b>V</b>, widgets on <b>F10</b>, what the AI can and cannot do; for modders — checking a dialogue in AI mode.</td>
  </tr>
  <tr>
    <td align="center"><img src="../../docs/images/icons/voice.png" width="64" alt=""></td>
    <td><b><a href="VOICE.md">Voice</a></b> · <a href="../VOICE.md">RU</a><br>
    Text-to-speech (Edge, ElevenLabs, OpenAI, Qwen3-TTS, Higgs TTS 3, XTTS-v2, Silero), voice cloning, speech recognition and push-to-talk.</td>
  </tr>
</table>

## Updates

The app keeps everything fresh by itself: **at every start** it checks for a new version of the app (GitHub releases)
and new content of our mods (packs from boopi.site, signature checked), then **every 30 minutes** while it is open. No
network — the check quietly tries again in a few minutes, nothing hangs.

When something new is found, the **"What's new"** window opens:

- **a new app version** — the release's list of changes; **"Install"** downloads it, **"Restart and update"** installs
  it (your data in `%APPDATA%\BoopiMod` is never touched);
- **new in our mods** — what changed in each pack; **"Install"** downloads the packs, the app reads them **at once** (no
  restart) and right away updates our mods in the game (the OldGenAI and G.A.M. plugins, Boopi Corp., the posters, the
  map icons…) through the mod manager's journal: the old version's files are replaced by the new ones;
- **our mods in the game are older than the app** (after an app update, say) — the same update of the mods in the game;
- **an old copy of one of our files sits in the game** that the app no longer counted as its own (say `OldGenStory.esp`
  or `BoopiCorp.esp` installed before the journal, or a file the game held open during an earlier update) — the window
  lists such files and **"Install"** replaces them with the mod's version. The app knows its files by their content: it
  must be the exact build of one of our versions. The old copy is kept in the journal and comes back if the mod is removed;
- **your own copy is used instead of the mod's file** (you edited `OldGenStory.esp` in an editor, or put someone else's
  file with the same name there) — the app **never touches it** by itself and only asks: "Your own copy of … is used
  instead of the file of … — replace it with the mod's version?". **"Replace with the mod's version"** swaps that one file
  (through the journal: your file is kept and comes back when the mod is removed), **"Later"** keeps yours.

While **Fallout 4 is running**, nothing in the game is touched: the window asks you to close the game — close it and
press **"Retry"**. **"Later"** hides the window until a check finds something newer still. To check by hand: Settings →
About → "Check now".

## If the core does not respond

The app window works with the boopi_mod core (`core\oldgenai-core.exe`) at `http://127.0.0.1:47800`. The address is
fixed: the game's plugins talk to the core there too, so the app never moves the core to another port. When there is no
connection, the "Core is not responding" screen says why:

| Title | What happened | What to do |
|---|---|---|
| **The core file is missing** | The program folder has no `core\oldgenai-core.exe` — almost always an antivirus removed it or put it in quarantine (a false alarm: the core is an unsigned program built with Python) | Restore the file from the quarantine, add the boopi_mod folder to the antivirus exclusions, or unpack the archive again |
| **The core runs, but the app cannot connect to it** | The core is running, but the window is not let through to it: an antivirus web protection, a firewall or a proxy intercepts local connections to `127.0.0.1` | Add `boopi_mod.exe` and `core\oldgenai-core.exe` to the antivirus exclusions (or allow them local connections), or switch off HTTPS/web scanning for `localhost`; a system proxy must bypass local addresses |
| **The core's port is used by another program** | The address `127.0.0.1:47800` is taken by another program (often an old OldGenAI or boopi_mod). The screen names it: "The port is held by: python.exe (PID: 4242)" | Close that program in Task Manager (the Details tab, PID column) |
| **The core could not be started** / **The core keeps stopping** | The core started and crashed | The reason is in `core.log` and `errors.log` in the logs folder |

After the fix press **"Check again"**. Every such screen has:

- **"Details"** — what the app sees (the core port is free / taken by another program / the boopi_mod core answers) and
  the last lines of `core.log` and `app.log`;
- **"Open the logs folder"** — `%APPDATA%\BoopiMod\logs` in Explorer;
- **"Copy diagnostics"** — the version, the problem code, what is on the port and the last lines of the logs as one text.
  If nothing helps, paste it into an [issue](https://github.com/boopi-coder/boopi_mod/issues/new) or a message to the author.

## Paths used in the guides

| What | Where |
|---|---|
| Data and settings | `%APPDATA%\BoopiMod\` |
| Your dialogues | `%APPDATA%\BoopiMod\talk` |
| Versions of studio files | `%APPDATA%\BoopiMod\talk\.history` |
| Installed studio mods | `%APPDATA%\BoopiMod\studio_mods` |
| Record ranges of the trees | `%APPDATA%\BoopiMod\plugin\tree_slots.json` |
| G.A.M. scenes | `%APPDATA%\BoopiMod\gam\scenes` |
| Your G.A.M. contexts | `%APPDATA%\BoopiMod\gam\contexts` |
| Scenes for other games | `%APPDATA%\BoopiMod\gam\exports` |
| Saved mods | `Documents\BoopiMod\Mods` |
| Your F.O.R.G.E. textures | `%APPDATA%\BoopiMod\forge\textures` |
| Textures saved as PNG | `Documents\BoopiMod\Textures` |
| Logs | `%APPDATA%\BoopiMod\logs` |
| The list of installed mods and the journal of files in the game | `%APPDATA%\BoopiMod\mods.json`, `%APPDATA%\BoopiMod\deploy\deploy_state.json` (with `.bak` copies beside them; keep them — they let a mod leave the game byte for byte) |
| The program | usually `C:\Games\boopi_mod` |
