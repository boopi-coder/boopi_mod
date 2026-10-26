<p align="center"><img src="../../docs/images/banners/gam.jpg" alt="G.A.M. — the animation engine: import and your own scenes" width="100%"></p>

# <img src="../../docs/images/icons/import.png" width="56" align="absmiddle"> Animations in boopi_mod: import from mods, Skyrim, and your own scenes

[🇷🇺 Русский](../ANIMATION_IMPORT.md) · 🇬🇧 English

[← All guides](README.md) · [Project home page](../../README.en.md) · Next: [Animations in mods and scripts](ANIMATION_GUIDE.md)

> *Modding has never been this easy.*

boopi_mod is first of all a **mod manager in which you create your own things**: animations, scenarios, scenes and dialogues —
by hand or with AI help. Animations belong to **G.A.M. — the animation engine**: a 3D editor with IK handles, import of animations from
Skyrim / OAR / Fallout 4 mods, the AI animator, and playback of scenes right in the game.

> [!NOTE]
> **⏱ In 1 minute**
>
> - Every animation in boopi_mod is a **G.A.M. scene** (a `.gam` file in your library): roles, bones, furniture and props, camera, tags.
> - The fastest way: open **G.A.M.** and **drag** a mod archive, folder, plugin, BA2 or HKX into the window — the pack
>   is scanned, you tick what you need, and it becomes tagged scenes (into the game when «and install into the game» is ticked).
> - It reads Fallout 4 mods (HKX, idles, OAR gaits) and **Skyrim SE** mods (FNIS, SexLab Animation Loader).
> - Importing is your choice: the app itself depends on no animation mod of anyone else. When no scene fits, the game's
>   own animation plays.
> - Make your own in the editor: set up roles, drag **IK handles**, place keys — or ask the **AI animator** in plain words.
> - Then the scene is found by «Life», by dialogue lines (via tags) and by Papyrus scripts, and your mod (`.ogmod`) carries it to other players.
> - Play it yourself right in the game: look at a person and **hold "="** — the animation menu opens
>   ([4.6](#46-play-it-in-the-game-the-animation-menu)).

## Contents

1. [The fastest way: drag in and play](#1-the-fastest-way-drag-in-and-play)
2. [Importing Fallout 4 mods](#2-importing-fallout-4-mods)
3. [Skyrim animations](#3-skyrim-animations)
4. [Your own scene in the editor](#4-your-own-scene-in-the-editor) — [play it in the game: the animation menu](#46-play-it-in-the-game-the-animation-menu)
5. [How animations reach the player](#5-how-animations-reach-the-player)
6. [FAQ](#6-faq)
7. [What next](#7-what-next)

---

## Where scenes come from

Every animation in boopi_mod is a **G.A.M. scene** (`.gam` files in your library): who takes part (roles), what each bone does,
where the furniture and props stand, the camera, the tags.

| Source | How | Section |
|---|---|---|
| A Fallout 4 animation mod (HKX clips, idles, OAR gaits) | drag into G.A.M. or use «Import» | [2](#2-importing-fallout-4-mods) |
| A Skyrim SE animation mod (FNIS, SexLab Animation Loader) | drag into G.A.M. | [3](#3-skyrim-animations) |
| Your own scene from scratch | the G.A.M. editor | [4](#4-your-own-scene-in-the-editor) |

After that the scene plays in the game: in «Life» (by context), in dialogue lines (by tags), from Papyrus scripts — and it can
travel inside your mod to other players. How to call animations from dialogues and scripts: [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md);
the dialogue studio: [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md).

> [!NOTE]
> No third-party programs are needed: boopi_mod reads and converts everything itself. Nothing from the source mod is ever executed.

---

## 1. The fastest way: drag in and play

1. Open **G.A.M.** in the boopi_mod menu.
2. Drag a mod archive (zip / 7z / rar), its folder, a plugin (ESP / ESM / ESL), a BA2 or a single HKX into the window.
   A hint appears: «Drop the file: Skyrim and Fallout 4 animations — the import sorts it out».
3. The pack is **only scanned**: «Library → Import» opens the list of what was found, with kinds and counts (pairs: 73, clips:
   16168…). No scene is made by itself and nothing goes into the game.
4. Tick what you need (a name filter, «all kinds» / pairs / clips…, «Tick the shown») and press **«Convert the ticked»** (or «Convert
   all»). Every clip, pair, SexLab scene and OAR gait set becomes tagged scenes (from the pack's tags, from words in names and, for
   single clips, from the motion itself). The **«and install into the game»** box puts them into the game at the end (off by
   default). More than 200 items or installing into the game — the app asks first and says how long it takes.
5. The conversion runs in the background: «Converting the pack: N / M… · ≈ K min left», with a **«Stop»** button (what is done stays
   in the library, nothing goes into the game). You can leave for another tab or page and come back — the job is still there.

A single scene file **`.gam`** (a friend's scene, an export from another game) is no pack: drop it into the window or pick it in
«Upload a file…» — it goes into the library as a scene of its own (`my/<name>`, a taken name gets a suffix) and opens.

Once installed into the game, «Life» and dialogues find the new scenes by tags at once.

**The same pack again makes no duplicates.** The same file (it is recognised by its content, whatever it is called) or the same
folder is the same source: it is parsed again in place and its scenes are updated under their old ids. Scenes you changed yourself
(or saved by hand from the editor) are not overwritten by the pack — the result says «yours kept: N». A different file with the
same name is a different source (`name_2`).

> [!TIP]
> For scale: a Skyrim pack of 990 clips, 8 gait sets — became 184 scenes already installed in the game in just over a minute.

---

## 2. Importing Fallout 4 mods

If you want to choose exactly what to take, open **Library → «Import»**. You can point at a source in three ways:

- **«Upload a file…»** — an archive, plugin, BA2 or HKX;
- **«A folder or file path»** → «Scan» — a mod unpacked anywhere;
- **«Scan the game»** — whatever is already installed in `Data`.

The source is unpacked once into your folder (`%APPDATA%\BoopiMod\gam\imports`) and sorted by kind:

| Kind | What it is |
|---|---|
| **pairs** | clips of two participants (recognised by names such as `_A/_B`, `Male/Female`, `Lead/Follow`…) |
| **idles** | the plugin's idle records with their clips |
| **vanilla** | vanilla idles that the plugin refers to (the clips come from the game's own archives) |
| **clips** | single HKX files (the skeleton is chosen by path: `Actors\Dogmeat\…` is a dog) |
| **OAR gaits** | walk / run / stance sets for «gait by condition» (drunk, wounded, tired) |

<p align="center"><img src="../../docs/images/gam-library-import.en.png" alt="G.A.M. library: a scene list filtered by tag on the left, the Import tab with a list of packs on the right" width="860"></p>

*The scene library (filtered by tag) and pack import: each pack shows how many pairs, idles and clips it holds, and the «Choose…» button.*

What you can do with the list:

- **Filter** by name or tag.
- **«✕»** — remove the source. The app shows how many of its scenes are in the library and asks: remove those too (from the
  library **and from the game**) or keep them. The scenes you changed always stay, as your own.
- **«To a scene»** on an item: it opens in the editor — roles from the clips (a pair faces each other), bones from the HKX.
  Edit it from there ([section 4](#4-your-own-scene-in-the-editor)) and press «Save» / «To the game».
- **«Choose…»** on a source opens its list: ticks, filters, «Convert the ticked» / «Convert all», the «and install into the game» box
  (section 1).
- **«Build gaits (N)»** — turns OAR sets into G.A.M. gaits (into the game only with «and install into the game» ticked).

> [!NOTE]
> Parsing hints: variants of the same action for a man and a woman (a `Female` subfolder) are variants, not a pair; numbers
> `_1/_2` are variants too; a clip on a vanilla path is marked «replaces vanilla»; a `no loop` folder means «play once».

---

## 3. Skyrim animations

Drag a **Skyrim Special Edition** mod (an archive, folder or file) straight into G.A.M. The motion is transferred to the
Fallout 4 skeleton automatically.

**The Skyrim skeleton.** The motion is transferred from its rest pose, so a skeleton is needed — it comes from your computer:
- from your installed Skyrim SE (`skeleton.hkx` from its archives or its Data folder) first;
- else from a mod you drop in yourself: drag the **XPMSE** archive in once (or any mod with `character assets\skeleton.hkx`) — the
  male and female skeletons are remembered.

The app downloads nothing itself. With neither the game nor such a mod, the source shows «No Skyrim skeleton…», and opening a clip
gives a clear error saying what to do.

**What is read:**
- SE clips (64-bit); 32-bit Legendary Edition clips are skipped with a note — packs usually have an SE version;
- **FNIS** lists (`FNIS_<mod>_List.txt` — event name → file);
- **SexLab Animation Loader** packs (`SLAnims/json/*.json` — multi-actor scenes with stages);
- all other clips one by one.

In the import list these are the kinds **Skyrim** (clips) and **Skyrim scenes**.

> [!WARNING]
> SexLab scenes with creatures are not imported.

The transfer was checked on ordinary Skyrim SE clips (dialogue, reading a book, sitting, drawing a bow): the poses look natural on a
Fallout 4 body. Fingers, hands and pelvis are corrected separately so the palms do not flip over.

**A scene for Skyrim and back.** The **Other games** button above the editor moves the open scene to another game's
skeleton: Export saves it for Skyrim SE (or for the shared canonical rig every boopi_mod game understands) into
`%APPDATA%\BoopiMod\gam\exports\<game>` (Show in folder opens it); Import takes another game's `.gam` file, converts
it to Fallout 4 and saves it as a new scene of yours. A pose looks the same on the other body, and the bones the other
game lacks (weapon bones, the Pip-Boy) stay in the scene and come back on the way home. Creatures and robots do not
move: their skeletons belong to their own game.

**Playing the scene in Skyrim itself (beta).** With Skyrim SE installed, **Install into Skyrim** in the same window
converts the scene onto your game's skeleton and puts it into `Data\GAM\Scenes\boopi`. Our SKSE plugin **GAM for Skyrim**
finds it there: in the game's console, `gam play boopi/<scene>`. How to install the plugin: [Skyrim (beta)](README.md#skyrim-beta).

---

## 4. Your own scene in the editor

Press **«New»** (or «Open a scene…» to edit an existing one). What you see in the editor is what plays in the game: it is the same code.

<p align="center"><img src="../../docs/images/gam-editor-ik-ai.en.png" alt="The G.A.M. editor: a scene on a Fallout 4 body, orange IK handles, the light panel and the AI animator log" width="860"></p>

*The G.A.M. editor: an imported scene on a Fallout 4 body (the same editor opens Skyrim clips), IK handles on the hands, feet and head, the «☀ Light» window and the AI animator log on the right.*

### 4.1 Participants and place

1. **Roles.** Add participants with the buttons «+ Man», «+ Woman», «+ Creature» (dog, super mutant, deathclaw, Mr. Handy, yao guai…),
   «+ Boy» / «+ Girl» (family, story). Bodies and skeletons are read from your game.
2. **Races** of a role: which races and groups may take it (`HumanRace`, `@synths_gen4`…), and which never. The list comes from your
   game and mods.
3. **Objects.** «+ Object» is:
   - **furniture** — it can be the **anchor**: the whole scene is then placed relative to the bed / bench;
   - an **item** in place;
   - an item **in the hand** — it follows a bone (a cigarette, a flower, a bottle).

   The «from, s» / «to, s» fields set when the object appears and disappears.

   An object is named by a form, `Plugin.esm|0x0004D1F9` (the plugin and the record's number inside it, as xEdit shows them). From
   it the viewport draws the record's **real model** from your game — furniture, statics, items, weapons, activators — not a box;
   an anchor furniture piece is tinted green. When there is no model (armour, a model on a skeleton — a creature or a robot, the
   plugin is not loaded, the game is not found), the box stays. This is only how it looks in the viewport: the model is not written
   into the scene file, and in the game G.A.M. places the object by the same form.

### 4.2 Motion

**Bone.** Click a joint or the body and pick a tool above the viewport:

| Tool | Key | What it does |
|---|---|---|
| **Rotate** | `R` | rings on a bone: turn a joint |
| **Move** | `G` | arrows and planes; the COM and pelvis move |
| **Character** | `C` | «Move the whole character» through the scene |
| **Heading** | `T` | turn the character |
| **IK** | `I` | hands, feet and head turn into orange ball handles |

A key lands at the current moment; «Key the current pose» makes a key with whatever the bone shows right now.

**IK.** Turn IK on (`I`) and drag an orange handle, with any tool: the arm or leg bends after it (the elbow and knee follow on their
own, bone lengths do not change; `Shift` drags along the floor, `Alt` up and down). Let go — keys are written onto the chain. The
head looks at a point.

**Base pose.** A bone's first key later than 0 s with no key at 0 s makes the pose from the very start. The **«Base pose at 0 s»**
checkbox (on by default) puts the rest pose at 0 s by itself, and the motion goes FROM it. Buttons:
- **«Fix initial keys»** — for bones whose first key is later than 0 s;
- **«Fix this bone»**;
- **«Fix the base pose at 0»** — all bones of the role.

**Viewport light** («☀ Light»): studio / day / night / warm interior / back light, brightness, ambient light, light side and height,
«Reset light».

> [!NOTE]
> The light affects only the viewport; it is not written into the scene.

**Nothing is lost.** Going to another page and back does not reset the scene, the selection, the request text or the library tabs;
an unsaved scene returns after a restart («An unsaved draft of the scene was restored.»).

**Editing.** Every change of the scene can be undone (`Ctrl+Z`, `Ctrl+Y`). Several keys are picked with a box or `Shift` / `Ctrl` +
click and move together; you can copy a pose (`Ctrl+C` / `Ctrl+V`), mirror it left ↔ right, stretch the time, «Fix loop seam» on a
looping scene and mark up stages. The **«⛶ Full screen»** button (or `F11`) gives the window to the viewport and the timeline, the
**«?»** button lists the keys. Details: [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md#104-editing-a-scene-in-the-editor-undo-keys-mirror-time),
section 10.4.

**Keys, tracks and the scene:**
- **Key**: time, transition (smooth / linear / step / curve), ease in and ease out.
- **Tracks**: the actor's place, bones, face, camera (how they play in the game — below, «Face and scene camera»).
- **Scene**: name, length, mode — «Animation» (a whole pose) or «Layer over the game» (a sway over vanilla walking); blend in and out
  (seconds, a smooth blend with the current pose); **loop** («Loop start» / «Loop end»): an activity — entry, loop until stopped, exit.
- **Events** at a moment in time: sound, line, facial expression, equip / unequip, quest stage, a word of your own for scripts. In the
  game G.A.M. performs them itself (since 0.4.0); what to write in «Value» — the hint under the field and
  [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) §5.2.
- **«Optimise»**: smooth out jitter and keep the minimum of smooth keys within the tolerance (rotation °, position).

#### Face and scene camera

**Face** (the «Face» section of the inspector): pick an expression (happy, angry, sad, afraid, surprised, in pain… — Fallout 4's 35
facial expressions) and a weight and press «+ Face key on …» (with the selected role's name) — that role gets a «face: …» track at the current moment. Several keys —
the face changes during the scene.

- In the game **one expression** shows — the strongest at 0.5 and over; when all are weaker the actor has their own face. After the
  scene the face comes back.
- Weights between 0 and 1 are not mixed in the game: an expression is either on or off. **Single morphs** (a brow, the lips, a blink)
  G.A.M. does not play in the game yet — Fallout 4 1.10.163 has no documented way to set them from a plugin without risking a crash.
- «in the game now: …» under the title shows which expression will be seen at this moment.

**Scene camera** (the «Scene camera» section): set the view in the window the way the camera should film and press **«🎥 Camera key
from this view»**; go to another moment, change the view — another key: the camera moves between them. «Field of view, °» (optional) is
written into the key; empty — the game's field of view. **«Look through the scene camera»** — the window shows what the camera will see
when it plays; the light blue pyramid in the window is where the scene camera stands.

- In the game a scene with a camera track is filmed by it by itself (the «scene camera» mode, `track`); F7 switches to auto, free and
  the game's camera. Camera keys are relative to the scene's origin, like the actors' places: wherever the scene plays, the shot is the
  same.
- When the scene ends the camera, the first person view and the game's field of view come back.
- The field of view from the keys is experimental (check it in the game); the camera's place and turn work the same way as the auto
  camera of 0.3.0.

#### The AI animator

The **«AI animator»** section is the first in the right column, and an empty scene has a **«Where to start»** card over the view
(describe a scene, open one from the library or put a pose without the AI). It needs a key in «Settings → LLM providers». Describe the
scene in words, for example «put a man and a woman face to face and have them shake hands», and press **«Do it»** (`Ctrl+Enter`). The
AI knows the picked bone and the current moment — the line under the field says what it sees.

- You can see what is happening: a time counter and «Cancel», and a log («request sent → the model answered → N operations parsed →
  applied / skipped (with reasons) → check»).
- No key or the model refused — a clear error with the text and a link to the settings; «the model proposed no operations» — the scene
  did not change.
- The AI places participants itself — people, children («father and son»), creatures («a dog nearby») — and moves them: arms (including
  «arm to a point» through IK), head, gaze, crouch, knee, sitting.
- After the first request a creature can be brought to life with the next ones («let the dog wag its tail»).
- A new scene is named from the answer («Handshake») — and gets its id from that when saved.
- One wrong value in the model's answer (a time of `null`, «1.2 s», a point as text) skips only that operation, with a clear reason in
  the log; the rest is applied. The motion polish says in the log what it does (the score before, a pass, fixing the anatomy) instead
  of going silent.
- The result belongs to the scene it was asked for: when another one was opened while the request ran, it is not applied to it (the
  log says so). Under the result you see how many tokens it took.
- No key? Ready poses (standing, sitting, kneeling, lying…) work without the AI — [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) §10.4.

> [!TIP]
> Use the AI as a first draft: let it place the participants and sketch the motion, then refine the result with the IK handles and «Optimise».

### 4.3 Tags: so that the scene can be found

**Tags** are added one at a time: type a tag in the «Tag + Enter» field and press Enter (to remove a tag, click it):
- kind — talk, romance, activity, dance…;
- action — handshake, hug, smoking…;
- participants — solo, pair…;
- place — chair, wall, bed…

Under the tags you see **«Plays in contexts»** — where «Life» will pick the scene up. The line «No context takes this scene — add tags»
means exactly that: add tags. The list of contexts, and your own contexts, are in the library's «Contexts» tab
([4.5](#45-the-library-find-group-remove)).

### 4.4 Save and send to the game

- **«Save»** — to your library (`%APPDATA%\BoopiMod\gam\scenes`). A new scene gets its id from the name («Кивок» →
  `my/kivok`). **A taken id is never overwritten**: the scene gets a suffix (`my/kivok_2`) and the app tells you so.
- **«Save as…»** — a copy of the open scene under a new name in the folder you pick (a folder is part of the id: «Dances» →
  `dances/…`). The copy is your own even if the original came from someone else's pack: re-importing the pack will not touch it. But
  its motion is still somebody else's, and «Save the mod» will say so ([section 5](#5-how-animations-reach-the-player)).
- **«Delete»** — the open scene leaves the library and its copy leaves the game (after a confirmation). What is on the screen
  stays as an unsaved scene: you can save it again.
- **«History»** — earlier versions of the open scene (the button works for your own scenes). Before every save, and before a delete
  too, the previous version is kept: the last 12 stay (`%APPDATA%\BoopiMod\gam\history\<id>\`), and saving the same thing again adds
  none. The list shows the time, the name and the length; **«Restore»** makes the scene what it was. The current version is not lost:
  it goes into the history itself, so a restore can be undone the same way. Unsaved changes in the window are lost on a restore (the
  app warns you). Until the scene has been saved again there are no versions.
- **«To the game»** — the scene is installed and available in the game at once (the game re-reads the library); play it there
  from the animation menu ([4.6](#46-play-it-in-the-game-the-animation-menu)).
- **«▶ In game»** — play what is in the editor right now in the running game on the player or an NPC nearby, without saving or
  installing it; the game's log about this scene is there too: why it did not play and what to do
  ([ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) §11).

### 4.5 The library: find, group, remove

The **Library → «G.A.M. scenes»** tab holds everything you have: your own scenes, imported ones and those that ship with the app.

- **Search** — one field: a name, an id, a tag or a pack name. Several terms with commas must all hold (`kiss, couch`); `-tag`
  leaves scenes out (`-intimate`). Tag words are understood in Russian and English.
- **Groups** — by folder (a part of the id: `my`, `import/<source>`, `gait/…`) or by import source; a group can be folded.
  **Order** — by name, newest first, longest first, by number of roles.
- **★** — favourites: those scenes stay on top, the «★» button above the list shows only them.
- **Preview** — each scene has a thumbnail: a skeleton silhouette in one pose (the middle of the loop), one colour per role. It is
  drawn on your computer once and kept until the scene changes. While there is no skeleton from the game (check the game path)
  you get plain figures, one per role, instead.
- **What the game has** — a «in game» or «game copy is old» badge (the scene was saved after it was put into the game) and the
  buttons «To the game» / «Update» / «Remove» (the game copy goes, the scene stays in the library).
- **Copy** — your own copy of a scene (of any, bundled ones too); **✕** — delete the scene from the library and from the game
  (after a confirmation; the app's bundled scenes cannot be deleted).
- **The «Contexts» tab** — where the systems (the body, «Life», «The living world», your own contexts) want an animation, and how
  many installed scenes fit each place («fits: N»; «nothing installed — the game keeps its own»). Its **«+ Own context»** makes your
  own tag query so that lines, triggers and «Life» find your scenes (how contexts work:
  [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md#8-through-the-life-system-contexts)).

### 4.6 Play it in the game: the animation menu

Your own scene (or a scene of a pack) plays in the game with no scripts and no AI (G.A.M. 0.7.0):

1. Put the scene into the game with **«To the game»** (the scenes of packs, and imports with «and install into the game», are
   there already).
2. In the game, look at a person and **hold "="** for about half a second. A menu opens in the top right corner; the world
   is paused.
3. At the top choose **who plays**: **Me** · **the person in front** · **them and someone nearby** (a pair scene of two NPCs:
   for each scene the nearest person who fits its roles is taken) · **Me + them** (a pair scene with you). With nobody in
   front the menu opens for you alone.
4. The list holds only what fits: solo scenes for one, pair scenes for two, the roles by race and sex (the app turns a pair
   round when the "man / woman" roles are the other way). **Favourites** and **recent** come first, then the sections
   (gestures, dances, social…). To find a scene, just type its name.
5. **Enter** (or a double click) plays it; the menu closes and the scene starts.

| Key | What it does |
|---|---|
| ↑ ↓, PgUp / PgDn, the wheel | move in the list |
| ← → | who plays |
| Tab / Shift+Tab | the section |
| letters and digits, Backspace | search |
| Space (or a click on the star) | favourite / not |
| Del (or «Stop») | end the scene that plays on you or on the person in front |
| F2 (or «Camera») | the scene camera: G.A.M.'s choice → auto → free → the scene's → off (a gesture leaves the camera alone) |
| Esc | clear the search; again — close the menu |

- **The menu key** is set in the app: **Settings → Game → «G.A.M. in the game: the animation menu»**. A running game takes it
  within seconds while boopi_mod is open; without the app the last one it got stays (or `GAM.ini` `[Menu] iKey`).
- **Without the app** the menu works too: every scene except the scenes of closeness (those are listed by a running
  boopi_mod — the app's protection decides which are allowed for these people). The menu says how many it leaves out.
- **A looping scene** runs until «Stop» (or 60 seconds — `GAM.ini` `[Menu] fLoopSeconds`); while you are in a whole-body
  scene your controls are off, as in any G.A.M. scene.
- **FPS**: the closed menu does nothing in the game's frame; the open one pauses the game (`GAM.ini` `[Menu] bPause`).
  Favourites and recent ones are kept in `Documents\My Games\Fallout4\F4SE\GAM_Menu.json`.

---

## 5. How animations reach the player

- **The menu in the game**: look at a person, hold "=" and pick a scene ([4.6](#46-play-it-in-the-game-the-animation-menu)).
- **«Life»**: contexts («Hug», «Sit together», «Closeness»…) pick scenes by tags, furniture and participants.
- **Dialogues**: in Script studio a line has an «Animation» field — your own scene of the library picked by name, by tags (you see
  how many scenes fit) or by a «Life» context ([SCRIPT_STUDIO.md](SCRIPT_STUDIO.md#2-your-first-conversation-in-5-minutes), step 3).
- **Triggers of your own story**: the «G.A.M. scene» action — by name from the library, by tags or by a context
  ([SCRIPT_STUDIO.md](SCRIPT_STUDIO.md#12-triggers-your-own-story)). The library scenes lines and triggers play go into the game with
  the studio's «To the game».
- **Scripts**: `GAM.Gesture`, `GAM.RunScene`, a tag query `"hug,pair,-intimate"` ([ANIMATION_GUIDE.md](ANIMATION_GUIDE.md)).
- **Your own mod**: in Script studio press «Save the mod» — the scenes your files play by id go in by themselves, tick others — they
  travel in the `.ogmod` together with the dialogues. For whoever installs the mod, the scenes land in their library and straight in the
  game (`Data\GAM\Scenes`) and are removed together with the mod on uninstall. If a scene plays clips of someone else's pack, the mod
  remembers which pack is needed and shows it at install time ([SCRIPT_STUDIO.md](SCRIPT_STUDIO.md#9-your-own-mod-save-and-share),
  section 9). Your own G.A.M. contexts and race groups that its files and packed scenes name travel with the mod too.
- **Rights to other people's work.** A scene made of somebody else's animations (an imported pack, Skyrim, OAR gaits, a plugin's
  clips) carries somebody else's motion: in the «Save the mod» list it is marked «not yours», the warnings name it («you need the
  author's permission to share it»), and the «Only my own scenes» box keeps in the mod only what you made yourself. Share other
  people's work only with their author's permission.

---

## 6. FAQ

**«gamtool (the G.A.M. animation library) is missing».**
The G.A.M. animation library is missing — reinstall boopi_mod.

**«No skeleton: …».**
The skeleton is extracted from the game files; check the game path in the settings. For Skyrim, an installed Skyrim SE gives the
skeleton itself (set its folder in «Other games»); without it, drag an XPMSE archive (or any mod with the skeleton) in once.

**The editor showed «This part could not be shown: …».**
A part of the editor failed on this scene, the rest of the app works: «Try again», «Reset the G.A.M. state» (a new empty scene) or
«Details» for a bug report. The scene the editor failed on is not opened by itself at the next start («Open it anyway»). Errors in a
scene file (an object without a place, a key without a time…) are mended while reading, and a note over the view says what was
mended.

**Import: «some parts could not be read».**
Some files of the pack are damaged or in an unfamiliar format; the rest was imported, the list is in the message.

**Skyrim clips were skipped.**
These are 32-bit Legendary Edition clips — take the SE version of the pack.

**The scene exists but does not play in the game.**
Press «To the game» on the scene; check «Plays in contexts» and the tags; for a dialogue, check how many scenes fit the line's tags.

**A pair stands wrongly.**
Open the scene and fix the roles' «place» (the root track) or put in an anchor furniture piece.

---

## 7. What next

- [ANIMATION_GUIDE.md](ANIMATION_GUIDE.md) — calling animations from Papyrus scripts, dialogues and «Life», the camera, your own mod.
- [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md) — Script studio: dialogues, animations in lines, the `.ogmod` mod.
- [AI_DIALOGUE.md](AI_DIALOGUE.md) — the «Dialogues: AI» mode from the player's side.
- [VOICE.md](VOICE.md) — voice-over and speech recognition.
- [Guides index](README.md) · [Project home page](../../README.en.md)
