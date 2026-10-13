<p align="center"><img src="../../docs/images/banners/studio.jpg" alt="boopi_mod Script studio: your own dialogues, scenes and branches off the game's dialogue wheels" width="100%"></p>

# <img src="../../docs/images/icons/studio.png" width="56" align="absmiddle"> Script studio: your own dialogues, scenes, voice-over and mod

[🇷🇺 Русский](../SCRIPT_STUDIO.md) · 🇬🇧 English

[All guides](README.md) · [Project home page](../../README.en.md)

**boopi_mod is first of all a mod manager in which you CREATE**: your own animations, scenarios, scenes and dialogues — by hand or with AI help. *Modding has never been this easy.*

**«Script studio»** (the menu item right after G.A.M.) is the part where dialogues and everything around them are made: your own conversation trees, branches off the dialogue wheel of the game itself, voice-over, gestures and scenes right inside the lines, AI dialogue for your own person, and a finished mod in one `.ogmod` file that another player installs into boopi_mod by dragging it in. No programming needed.

> [!NOTE]
> **⏱ In 1 minute**
>
> - **What it is.** The boopi_mod section where you make dialogues for the game's characters or for your own mod without code: in forms or in YAML.
> - **The fastest path.** «Script studio» → **«New»** → pick a character → build the conversation in the builder → **«To the game»** → in the game press **E** on the character.
> - **Branches off the game.** Your own choice right on the wheel of a vanilla dialogue («From the game» → a scene → «Branch») and your own branch behind it.
> - **Voice and animations.** Your own recordings or synthesized voice («Voice with AI»), G.A.M. gestures and scenes in the lines.
> - **AI helps.** The AI helper writes branches and Papyrus scripts from a description, and in «AI dialogue» your person talks freely; you check the result in the test chat **«Check in AI mode»**.
> - **What you get.** One `.ogmod` file in `Documents\BoopiMod\Mods`: dialogues, voice and scenes travel together; another player drops it into the boopi_mod window and presses «To the game».

<p align="center"><img src="../../docs/images/studio-tree-builder.en.png" alt="The dialogue tree builder: flags, the «AI dialogue» section, the check and the AI helper on the right" width="860"></p>
<p align="center"><em>The tree builder: flags, the «AI dialogue» section, the check and the AI helper on the right.</em></p>

## Contents

