<p align="center"><img src="../../docs/images/banners/modders.jpg" alt="Animations in boopi_mod and G.A.M. mods: gestures, scenes, camera" width="100%"></p>

# <img src="../../docs/images/icons/gam.png" width="56" align="absmiddle"> Animations in boopi_mod and G.A.M. mods: scripts, dialogues, scenes, camera

[🇷🇺 Русский](../ANIMATION_GUIDE.md) · 🇬🇧 English

[← All guides](README.md) · [Project home page](../../README.en.md) · Before this: [Import and your own scenes](ANIMATION_IMPORT.md)

> *Modding has never been this easy.*

boopi_mod is first of all a **mod manager in which you create your own things**: animations, scenarios, scenes and dialogues — by
hand or with AI help. This guide is for modders: how to make **G.A.M. — the animation engine** play an animation from a script, from a
dialogue line or from the «Life» system, how to build a cinematic scene with a camera, and how to pack a mod that our manager installs.

> [!NOTE]
> **⏱ In 1 minute**
>
> - There are two kinds of animation: a **gesture** (one-off, on one actor, a body part over whatever the actor is doing) and a **scene**
>   (the whole body, several actors, stages, a camera).
> - In Papyrus: `GAM.Gesture(actor, "gesture,talk,friendly")` for a gesture and `GAM.RunScene("hug,pair", actors)` for a scene.
> - An animation is chosen by a **scene id** or a **tag query** (`"hug,pair,-intimate"`): that way any installed pack can supply it.
> - From a dialogue: the `anim` block in a line's `do:` (`tags` or `context`, `who`, `part`, `when`); from «Life»: `OGAIAnim.Context(...)`.
> - Intimate scenes and children: the protection in the core and in GAM.dll always works and cannot be bypassed; your own mod is
>   `.gam` scenes with honest tags.

Importing other people's animations (Skyrim, OAR) and the scene editor are described in [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md).

> [!TIP]
> Everything below can be done without code in the app: **boopi_mod → «Script studio»** — dialogue trees in forms, animations in lines
> with a «what will play» hint, ready-made Papyrus scripts and an AI assistant. Details: [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md).

Everything described here was tested in the game (Fallout 4 1.10.163, G.A.M. 0.3.0, BoopiCorp 2.4.4): Stella's gesture in a dialogue,
«hands up» on an NPC and on the hero, a nod with the head only, a hug with the camera in both modes.

## Contents

