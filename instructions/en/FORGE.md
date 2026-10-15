<p align="center"><img src="../../docs/images/forge-retexture.en.png" alt="F.O.R.G.E.: a new texture on the Vault 111 jumpsuit" width="100%"></p>

# <img src="../../docs/images/icons/forge.png" width="56" align="absmiddle"> F.O.R.G.E. — 3D objects and textures

[🇷🇺 Русский](../FORGE.md) · 🇬🇧 English

[← All guides](README.md) · [← Project home page](../../README.en.md)

> [!NOTE]
> F.O.R.G.E. is the younger sibling of [G.A.M.](ANIMATION_IMPORT.md): G.A.M. moves the bodies, F.O.R.G.E. dresses and paints
> them. Any 3D object of your game — furniture, items, weapons, clothes and armor, people and creatures — with its textures:
> look at it, repaint it and put it into the game with one button. The game's files are read **only from your computer** —
> the app does not contain them and never sends them anywhere.

> ### ⏱ In 1 minute
>
> - **F.O.R.G.E.** is in the menu on the left, right after G.A.M. On the left — what your game has, in the middle — the 3D view,
>   on the right — the parts of the model and their textures.
> - Pick a thing → a part of the model → a **texture slot** (color, relief, gloss, glow) → **«Save as PNG»** to paint over the
>   original.
> - **«New picture…»** — PNG, JPG or DDS. The app converts it into the right DDS format with mipmaps and shows it on the model
>   at once.
> - **«Into the game»** — the change goes into the **«My textures»** mod (it is on the «Mods» page too). Remove the change and
>   the game has exactly the texture it had.
> - Your textures can be saved as a **`.ogmod` pack** and shared like any mod.
> - Have a texture mod already — a folder or a `.zip` with `Textures\…`? **Drop it onto the page**: F.O.R.G.E. shows what
>   fits your game and puts it all in with one button (the **«Import»** tab, [section 7](#7-a-texture-mod-a-folder-or-a-zip)).

## Contents

1. [What you can open](#1-what-you-can-open)
2. [The 3D view and texture slots](#2-the-3d-view-and-texture-slots)
3. [Repaint: a new picture](#3-repaint-a-new-picture)
4. [Into the game: «My textures»](#4-into-the-game-my-textures)
5. [A texture pack: share it](#5-a-texture-pack-share-it)
6. [Open your own model (OBJ, glTF, NIF)](#6-open-your-own-model-obj-gltf-nif)
7. [A texture mod: a folder or a .zip](#7-a-texture-mod-a-folder-or-a-zip)
8. [If something is wrong](#8-if-something-is-wrong)
9. [What comes next](#9-what-comes-next)

---

## 1. What you can open

<p align="center"><img src="../../docs/images/forge-browse.en.png" alt="The F.O.R.G.E. catalog: the Vault 111 jumpsuit in the 3D view" width="100%"></p>

Four tabs on the left:

| Tab | What is there |
|---|---|
| **Catalog** | Everything your game has a model for, **with the game's own names**: furniture, objects, items, weapons, clothes and armor, people (their faces), creatures. Search by name, editor id, form id (as the console shows it: `0001EED7`) or model path. |
| **Files** | Every `.nif` model of the game's archives and loose files — for what the catalog does not list. Search by words of the path. |
| **My textures** | Your changes that are in the game now. |
| **Import** | A model from disk (OBJ, glTF / GLB, NIF) and a texture mod — a folder or a `.zip`. |

The catalog is built from **your game's plugins** (official, DLC and mods in load order) — about a minute the first time,
instant afterwards. Clothes open as **«Female» / «Male» / «On the ground»** (buttons above the 3D view), a person with their
face from the game and a body. When a mod replaces a texture or a model, F.O.R.G.E. shows the one the game sees: a loose file
wins over an archive, the archive of a plugin lower in the load order wins over one higher up.

## 2. The 3D view and texture slots

- **Rotate** with the left mouse button, **pan** with the right one, **zoom** with the wheel; **«Show all»** brings the view back.
- **«Textures»** — the model with its textures or plain grey; **«Wireframe»** — the mesh.
- **Background** — three dots: dark, neutral grey (colours read truest) and light (for dark things); the choice is remembered.
- **«Snapshot»** — save the view as a PNG in `Documents\BoopiMod\Screenshots` («Show» opens the folder).
- **A click on the model** picks a part of it; the parts are listed on the right (with their triangle counts).
- The picked part's **texture slots**: color (diffuse), relief (normal), gloss (specular), glow and the rest (reflection,
  palette…), with the file's path. **«from the material»** means a material file (`.bgsm` / `.bgem`) names the texture;
  **«from the model»** — the model itself does (faces, for instance).
- Under the slot: the format (`BC7_UNORM`, `BC5_UNORM`…), the size, the mipmap count and **where** the game takes the file from
  (an archive or a loose file).

Color, relief, gloss and glow can be edited; the other slots are shown for reference.

## 3. Repaint: a new picture

1. Pick a slot → **«Save as PNG»**. The file goes to `Documents\BoopiMod\Textures`, **«Show»** opens the folder. Paint over it —
   that way the UV layout matches the model.
2. **«New picture…»** — PNG, JPG, BMP, TGA, WebP or DDS. F.O.R.G.E. converts it with **texconv** (it comes with the app):
   - into **the same DDS format** the original has (BC1, BC3, BC5, BC7…), with a **full mipmap chain**;
   - on **powers of two** (or **«The original's size»** in «Conversion options»);
   - **a normal map stays a normal map**: its vectors are evened out, a missing blue channel is rebuilt, BC5 stays BC5. A picture
     from an OpenGL tool (Blender, Substance in OpenGL mode) — tick **«flip the green channel»**; only a black-and-white height map —
     **«It is a height map»**, and the relief is made from it;
   - when the picture has no transparency and the original has (hair, cloth with cut-outs), **the original's transparency is kept**.
3. The new texture **shows on the model at once**. **«Show the original»** compares. Warnings tell when the proportions differ
   from the original's (the UV layout will stretch the picture) or a picture in the relief slot does not look like a normal map.

## 4. Into the game: «My textures»

Before **«Into the game»** choose what changes:

| Option | What happens |
|---|---|
| **Replace this texture file** | The new file takes the game texture's place — **everything** that uses it shows it. |
| **This material only** | F.O.R.G.E. makes a copy of the material (from your own game) whose slot points at your new texture. Only what uses that material changes. |

Every change is **one entry** of the **«My textures»** mod. The mod is installed through the mod manager's journal like any other:

- **«Remove»** on an entry («My textures» tab) — the game shows **exactly the file** it had before the change (byte for byte),
  another mod's file too if one was there;
- on the **«Mods»** page «My textures» can be removed as a whole — the entries stay in the list marked «not in the game», and
  «Into the game» brings them back;
- a second change of the same texture replaces the first, changes of different slots of one material gather into one entry.

The game must be allowed to read loose files over its archives (`Fallout4Custom.ini`: `bInvalidateOlderFiles=1`). When it is not,
F.O.R.G.E. shows a warning at the top with a **«Turn on»** button.

> [!TIP]
> Install textures while the game is closed: the game does not read again a texture it has already loaded — after an
> install, start the game anew.

<p align="center"><img src="../../docs/images/forge-ingame.jpg" alt="In the game: the repainted couch (its material only) and Vault 111 jumpsuit" width="100%"></p>

## 5. A texture pack: share it

<p align="center"><img src="../../docs/images/forge-mine.en.png" alt="My textures and a texture pack" width="80%"></p>

**«My textures»** tab → **«Texture pack (.ogmod)»**: name, author, version, description → **«Save the pack»**. Tick the changes you
want (with none ticked every change goes in). The pack is saved to `Documents\BoopiMod\Mods`.

- The pack holds **only your textures** — not a single file of the game. A «this material only» change travels as a recipe: the
  boopi_mod of whoever installs the pack makes the material copy **from their own game**.
- A pack installs like any boopi_mod mod: drop the `.ogmod` on the app (or install it from boopi.site) — it shows on the «Mods»
  page and is removed from there, every file through the journal.
- It is published the same way as a studio mod ([Publish to boopi.site](SCRIPT_STUDIO.md#97-publish-to-boopisite)). Share only
  your own work: a picture repainted over a game texture remains derived from it.

## 6. Open your own model (OBJ, glTF, NIF)

<p align="center"><img src="../../docs/images/forge-open.en.png" alt="An OBJ model of your own in F.O.R.G.E." width="100%"></p>

**«Import»** tab → **«Open a model…»** (or drop the model's files onto the page):

- **OBJ** — pick the `.obj`, its `.mtl` and pictures together; **glTF** — the `.gltf` with its `.bin` and pictures, or a single `.glb`;
- **NIF** — a Fallout 4 model (20.2.0.7); its textures named by game paths come from your game.

If the model names pictures that are not among the chosen files, F.O.R.G.E. lists them — pick them together with the
model or drop the model's whole folder onto the page.

The model shows in the 3D view, its materials and pictures are listed on the left. **«Into the picked slot»** hands a picture of
the model to the picked slot of a game texture (pick a thing and a slot in the catalog first) — then go on as in
[section 3](#3-repaint-a-new-picture).

## 7. A texture mod: a folder or a .zip

<p align="center"><img src="../../docs/images/forge-import.en.png" alt="F.O.R.G.E.: a texture mod before it goes in — what fits the game" width="100%"></p>

If you already have textures laid out like the game's (`Data\Textures\Clothes\…`) — a DDS set of your own or a texture
mod you downloaded — there is no need to put them in one by one:

1. The **«Import»** tab → **«Folder…»** or **«.zip or files…»** — or just **drop the folder / `.zip` onto the page**.
2. F.O.R.G.E. matches every file to the game's files and shows the list:
   - **fits** — it replaces a texture your game has (with its format and size; «replaces your entry» when you changed it already);
   - **not in the game** — a new file of the mod that only the mod itself uses (install such mods whole on the «Mods» page);
   - **skipped** — not a texture: models, materials, plugins, readmes;
   - **error** / **duplicate** — a DDS that cannot be read, or the mod has the same texture already (a DDS wins over a PNG).
   A path without a `Textures` folder (say `MyMod\Clothes\x_d.dds`) is matched by its longest tail the game knows.
3. Untick what you do not want → **«Into the game: N»**. Every texture becomes an entry of «My textures» of its own — take
   them out one by one and the game has its own texture back, byte for byte. To take the whole mod out at once: «My textures» →
   **«Choose «the mod's name»»** → **«Remove the chosen»**.

A DDS of the mod goes in as it is; a PNG, JPG or TGA is converted to the original texture's format with mipmaps, as in
[section 3](#3-repaint-a-new-picture). Put textures in while the game is closed.

## 8. If something is wrong

| What | What to do |
|---|---|
| «The game is not found» | Set the Fallout 4 folder in «Settings → Game». |
| The catalog is empty or slow | The plugins take about a minute the first time; the progress bar is above the list. |
| «texconv is missing» | texconv comes with the app; reinstall boopi_mod. |
| The texture does not show in the game | «Turn on» in the warning at the top (loose files); restart the game. |
| A texture mod: «no file replaces a texture» | The paths in the mod must follow the game's: `Textures\Clothes\…\x_d.dds`. Unpack a 7z or rar and pick the folder. |
| A model does not open | F.O.R.G.E. reads Fallout 4 NIF (20.2.0.7); open models of other games as OBJ / glTF. |
| Put everything back | «My textures» → «Remove» on the entry, or remove «My textures» on the «Mods» page. |

## 9. What comes next

In 0.1.9 F.O.R.G.E. changes the **textures** of the game's models. Your own model can be opened and looked at and its pictures
used, but **a new model cannot go into the game** yet: that needs the app to write NIF files (geometry, skeleton and weights,
collision) and plugin records — the next step of F.O.R.G.E. Retexturing a single character or armor through the game's records
(TXST / material swaps) is ahead too; for now the «This material only» option does the same job.

---

[← All guides](README.md) · [Animation import and the G.A.M. editor](ANIMATION_IMPORT.md)