1. [How it works](#1-how-it-works)
2. [Your first conversation in 5 minutes](#2-your-first-conversation-in-5-minutes)
3. [The studio tabs](#3-the-studio-tabs)
4. [Bundled trees as a model](#4-bundled-trees-as-a-model)
5. [Lines from the game and branches](#5-lines-from-the-game-and-branches)
   - [5.1 Start from a scene](#51-start-from-a-scene)
   - [5.2 A branch: your own choice on the game's wheel](#52-a-branch-your-own-choice-on-the-games-wheel)
6. [Voice-over for lines](#6-voice-over-for-lines)
7. [«Build and check»](#7-build-and-check)
8. [AI dialogue: a person who talks on their own](#8-ai-dialogue-a-person-who-talks-on-their-own)
9. [Your own mod: save and share](#9-your-own-mod-save-and-share)
10. [The AI helper](#10-the-ai-helper)
11. [Papyrus scripts for your own mod](#11-papyrus-scripts-for-your-own-mod)
12. [FAQ](#12-faq)
13. [What to read next](#13-what-to-read-next)

Tags and scenes are taken from what you already have installed in the game and in the G.A.M. library.

---

## 1. How it works

In the studio you make:
- your own **dialogue trees** for the game's characters or for your own mod — in forms or in YAML;
- **branches off the game's own dialogues**: your own choice on the wheel of a vanilla conversation and your own branch behind it;
- **voice-over** for lines: your own recordings, synthesized voice and lip sync;
- **animations right inside the lines**: a nod, a gesture, a scene of the two after the talk;
- **Papyrus scripts** for your own mod in the Creation Kit: ready templates or written from a description by the AI;
- **AI dialogue** for your own person: who they are, where the talk should lead, while the outcomes come from your nodes — checked in a test chat;
- **your own mod**: everything you made in one `.ogmod` file that another player drops into boopi_mod; dialogues, voice and G.A.M. scenes travel together.

The path from a file to the game:

```
 your .yaml files (%APPDATA%\BoopiMod\talk)        studio: builder / YAML / map / check / AI
 + voice recordings (talk\audio)                   «From the game»: lines of the game's characters, branches
 + mods of other players you installed (.ogmod)
          │
          ▼  «To the game»
 BoopiCorp.esp is rebuilt: bundled trees + yours + from mods (trees with errors are skipped),
 voice goes to Data\Sound\Voice\BoopiCorp.esp\<the character's voice type>\
          │
          ▼
 in the game: E on a character → your conversation; on the game's wheel → your branch; lines are spoken with your recordings
```

- Your files live in `%APPDATA%\BoopiMod\talk\*.yaml`, in the same format as the game's bundled trees (`data/talk`).
- Your trees are built into the plugin **after** the bundled ones. This way the records of bundled trees, which saves remember, never shift.
- A tree with errors stays a draft: the file is saved, but the tree does not go into the game until the errors are fixed.
- The hash of your files, recordings and installed mods is part of the plugin version (`2.4.4-u1a2b3c4d`). Change something — the manager sees an update, and «To the game» rebuilds the plugin.

> [!NOTE]
> This guide is about working in the program.

---

## 2. Your first conversation in 5 minutes

**Step 1. Create a file.** Press **«New»** and fill in:
- the file name (`my_barman`);
- the tree id;
- **who speaks** — start typing the character's name (`Preston`, `Piper`, `Maxson`) or their editor id and pick from the list. Story characters (companions, factions, DLC) come first, the other NPCs of the game are found by name or editor id. For an NPC of your own mod, use its editor id, with a star if you like: `MyModBarman*`;
- the title.

You get a small working tree: a greeting, the question «Who are you?» with a nod, and «I have to go».

**Step 2. Build the conversation in the builder.** Its sections:
- **Tree** — who speaks (search by name or editor id; the chip shows the name), the title, the flags (what the game will remember: `met`, `told_secret`…), whether they are a trader.
- **Greetings** — what the character says on E. The first one whose conditions hold fires, so the last one must have no conditions.
- **Nodes** — every choice wheel, up to 4 hero choices (↑ question, ← left, → right, ↓ bottom). At the top you can see how the wheel looks in the game.
- **A hero choice** — the label on the wheel (up to 40 characters), a «Life» action (`compliment`, `flirt`, `hug`… — the core decides the outcome), where to go next, conditions and consequences.
- **The character's answers** — answer groups. If a choice has an action, a group can have an outcome: `ok` — it worked, `no` — a refusal, `later` — it was done recently… Text variants are written one per line, the game picks a random one.

<p align="center"><img src="../../docs/images/studio-tree-builder.en.png" alt="The builder: the my_rr_marge tree — who speaks, title, flags and the «AI dialogue» section" width="860"></p>
<p align="center"><em>The «Tree» section of the builder: who speaks, priority, title and flags; on the right — the «Check» and the «AI helper».</em></p>

**Step 3. Add an animation to a line.** Every answer has an «Animation» field:
- *by tags* — a gesture from the installed scenes. Under the field you see how many scenes fit. If it says «no scene in the game fits», install a pack with such tags;
- *a Life context* — the core picks the scene. Intimate contexts are marked «consent only»;
- **Who**: the character, the hero or both (then it is a scene with a camera);
- **Part of the body**: head — a nod, upper body — a gesture, arms, one arm…;
- **When**: during the line (a gesture) or after the talk (a scene).

**Step 4. Watch the «Check».** It is on the right and runs by itself a second after an edit. A click on an error opens the right place.

**Step 5. Save and send to the game.** **Ctrl+S** or «Save». Then **«To the game»**: close the game, the plugin is rebuilt. Start the game and press E on the character.

> [!TIP]
> Don't want to start from scratch? Open «Bundled» and press «Start from this» ([section 4](#4-bundled-trees-as-a-model)): a ready tree becomes your copy with a new id.

---

## 3. The studio tabs

| Tab | What is there |
|---|---|
| **Builder** | Everything in forms: the file's trees, greetings (or a branch off the game), nodes, choices, answers, voice-over, animations, conditions and consequences |
| **YAML** | The same file as text — for those who know the format or paste something ready-made. The builder and YAML always show the same thing |
| **Map** | The conversation as a diagram: greeting → nodes → end. Red marks a node nobody reaches or one with no way out. A click opens the node in the builder |
| **Papyrus script** | Script templates for your own mod in the Creation Kit, and an AI that writes a script from a description |

<p align="center"><img src="../../docs/images/studio-tree-map.en.png" alt="The «Map» tab: the dialogue tree's nodes, branches and transitions" width="860"></p>
<p align="center"><em>The «Map» tab: the greeting, the nodes and the transitions between them. Red highlights a dead-end node.</em></p>

**Conditions and consequences** in the builder are «key: value» lines:
- a condition `flag` = `met`, `stage` = `">=friend"`, `trust` = `">=40"`, `time` = `night`;
- a consequence `set` = `met`, `affinity` = `+5`, `give` = `{ item: NukaCola, count: 2 }`, `after` = `trade`.

The list of keys is suggested as you type.

---

## 4. Bundled trees as a model

«Bundled» are all the trees that ship with boopi_mod (Stella, the club, Red Rocket, the story…):
- you can open them and see how they are made;
- **«Start from this»** — a copy with a new id becomes yours.

> [!WARNING]
> If your tree speaks for the same character as a bundled one, the check warns you: in the game, on E, the one with the higher priority fires (`priority`, 45 by default). Raise the `priority` of your tree if you want it to answer.

---

## 5. Lines from the game and branches

The **«From the game»** button is next to «Bundled». Find a character by name and you see everything they say in Fallout 4 and the DLCs:
- by quest: **scenes** (how many dialogue wheels and lines they have) and separate **lines** marked «greeting», «in passing», «combat»… with the game's conditions (`GetStageDone(MQ102) == 1` — after such-and-such quest stage);
- a scene can be opened and read in order: what they say, the wheels with the hero's choices (the wheel label is in brackets) and their answers. The faded lines belong to the other participants of the scene.

### 5.1 Start from a scene

**«Start from this»** on a scene with a wheel creates a new file: the scene's wheels in order, the hero's choices and the answers as in the game. Choices that the game shows only under quest conditions are taken as they are visible by default; the answers for the heroine and the hero are kept through `when: { player: female }`. This is a new conversation for the same character — the vanilla one is not changed. If the character already has a bundled tree (Preston, Piper…), the check warns you about priority.

### 5.2 A branch: your own choice on the game's wheel

This is how you build your own branch right into the game's conversation — for example, on Arturo's first wheel «Какие слухи?» («What rumours?») appears in place of «Maybe», your branch is behind it, and from it you go back to his wheel.

1. «From the game» → the character → open a scene.
2. At the wheel you need, at the slot you need (↑ ↓ ← →), press **«Branch»**. Set the label of your choice (up to 40 characters) and the file name → «Create». The file opens in the builder.
3. In the builder, in place of greetings, there is the **«Branch from the game»** card: the scene, the wheel and the slot; the label; what the hero says (optional) and the voice-over of that phrase; the **condition under which the choice is shown**; the first node of the branch.
4. The branch is made of ordinary nodes. In «Next» there is **«↩ back to the game»** — back to this wheel of the game, and «■ end of the talk».
5. «Save» → «To the game».

What you need to know:
- The wheel has exactly 4 slots: your choice **takes a slot**, and the vanilla choice there is not visible while yours is available. Without a condition — always.
- If the vanilla choice moves a quest (starts a scene, sets a stage), «Build and check» warns you: set a condition (for example, `flag: met` of your own tree or a quest stage), otherwise the quest may get stuck.
- The empty top slot of traders is filled by the game with its own story choices («The search for Shaun») — a branch does not fit there, and there is no button.
- Branches can so far be made off scenes of the base game (not DLC).
- Other mods that change the same quest (for example, the unofficial patch) are shown in «Build and check».

> [!IMPORTANT]
> Don't hide a vanilla choice that moves a quest unconditionally. Always set a visibility condition for your choice — then the game doesn't lose the choice it needs.

---

## 6. Voice-over for lines

Greetings, the character's answers, the hero's phrases («More» → «The hero's full line») and the entrance of a branch have a **«Voice»** field: one recording per text variant, for Russian and English separately.

**Step 1. Add a recording.** «Voice» → at the variant you need press **«Upload…»** → choose a file:
- **WAV** — PCM 16 bit, mono, 44100 or 48000 Hz (this is what all recording and voicing programs write);
- **XWM** — the game's already compressed sound;
- **FUZ** — a ready line file of the game (sound and lip sync in one);
- or the **«Voice with AI»** button: the text of this variant is voiced by the service selected in «Settings → LLM providers» (Edge, ElevenLabs, OpenAI, Piper, XTTS…; the «Who speaks» list picks the voice), and the WAV is put into the recordings at once. Voice setup — [VOICE.md](VOICE.md).

<p align="center"><img src="../../docs/images/settings-voice-tts.en.png" alt="Settings: the Piper, XTTS-v2 and Silero TTS voice engines" width="860"></p>
<p align="center"><em>The voice engines in the settings (here Piper, XTTS-v2 and Silero TTS): the one marked «Voice with this» speaks your lines when you press «Voice with AI».</em></p>

**Step 2. Make the lip sync.** You make the `.lip` file (so that the lips move) yourself — in the Creation Kit (the 32-bit editor from `Tools\LipGen`), FaceFXWrapper (used by xVASynth and Yakitori Audio Converter) or another program — and upload it with the **«+ .lip»** button next to the recording. Without a `.lip` the sound plays, the lips don't move. A FUZ already has lip sync inside.

**Step 3. Listen.** A WAV can be played right in the studio.

**Step 4. Save and send to the game.** «Save» → «To the game».

On build, the WAV is compressed by `Tools\Audio\xwmaencode.exe` from the **Creation Kit** (it must be installed in the game folder; without it upload XWM or FUZ), glued with your `.lip` into a `.fuz` and put into the voice folder of whoever speaks: for a character — their voice type from the game (Arturo's is `NPCMArturo`), for the hero — `PlayerVoiceFemale01` / `PlayerVoiceMale01` (for a phrase with `{p:…|…}` — its own recording in its own folder). Checked in the game: the line sounds with your recording, and the subtitle stays as long as it lasts.

The recordings are in `%APPDATA%\BoopiMod\talk\audio`.

> [!NOTE]
> Recording file names must be in Latin letters (the studio renames them by itself).

> [!TIP]
> No Creation Kit? Upload a ready **XWM** or **FUZ** — they need no encoder.

---

## 7. «Build and check»

A button in the file list. The plugin is built the same way as for «To the game», but **nothing is installed into the game** — it is a check for whoever prepares a mod. The build takes about a minute. In the report (a click on a row opens the place):
- the errors and warnings of all files, the trees that did not make it into the plugin, and why;
- the plugin is read back: how many records it has and how big it is;
- **voice-over**: the file is there, the format plays, a `.lip` is next to it, an encoder for WAV is available;
- **branches**: the slot's vanilla lines move a quest (a condition is needed); which mods of your load order change the same quest or topic and what follows from it;
- **animations** by tags for which no installed scene exists (nothing will play).

> [!TIP]
> Run «Build and check» before you save a mod for others: you will see the same thing the game will see at the recipient's.

---

## 8. AI dialogue: a person who talks on their own

If the player has the «Dialogues: AI» mode on (Settings → Dialogues → «Progressive AI dialogue»; [AI_DIALOGUE.md](AI_DIALOGUE.md)), your person talks freely, while **the outcomes come from your nodes**. Whatever your choice in the tree opens (flags, items, caps, a quest stage, «after the talk», a gesture or a scene), the AI may issue when the conversation has really got there — with the same `when` conditions, flags and globals as in an ordinary dialogue. It works the same way for bundled trees, your own and the trees of installed mods. Trees with errors (drafts) do not go into the game, so the AI does not see them either.

<p align="center"><img src="../../docs/images/settings-dialogue-mode.en.png" alt="Settings, the «Dialogues» tab: the «Progressive AI dialogue» mode" width="860"></p>
<p align="center"><em>Settings → Dialogues: the «Progressive AI dialogue» mode, the model route and the reply length.</em></p>

Without an `ai` block everything works by nodes: goals, topics and the greeting come from the tree. The block **only narrows or colours** the conversation — the safety and «Life» rules are above it, it cannot open what they have closed.

### 8.1 The «AI dialogue» section

In the builder, under the tree's flags; it unfolds on a click (see the builder screenshot at the start of this guide).

1. **Who they are** — manner, character, what matters to them (up to ~900 characters; in Russian and in English; the model reads this every turn).
2. **Where a talk with them should lead** — the person's goal («sell the hero a couple of stimpaks, but not for free»).
3. **Only these kinds of talk** — small talk, asking around, about the mission, persuade, trade, flirt, romance, intimacy, have a drink, pressure, apologize. Nothing chosen — all that fit are open.
4. **Closed kinds of talk** — what the person will never support (wins over the previous item).
5. **Story hints** — short texts with a `when` condition («you have not met yet», «the deal was done, you are friends»); shown to the model while the condition holds.

A closed kind is not offered to the player and does not start.

> [!NOTE]
> The check warns you if a text is written in only one language: write both in Russian and in English.

### 8.2 The check: «Check in AI mode»

The button in the «AI dialogue» section opens a test chat with the person from the tree — as it is in the editor right now (even unsaved and with errors):
- on the left choose the **kind of talk**, the **hero's sex**, **SPECIAL**, the relationship **stage**, level and caps, set the **flags** you need and press **«Start»**;
- in the left column under the button — the **goals open now** (choices of the tree that the AI may «take», with the flags they set);
- talk: under each answer you see what fired (**goal, flag, item, quest, animation, achievement**), and if the core refused — in what and why.

<p align="center"><img src="../../docs/images/studio-ai-test-chat.en.png" alt="The «AI mode» test chat: an in-character reply, the goals and flags that fired" width="860"></p>
<p align="center"><em>The test chat: an in-character reply, and under it the goals and flags that fired.</em></p>

The test runs in a separate save, `studio-test`, and does not touch your real saves; a model key for dialogues is needed. «Start again» forgets the flags and the memory of earlier checks.

> [!IMPORTANT]
> The AI never goes around the hard rules, whatever it is asked and whatever the author writes in the `ai` block: only adults in romance, intimacy only through a «Life» action and the core's consent, no explicit text, never «forced», captives or animals.

---

## 9. Your own mod: save and share

### 9.1 Save a mod

**«Save the mod»** (in the file list):
1. Name, author, version (`1.0`), description.
2. Mark the **dialogue files** (files with errors are not taken — fix them).
3. If you like, mark **G.A.M. scenes** from your library (search by name or tags) — your mod's own animations.
4. «Save». The mod appears in `Documents\BoopiMod\Mods\<name>-<version>.ogmod`, with a «Show in folder» button.

A mod contains: your trees and branches, `ai` blocks, the voice recordings they name (with `.lip`), and the selected G.A.M. scenes. If a scene plays clips from somebody else's pack, the mod remembers which plugins are needed and shows it on install.

<p align="center"><img src="../../docs/images/gam-editor-ik-ai.en.png" alt="The G.A.M. animation engine editor: a pose, IK handles and the AI animator" width="860"></p>
<p align="center"><em>The editor of G.A.M. — the animation engine: you make your own scenes here, then mark them in «Save the mod».</em></p>

### 9.2 Install somebody else's mod

Drag an `.ogmod` into the boopi_mod window — onto «Script studio» or onto the «Mods» page. The mod is checked (integrity, trees, id clashes with yours and with other mods) and appears in the studio in the **«Installed mods»** section: you can look at it and remove it (✕). Then **«To the game»** — and the mod works: it is built together with your trees, in the language of your game, with its own record numbers (it does not overlap with other mods).

### 9.3 A mod's scenes go into the game at once

On install, the G.A.M. scenes from the mod go into your library and, if the game is found, into `Data\GAM\Scenes` — like the «To the game» button on the G.A.M. page. Animations by tags in the mod's lines find only what is already installed in the game, so without this step they would stay silent. A scene with the same id that you made yourself is never overwritten (the install refuses with a clear reason); when the mod itself is updated, its scenes are replaced. Removing a mod (✕) removes its scenes from the game too.

> [!NOTE]
> Why a mod is the sources and not a finished esp: the trees work on boopi_mod's quests and scripts, so the mod is for boopi_mod anyway, and built at the recipient's it adapts to their game and their other mods.

---

## 10. The AI helper

You need an API key of any AI provider in the settings. The model is chosen in «Settings → Routing → Script studio».

**Trees.** Describe what you need, for example: «add a node where the barman tells rumours, three hero choices and a nod in the answer». Ready hints:
- «New branch», «Nods in answers», «Honest refusals», «Trader», «Scene after the talk».

How the answer is processed:
- the AI receives the whole file, the format, your tags and contexts, and writes the file anew;
- the answer goes through the same check; if there are errors, the AI receives them itself and fixes them (one retry);
- the result waits for the **«Apply»** button: look at the text and accept or discard it.

**Papyrus scripts.** For example: «a guard salutes when the hero comes closer than 300 units». The script is checked against **the real signatures from your game's sources** (`Data\Scripts\Source`). A wrong number of arguments is caught, and the AI fixes it by itself.

> [!WARNING]
> The AI's answer replaces the whole file, and unsaved changes in it are lost — save what you want to keep before pressing «Apply».

> [!IMPORTANT]
> The AI never goes around the hard rules, whatever it is asked: only adults in romance, intimacy only through a «Life» action and the core's consent, no explicit text, never «forced», captives or animals.

---

## 11. Papyrus scripts for your own mod

The «Papyrus script» tab has templates that compile at once (checked with Caprica):

| Template | Where | What it does |
|---|---|---|
| A gesture during a line | a line fragment (TopicInfo) in the CK | `GAM.Gesture` on the speaker: a nod, a hand gesture |
| A scene of the two after a line | TopicInfo, `OnEnd` | `GAM.RunScene` of the hero and the interlocutor: the camera floats, stages in turn |
| A «Life» context after a line | TopicInfo | `OGAIAnim.Context`: the core picks the scene, an intimate one only with consent |
| A scene on activation | furniture / activator | the hero plays a scene on this reference (sit, dance) |
| Quest functions | a quest script | `Gesture` and `SceneWithPlayer` — call them from your own fragments |

- **«Check»** — a quick check: blocks are closed, the G.A.M. and OGAIAnim functions exist, the number of arguments matches the game's sources, an intimate scene is not requested by tags.
- **«Copy»** — to the clipboard, then compile in the Creation Kit or Caprica. The `GAM.psc` source is installed with G.A.M. into `Data\Scripts\Source\User`.

> [!NOTE]
> «Check» is a quick check, not a compiler: the Creation Kit or Caprica has the last word.

---

## 12. FAQ

**«To the game» is unavailable.**
The file has errors — see the list on the right.

**The character is silent.**
Check «Who speaks» (for a game NPC the chip shows a name; a chip without a name is an editor id typed by hand, and such an NPC may not exist in the game) and that the last greeting has no conditions. If the character already has a bundled tree, raise your `priority`.

**The branch is not visible on the wheel.**
Is its condition met; is it not the empty top slot of a trader; is another mod not overriding the topic (see «Build and check»). After edits — «To the game» and restart the game.

**A line has no sound.**
The recording is uploaded and selected at this variant and this language (the language is the language of your game); for a WAV, the Creation Kit is in the game folder (`Tools\Audio\xwmaencode.exe`). «Build and check» shows what is missing.

**The lips don't move.**
The recording has no `.lip` — make the lip sync and upload it with «+ .lip».

**A gesture is not visible in the dialogue.**
The dialogue camera holds a close-up. A nod (the head) is always visible; a gesture with the arms is better «after the talk» or as a scene.

**«No scene in the game fits».**
No installed scene matches the tags. Install «G.A.M.: gestures» (nods, «salute», «point», «hands up») or a pack with the tags you need ([ANIMATION_IMPORT.md](ANIMATION_IMPORT.md)).

**The mod won't install: «id already taken».**
You (or another installed mod) have a tree with the same id. Rename yours or remove the other mod.

**Where are my files?**
`%APPDATA%\BoopiMod\talk` (recordings — `talk\audio`), the path is shown at the bottom of the file list. You can edit them in any editor too: the studio rereads the file when opened. Saved mods — `Documents\BoopiMod\Mods`.

---

## 13. What to read next

- [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md) — where to get animations (import from Skyrim and Fallout 4 mods) and how to make your own in the G.A.M. editor.
- [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) — a reference for animations in dialogues and scripts: gesture and scene, camera, tags, contexts.
- [AI_DIALOGUE.md](AI_DIALOGUE.md) — the «Dialogues: AI» mode through the player's eyes.
- [VOICE.md](VOICE.md) — voice-over (TTS), voice cloning and speech recognition (STT).

[All guides](README.md) · [Project home page](../../README.en.md)