1. [Two ways to animate](#1-two-ways-to-animate)
2. [Quick start: 3 lines of Papyrus](#2-quick-start-3-lines-of-papyrus)
3. [Where animations come from: scene id and tag query](#3-where-animations-come-from-scene-id-and-tag-query)
4. [A one-off animation (gesture)](#4-a-one-off-animation-gesture)
5. [Scene](#5-scene) — [stages](#51-stages-how-a-scene-develops), [events](#52-scene-events)
6. [Scene camera](#6-scene-camera)
7. [Animation from a dialogue](#7-animation-from-a-dialogue) — [our trees](#71-our-dialogue-trees-datatalkyaml), [Creation Kit](#72-your-own-dialogue-in-creation-kit)
8. [Through the «Life» system: contexts](#8-through-the-life-system-contexts)
9. [Safety](#9-safety)
10. [A mod for our manager](#10-a-mod-for-our-manager)
11. [How to test in the game](#11-how-to-test-in-the-game)
12. [Common mistakes](#12-common-mistakes)
13. [What next](#13-what-next)

---

## 1. Two ways to animate

| | **One-off animation (gesture)** | **Scene** |
|---|---|---|
| What it is | Once, on one actor: wave, nod, scratch the back of the head, shrug | Like in a film: one or more actors, the whole body, stages in turn |
| Body | A body part over whatever the actor does on their own (arms while walking, head while talking) | The whole body; people step onto their marks |
| Camera | Not touched | Floats around the people and picks angles itself (`auto`) or the player controls it (`free`) |
| Player control | Stays | Disabled while the hero is in the scene (look stays for the manual camera) |
| Does the script wait | No: the function returns control at once | Yes: `RunScene` waits for the scene to end (or use `StartScene` without waiting) |
| Papyrus | `GAM.Gesture(actor, "gesture,point,forward")` | `GAM.RunScene("hug,pair", actors)` |
| Dialogue (our trees) | `do: { anim: { tags: "...", who: npc, part: head } }` | `do: { anim: { tags: "hug,pair", who: both, when: after } }` |
| Through «Life» (with consent) | `OGAIAnim.Context("talk_gesture", npc, "npc")` | `OGAIAnim.Context("hug", npc)` |

The rule of choice is simple:
- if the animation should happen «in passing», it is a **gesture**;
- if the player lets go of the mouse and watches, it is a **scene**.

---

## 2. Quick start: 3 lines of Papyrus

```papyrus
; point forward - a one-off gesture on the upper body, the NPC keeps walking
GAM.Gesture(akSpeaker, "gesture,point,forward")

; nod with the head only
GAM.Gesture(akSpeaker, "gesture,talk,friendly", "head")

; hug the hero - a scene: the camera floats, control is disabled, the script waits for the end
Actor[] two = new Actor[2]
two[0] = Game.GetPlayer()
two[1] = akSpeaker
GAM.RunScene("hug,pair", two)
```

For this to compile:
- `GAM.psc` must be in the import folder of your Papyrus compiler; its source is installed together with G.A.M.;
- `GAM.pex` and `GAM.dll` are needed in the game.

> [!WARNING]
> If G.A.M. is not installed, the calls do not compile (or, with late binding, do nothing) — see [section 10.3](#103-version-check),
> «Version check».

---

## 3. Where animations come from: scene id and tag query

Every G.A.M. animation is a scene file `Data\GAM\Scenes\<path>\<name>.gam`. Its **id** is the path without the extension:
`gesture/talk_friendly_f_s1`.

In every function with an `asWhat` parameter you can pass:
- a **scene id** — exactly that scene plays;
- a **tag query** — `"hug,pair"`, `"gesture,talk,-nervous"`. G.A.M. picks a random suitable scene:
  - all plain tags are required, tags with a minus exclude;
  - the number of roles must match the number of actors;
  - **an intimate one — never** (see [section 9](#9-safety)).

> [!TIP]
> A query beats an id: the player may have installed other packs, and a scene with the right tags will be found in any of them.

The tag vocabulary is in `data/gam/tags.yaml`. The most useful tags:

| What | Tags |
|---|---|
| A gesture in conversation | `gesture,talk` + a mood `friendly`, `confident`, `nervous`, `irritated`, `neutral`, `depressed`, `scared`, `shocked`; length `short` / `medium` |
| Hands up | `gesture,surrender` |
| Smoke and talk | `gesture,smoke` |
| Point a direction | `gesture,point` + `forward` / `back` / `left` / `right` |
| Salute | `gesture,salute` (+ `military`, `brotherhood`) |
| Wave | `wave` — the vanilla game has no such clip: you need your own scene or a pack with this tag |
| Pair | `pair` + an action: `hug`, `kiss`, `handshake`, `dance`, `hold_hands` … |
| One actor | `solo` |
| Upper / lower body | `upper_body` / `lower_body` |

**Gestures out of the box.**
- The «Gestures from the game» pack (`gam_gestures`, installed by the manager) builds 64 gestures from your own game's animations at
  install time: 8 moods × male/female × 4 clips, plus «hands up», «smokes and talks», three kinds of «salute» and «point» in four directions.
- No game files are copied into the pack: the clips are read from your archives during the build.
- Ids: `gesture/talk_<mood>_<m|f>_<s1|s2|m1|m2>`, `gesture/hands_up`, `gesture/smoke_talk`, `gesture/salute`, `gesture/salute_military`,
  `gesture/salute_bos`, `gesture/point_<forward|back|left|right>`.

> [!NOTE]
> A scene that does not exist in the game (for example «scratch the back of the head») cannot be played by G.A.M. Such an animation must
> first be made in the G.A.M. editor or imported with tags (`scratch`, `upper_body`, `solo`); then the query `"scratch"` finds it.

**See what is installed:**
- in the game: `GAM.ListScenes("gesture,talk")` — an array of ids;
- in the app: boopi_mod → G.A.M. → Library (filter by tags).

<p align="center"><img src="../../docs/images/gam-library-import.en.png" alt="G.A.M. library: a scene list filtered by tag and the pack import tab" width="860"></p>

*The G.A.M. library in the app: scenes with tags (filter by tag, for example `hug,pair,-intimate`) and pack import — this is where you see what exactly your query will find.*

---

## 4. A one-off animation (gesture)

```papyrus
int Function Gesture(Actor akWho, string asWhat, string asPart = "") global
```

- `asWhat` — an id or a tag query.
- `asPart` — the body part. An empty string means «as set in the scene» (`meta.part` or the tag `upper_body`). Options:

| `asPart` | What moves | Example |
|---|---|---|
| `upper` | everything from the waist up | point, spread the arms, a gesture in conversation |
| `head` | neck and head | nod, shake the head, look back |
| `arms` | both arms (shoulders and below) | clap, rub the palms |
| `left_arm` / `right_arm` | one arm | scratch the back of the head with the right, fix the hair |
| `lower` | legs and pelvis | shift the feet, stamp |
| `full` | the whole body | — (for the whole body a scene is better) |

How a gesture behaves:
- It plays **once** and smoothly returns the actor to their own animation (blend in 0.3 s, out 0.45 s).
- The rest of the body stays its own: you can wave while walking.
- The camera and control are not touched. The function returns a handle (0 — no suitable scene) and hands control back to the script at once.
- A clip for the actor's sex is looked for first: for a woman, one with the tag `female`. Only if there is none, any clip is taken.

Examples:

```papyrus
GAM.Gesture(akSpeaker, "gesture,talk,confident")                 ; a confident upper-body gesture
GAM.Gesture(akSpeaker, "gesture,talk,friendly,short", "head")    ; a nod only
GAM.Gesture(Game.GetPlayer(), "gesture,surrender")               ; the hero raises their hands
GAM.Gesture(akGuard, "gesture/talk_irritated_m_s1", "right_arm") ; a specific scene, right arm only
```

A lower level if you need your own behaviour:

```papyrus
int h = GAM.PlayPart("gesture/hands_up", actors, "upper")   ; plays until stopped (if the scene has a loop)
GAM.Stop(h)                                                 ; finish and exit; GAM.Stop(h, true) - at once
int o = GAM.OverlayPart(akActor, "drunk_sway", "upper", 0.6) ; a weighted layer until stopped
GAM.SetWeight(o, 0.3)
```

---

## 5. Scene

```papyrus
bool Function RunScene(string asWhat, Actor[] akCast, ObjectReference akFurniture = None, \
                       float afSecondsPerStage = 0.0, float afMaxSeconds = 0.0, string asCamera = "") global
```

- `akCast` — actors in the order of the scene's roles. For a pair, `[0]` is usually the hero and `[1]` the NPC.
- `akFurniture` — the anchor furniture (a bed, a sofa): the scene is placed on it. Without furniture the scene is placed where the first
  actor stands, the others relative to them.
- `afSecondsPerStage`:
  - `0` — each stage plays as many passes as the scene specifies;
  - `> 0` — each stage loops in whole passes until that many seconds have passed.
- `afMaxSeconds` — the limit of the whole scene. A scene **without stages** is looped and would run forever without a limit, so the default is 20 s.
- `asCamera` — `"auto"`, `"free"`, `"off"`; an empty string means «as in GAM.ini» (`auto` by default).

What happens on a call:
1. A scene is picked (`PickScene`).
2. Actors smoothly step onto their marks: bodies «glide» there instead of jumping. If an NPC tries to walk away under its own AI,
   G.A.M. returns it to its mark.
3. Stages ([5.1](#51-stages-how-a-scene-develops)) and the camera ([section 6](#6-scene-camera)) are switched on.
4. While the hero is in the scene, walking, combat, menus and view changes are disabled; look works — it turns the manual camera.
5. At the end the scene leaves the loop, actors smoothly return to their own animations, control comes back.

If there is no suitable scene, `RunScene` returns `false`.

Without waiting (for example, to flip through the stages yourself):

```papyrus
int h = GAM.StartScene("dance,pair", two, None, 0.0, "auto")   ; 0 = nothing found
if h > 0
    Utility.Wait(5.0)
    GAM.NextStage(h)          ; the next stage at once (false: that was the last one - exit)
    GAM.WaitScene(h, 60.0)    ; wait for the end, at most a minute; the hero's control is disabled meanwhile
endif
```

### 5.1 Stages (how a scene develops)

A scene with stages runs **in order**: each stage loops its passes, then the next one, and after the last one — exit. This is how
«developing» scenes are made: meeting → hug → dance.

Stages are set in the scene file in one of two ways:
- `meta.stages: [{ "name": "stage1", "start": 0, "end": 4, "loops": 2 }, ...]` — exact boundaries and the number of passes;
- markers `markers: { "stage1": 0.0, "stage2": 4.0, "stage3": 9.5 }` — a stage runs from its marker to the next one (the last — to the end), one pass each.

Functions:
- `GAM.StageCount(h)` — how many stages (0 — a scene without stages, just a loop);
- `GAM.GetStage(h)` — the current stage, 1…N;
- `GAM.NextStage(h)` — go to the next stage now;
- `GAM.Staged(h, sec)` — switch on step-by-step mode manually (`StartScene` does it itself).

### 5.2 Scene events

A scene can carry events (`events` in the file: a sound, a line, a change of expression). In Papyrus you can read them in turn:

```papyrus
string e = GAM.NextEvent(h)   ; "type|target|value", "end||" when the scene is over, "" - nothing yet
```

---

## 6. Scene camera

The camera is switched on **for scenes only** (`RunScene` / `StartScene`, our dialogues and «Life», when the hero is in the scene).
Gestures do not touch it.

| Mode | How it behaves |
|---|---|
| `auto` (default) | By itself: 6 shots in a cycle — front side, closer side, over the shoulder from behind, from above on the other side, low and close, wide front. Within a shot it slowly orbits the people and creeps in a little; between shots it glides over smoothly (2.5 s). It looks at chest level, with all the people in frame. |
| `free` | Manual: mouse or arrows — around the people, PageUp / PageDown or the wheel — closer / further. |
| `off` | The game's normal camera. |

How to control the camera:
- **F7** during a scene cycles the modes: `auto → free → off → auto`.
- If the hero was in first person, the camera switches to third person for the scene and goes back after it.
- The mode from a script: `GAM.Camera(h, "free")`; to read the current one — `GAM.CameraMode()` (an empty string if the camera follows nothing).

Settings are in `Data\F4SE\Plugins\GAM.ini`, section `[Camera]`:

| Key | Default | Meaning |
|---|---|---|
| `sMode` | `auto` | the default mode |
| `iSwitchKey` | `118` | the switch key (Windows code: F7 = 118, F8 = 119) |
| `fShotSeconds` | `7` | how long a shot lasts |
| `fGlideSeconds` | `2.5` | the glide between shots |
| `fOrbitDegrees` | `5` | degrees per second of orbit within a shot |
| `fDistance` | `1.0` | distance multiplier (0.7 in tight rooms) |
| `fHeight` | `35` | height of the look-at point above the people's centre (35 — chest) |
| `bMessages` | `1` | an on-screen note about a mode change (visible if the HUD is not hidden) |
| `bDebug` | `0` | 1 — camera shots are written to `Documents\My Games\Fallout4\F4SE\GAM.log` |

> [!WARNING]
> Camera limits:
> - The camera does not know about walls: in a tight place a shot may end up behind a pillar or a microphone stand. F7 → manual mode or
>   a smaller `fDistance` helps then.
> - The HUD is hidden during a scene, so the mode note may not appear.

---

## 7. Animation from a dialogue

### 7.1 Our dialogue trees (`data/talk/*.yaml`)

In the `do:` consequences block of any line (a hero option or an
NPC reply) you can add `anim`:

```yaml
do: { anim: { tags: "gesture,talk,friendly", who: npc, part: head, when: line } }
```

| Field | Values | Meaning |
|---|---|---|
| `tags` | a tag query | an animation straight from G.A.M. (a gesture for one, a scene for `both`) |
| `context` | a context id (`data/gam/contexts`) | the core picks the animation; an intimate one — only with consent ([section 8](#8-through-the-life-system-contexts)) |
| `who` | `npc` (default) / `player` / `both` | on the interlocutor, on the hero, or a scene for both |
| `part` | `head`, `upper`, `arms`, `left_arm`, `right_arm`, `lower`, `full` | the body part (by default — as in the scene) |
| `when` | `line` (default) / `after` | now, while the line is spoken, or when the conversation ends |

One of two is required: `tags` or `context`. A string with a comma in `context` is treated as a tag query. With `who: both` it is
always a **scene** with a camera. It is better to set it with `when: after` so that it does not fight the dialogue camera.

**Example: a small dialogue with a head and arm gesture.**

```yaml
trees:
  my_barman:
    who: [MyModBarman]
    title: { ru: "Бармен", en: "Barman" }
    flags: [met]
    greet:
      - { when: { not: met }, go: first, do: { set: met }, ru: ["Новенький? Садись."], en: ["New here? Take a seat."] }
      - { go: first, ru: ["Опять ты. Что налить?"], en: ["You again. What'll it be?"] }
    nodes:
      first:
        - slot: question
          label: { ru: "Что у вас тут?", en: "What's this place?" }
          reply:
            # a reply with a nod: only the head moves, the hands keep wiping the glass
            - { do: { anim: { tags: "gesture,talk,friendly,short", who: npc, part: head } },
                ru: ["Бар. Лучший в квартале. Единственный в квартале."], en: ["A bar. Best on the block. Only one on the block."], go: first }
        - slot: positive
          label: { ru: "Выглядишь уставшим.", en: "You look tired." }
          reply:
            # an upper-body gesture: spread the arms, the feet stay where they were
            - { do: { anim: { tags: "gesture,talk,depressed", who: npc } },
                ru: ["Третья смена подряд. А ты как думал{p:а|}?"], en: ["Third shift in a row. What did you think?"], go: first }
        - slot: negative
          label: { ru: "Руки вверх! Шучу.", en: "Hands up! Kidding." }
          reply:
            - { do: { anim: { tags: "gesture,surrender", who: npc } },
                ru: ["Очень смешно. Я чуть бутылку не уронил."], en: ["Very funny. Nearly dropped a bottle."], go: first }
        - slot: neutral
          label: { ru: "Мне пора.", en: "I should go." }
          reply:
            # a parting point at the door - after the conversation, on the move
            - { do: { anim: { tags: "gesture,point,forward", who: npc, when: after } }, ru: ["Выход там. Заходи ещё."], en: ["Door's that way. Come again."], go: end }
```

Checking the tree (errors in `anim` — an unknown field, `who`, `part`, `when` — are found by the check):

```bash
uv run --project core python scripts/check_talk.py data/talk/my_barman.yaml
```

After that the tree is built into a plugin together with the others:
- every line with `anim` gets the properties `AnimContext` / `AnimTags` / `AnimPart` / `AnimWho` / `AnimWhen` of the script
  `OGAITreeInfoScript`;
- in the game the line calls `OGAILifeScript.TreeAnim`.

A live example is `data/talk/black_acorn_singer.yaml`, Stella: a compliment — a friendly gesture; «Sing something» — a confident one;
«I'm just listening» — a nod.

### 7.2 Your own dialogue in Creation Kit

In a line fragment (TopicInfo) it is ordinary Papyrus:

```papyrus
Scriptname MyMod_TIF_Barman_Nod extends TopicInfo Hidden

Event OnBegin(ObjectReference akSpeakerRef, bool abHasBeenSaid)
    GAM.Gesture(akSpeakerRef as Actor, "gesture,talk,friendly,short", "head")   ; a nod while speaking
EndEvent
```

- The start of a line is `OnBegin`, the end is `OnEnd`.
- A scene for two is better started in the `OnEnd` of the last line: by then the dialogue camera has already been released.

```papyrus
Event OnEnd(ObjectReference akSpeakerRef, bool abHasBeenSaid)
    Actor[] two = new Actor[2]
    two[0] = Game.GetPlayer()
    two[1] = akSpeakerRef as Actor
    GAM.RunScene("hug,pair", two)
EndEvent
```

---

## 8. Through the «Life» system: contexts

A **context** is a meaningful place where an animation is wanted: «wave», «a gesture in conversation», «hug», «dance for two»,
«closeness». A context does not name a scene itself. It holds tag queries in order of preference, the kind (`overlay` — a gesture,
`scene` — a scene, `gait` — a gait), the number of actors, the body part and suitable furniture. The files are
`data/gam/contexts/*.yaml`. Your own contexts go into `%APPDATA%\BoopiMod\gam\contexts\*.yaml`.

A call from Papyrus (BoopiCorp.esp and a running boopi_mod are needed):

```papyrus
OGAIAnim.Context("talk_gesture", akNpc, "npc") ; a gesture on the NPC
OGAIAnim.Context("hug", akNpc)                 ; a hero + NPC scene: camera, stages, waiting for the end
OGAIAnim.Tags("gesture,talk", akNpc, "npc")    ; the same by tags, without the core (GAM.Gesture / GAM.RunScene)
```

How a call through the core differs from a direct one:
- the core picks a scene for these people and this place: sex, furniture nearby, «the same person — the same manner»;
- the kind of call comes from the context: `overlay` — a gesture, `scene` — a scene;
- an **intimate context** (`intimacy`) plays only after consent under the core's rules, and only with adults.

«Life» actions (`act: hug`, `act: kiss` in trees) are already linked to contexts through `verbs:` in `life.yaml`: a successful action
plays its own context by itself.

---

## 9. Safety

> [!IMPORTANT]
> These rules are not switched off anywhere.

- **Closeness** (`intimate`) — only through the core and its consent: relationship stage, trust, sobriety, not in public, never for
  payment. Adults only, never a captive, never «forced».
- `GAM.PickScene`, `GAM.RunScene`, `GAM.Gesture` and `OGAIAnim.Tags` **never** pick an intimate scene by tags.
- **Children.** GAM.dll will not start a scene with closeness or romance tags (`intimate`, `romance`, `kiss`, `sex`, `nsfw`, `flirt`)
  if one of the actors is a child — no matter who calls it. The core will neither save nor install a scene in which a child has an
  intimate role.
- **External packs.** A scene from another mod's pack for two or more, in which no simple safe action (a hug, a kiss, a handshake, a
  dance) is named, is considered intimate and goes only through consent.
- **People and animals** — never.

If your mod calls a scene and it does not play, look into `GAM.log`. The line `is a scene of closeness: never with a child` means this
protection kicked in. It cannot be bypassed, and that is by design.

---

## 10. A mod for our manager

### 10.1 What to put in the archive

```
MyMod.zip
└─ Data/
   ├─ MyMod.esp                         ; your plugin (NPCs, CK dialogues, quests)
   ├─ Scripts/MyMod_*.pex               ; your scripts (do NOT include GAM.pex - it comes from the G.A.M. pack)
   └─ GAM/Scenes/mymod/
      ├─ barman_wipe_glass.gam          ; your scenes: id = "mymod/barman_wipe_glass"
      └─ barman_toast.gam
```

- Put scenes in **your own folder** (`GAM/Scenes/<your_mod>/`) so that ids do not clash with other people's.
- Give your scenes **honest tags**. Contexts and other mods' queries find them by tags. A pair — `pair`, one actor — `solo`, the upper
  body — `upper_body`, closeness — `intimate` (without this tag the core will not let a scene into an intimate context, and with it —
  nowhere else).
- State the dependency in the mod description: G.A.M. 0.3.0+ (and «Gestures from the game» if you call `gesture,talk…`).
- The manager installs such an archive like an ordinary mod (hard links and a journal, one-button rollback). G.A.M. finds new scenes
  itself (`GAM.Reload()` or at the next load).

> [!TIP]
> The easiest way to build a mod is in «Script studio»: «Save the mod» → tick your G.A.M. scenes — they travel in the `.ogmod` together
> with the dialogues ([SCRIPT_STUDIO.md](SCRIPT_STUDIO.md)).

### 10.2 A minimal scene file

```json
{
  "gam": 1, "id": "mymod/barman_toast", "name": "Тост", "mode": "absolute",
  "duration": 2.4, "loop": false, "blend": { "in": 0.3, "out": 0.45 },
  "tags": ["toast", "drink", "solo", "upper_body"],
  "roles": [ { "id": "a", "label": "A", "skeleton": "human", "sex": "any" } ],
  "tracks": [
    { "kind": "bone", "target": "a", "name": "RArm_UpperArm",
      "rot": [ { "t": 0, "q": [1, 0, 0, 0] }, { "t": 1.2, "q": [0.92, 0.38, 0, 0], "i": "auto" }, { "t": 2.4, "q": [1, 0, 0, 0] } ] }
  ],
  "props": [], "events": [], "markers": {},
  "meta": { "part": "upper" }
}
```

Main fields:
- `roles` — actors in order: `id`, `sex` (`male` / `female` / `any`), `skeleton` (`human`).
- `tracks` — bone keys; the quaternion is `[w, x, y, z]` in the bone's local axes, as in the game's clips.
  - `kind: root` — the actor's place and heading relative to the scene origin (for pairs).
- `markers` — `loop_start` / `loop_end` (a loop: entry — loop until stopped — exit) and `stage1…N` (stages, [5.1](#51-stages-how-a-scene-develops)).
- `meta.part` — the default body part; `meta.stages` — stages with the number of passes.

Scenes are easier to make in the G.A.M.
editor (boopi_mod → G.A.M.): the skeleton, timeline, keys, IK handles, a check and one-button installation into the game are all
there. How to work with it: [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md).

<p align="center"><img src="../../docs/images/gam-editor-ik-ai.en.png" alt="The G.A.M. editor: IK handles on the body, the light panel, the timeline and the AI animator log" width="860"></p>

*The G.A.M. editor: keys are placed with rings and IK handles right on the body, and the AI animator, given a description in words, places the participants and makes a first draft of the motion.*

> [!NOTE]
> G.A.M. never moves the service bones of vanilla clips (`Camera`, `CamTarget`, `Weapon*`, `AnimObject*`, IK targets, `PipboyBone`):
> the scene camera is its own, and weapons and items in hands follow the wrist.

### 10.3 Version check

```papyrus
if GAM.GetVersion() >= 300        ; 0.3.0: stages, camera, PickScene, RunScene, Gesture
    GAM.Gesture(akSpeaker, "gesture,salute")
endif
```

> [!TIP]
> If your mod must also work without G.A.M., call its functions from a separate script: then a missing GAM.pex breaks only that script,
> not the whole mod. Papyrus scripts are bound late.

---

## 11. How to test in the game

The console (`~`) — call any global function from it:

```
cgf "OGAIAnim.Tags" "gesture,surrender" 14 "player"                 ; the hero raises their hands (14 - the hero's reference)
cgf "OGAIAnim.Tags" "gesture,talk,confident" <refid> "npc"           ; a gesture on an NPC (refid - click the NPC in the console)
cgf "OGAIAnim.Tags" "gesture,talk,friendly" <refid> "npc" "head"     ; head only
cgf "OGAIAnim.Tags" "hug,pair" <refid> "both"                        ; a hero + NPC scene with the camera
```

The log `Documents\My Games\Fallout4\F4SE\GAM.log`:

| Line | What it means |
|---|---|
| `play 3 'gesture/hands_up' (1 actors, part 1, first 00000014)` | scene 3 started, body part 1 (upper) |
| `scene 3 'gesture/hands_up' ended after 3.4 s (frames: 00000014:205)` | it ended; how many frames each actor received (0 — the actor was not updated: unloaded or far away) |
| `scene 1 asked to stop at 20.8 s` | a script asked it to finish (`Stop`, the `WaitScene` limit) |
| `camera: following scene 1 (auto)` | the camera took hold of the scene |
| `no scene 'x'` / `needs 2 actors, got 1` / `does not fit role` | id not found / not enough actors / the race does not fit the role |

In the app all logs — the core's, the game's, Papyrus and F4SE — are collected into a single file `%APPDATA%\BoopiMod\logsll.log`, and
errors into `errors.log` next to it.

---

## 12. Common mistakes

**A gesture is not visible in a dialogue.**
The dialogue camera holds a close-up of the face. The upper body is hard to see, a nod (`part: head`) is easy. For arms use `when: after`
or a wide gesture.

**A scene for two in a dialogue «fights» the dialogue camera.**
Use `when: after` or start it in the `OnEnd` of the last line.

**The NPC stands sideways.**
In a full-body scene the actors are put on marks. For a gesture the actor stays where they stand — turn them yourself (`SetAngle`) or use a scene.

**A scene without stages runs for 20 seconds.**
That is the default limit for a looped scene. Set stages ([5.1](#51-stages-how-a-scene-develops)) or `afMaxSeconds`.

**Nothing plays, the log is empty.**
There is no suitable scene. Check `GAM.ListScenes("your,tags")` and install a pack with such tags.

---

## 13. What next

- [ANIMATION_IMPORT.md](ANIMATION_IMPORT.md) — where to get animations (Skyrim, OAR, Fallout 4 mods) and how to make your own scenes.
- [SCRIPT_STUDIO.md](SCRIPT_STUDIO.md) — Script studio: dialogues, animations in lines, Papyrus scripts, the `.ogmod` mod.
- [AI_DIALOGUE.md](AI_DIALOGUE.md) — the «Dialogues: AI» mode from the player's side.
- [VOICE.md](VOICE.md) — voice-over and speech recognition.
- [Guides index](README.md) · [Project home page](../../README.en.md)
