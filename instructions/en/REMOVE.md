# Removing boopi_mod from the game

[🇷🇺 Русский](../REMOVE.md) · 🇬🇧 English · [← Guides](README.md)

boopi_mod puts few files into the game folder (`Data`): it packs its mods into BA2 archives next to their plugin
(`BoopiCorp.esp` + `BoopiCorp - Main.ba2` + `BoopiCorp - Textures.ba2`) instead of thousands of separate files, and it
writes every file into its journal — so it can take all of it out again, to the byte. If you start the game from
**Mod Organizer 2**, boopi_mod can keep its mods there instead of in the game folder: «Mods → Other mod managers → Keep
mods in MO2».

## 1. From the app

**«Mods» → «Remove boopi_mod from the game» → «Remove from the game…».** Every file the app put into the game goes (the
other authors' mods installed through it too), the files that were there before come back, plugins.txt and our lines in
the game's settings go back to what they were, the `Data\GAM` folder (G.A.M. scenes from the studio) and old copies of
our files go to the Recycle Bin. A file you changed yourself stays where it is — the app names it. The app itself and the
downloaded mods stay: «Install» brings everything back.

## 2. From Windows — even after the app folder was deleted

**Settings → Apps → Installed apps → boopi_mod → Uninstall.** The app keeps a copy of its journal in
`%LOCALAPPDATA%\BoopiMod\uninstall` — the removal works from it, even without the app and its data folder. It takes out
of the game what item 1 does, then asks whether to delete the app's data and its folder (to the Recycle Bin).

## 3. If you already deleted everything by hand

Then remove what is left yourself — here is everything boopi_mod could have put into the game. The other authors' mods
the app installed (F4SE, Address Library, Buffout 4, the Unofficial Patch, High FPS Physics Fix, MCM, Baka ScrapHeap)
are their files: remove them like any mod if you do not need them.

<!-- removal-list:start -->
**boopi_mod's files** — delete them (in the game folder, usually `C:\Games\Fallout 4` or `...\steamapps\common\Fallout 4`):

- `Data\BoopiCorp - Main.ba2`
- `Data\BoopiCorp - Textures.ba2`
- `Data\BoopiCorp.esp`
- `Data\F4SE\Plugins\BoopiUI.dll`
- `Data\F4SE\Plugins\BoopiUI.ini`
- `Data\F4SE\Plugins\GAM.dll`
- `Data\F4SE\Plugins\GAM.ini`
- `Data\F4SE\Plugins\OldGenAI.dll`
- `Data\F4SE\Plugins\OldGenAI.ini`
- `Data\Interface\BoopiHUD.swf`
- `Data\Interface\BoopiInput.swf`
- `Data\Interface\gammenu.swf`
- `Data\OldGenStory - Main.ba2`
- `Data\OldGenStory.esp`
- `Data\Scripts\BoopiSynthPodScript.pex`
- `Data\Scripts\BoopiTurntableScript.pex`
- `Data\Scripts\BoopiUI.pex`
- `Data\Scripts\Fragments\Quests\QF_MQ101_0001ED86.pex`
- `Data\Scripts\Fragments\Quests\QF_MQ106_000229E7.pex`
- `Data\Scripts\Fragments\Quests\QF_MQ206_000229EC.pex`
- `Data\Scripts\GAM.pex`
- `Data\Scripts\OGAIAnim.pex`
- `Data\Scripts\OGAIDancerScript.pex`
- `Data\Scripts\OGAIHouseScript.pex`
- `Data\Scripts\OGAILifeScript.pex`
- `Data\Scripts\OGAILipsScript.pex`
- `Data\Scripts\OGAIPlaceScript.pex`
- `Data\Scripts\OGAIPlacesScript.pex`
- `Data\Scripts\OGAITalkInfoScript.pex`
- `Data\Scripts\OGAITerminalScript.pex`
- `Data\Scripts\OGAITreeInfoScript.pex`
- `Data\Scripts\OGSMilestoneScript.pex`
- `Data\Scripts\OGSNewStartScript.pex`
- `Data\Scripts\OGSVanillaScript.pex`
- `Data\Scripts\OGSWorldScript.pex`
- `Data\Scripts\OldGenAI.pex`
- `Data\Scripts\Source\User\GAM.psc`

**Folders only boopi_mod writes** (older versions put thousands of separate files there) — delete them whole:

- `Data\GAM\`
- `Data\F4SE\Plugins\BoopiUI\`
- `Data\Sound\Voice\BoopiCorp.esp\`
- `Data\Sound\Voice\OldGenStory.esp\`
- `Data\Textures\Boopi\`
- `Data\Materials\Boopi\`
- `Data\Meshes\Boopi\`
- `Data\Materials\Props\BoopiPrn001.BGSM … BoopiPrn011.BGSM`

**Our copies of the game's files** — delete them unless another mod of yours changes these files (the game takes its own again):

- `Data\Interface\MainMenu.swf`
- `Data\Interface\HUDMenu.swf`
- `Data\Interface\MapMarkers.swf`
- `Data\Interface\Pipboy_MapPage.swf`
- `Data\Interface\FontConfig.txt`
- `Data\Textures\SetDressing\Signage\AdvertsPosters02_d.DDS … AdvertsPosters07_d.DDS`
- `Data\Textures\SetDressing\Signage\BillboardsLrg*.DDS (8)`
- `Data\Unofficial Fallout 4 Patch - RU.esp`
- `Data\Unofficial Fallout 4 Patch - RU.txt`

**plugins.txt** (`%LOCALAPPDATA%\Fallout4\plugins.txt`) — remove the lines:

- `BoopiCorp.esp`
- `OldGenStory.esp`
- `Unofficial Fallout 4 Patch - RU.esp`

**Our plugins' logs** (`Documents\My Games\Fallout4\F4SE`): `BoopiUI.log`, `OldGenAI.log`, `GAM.log`.

**The app's data**: `%APPDATA%\BoopiMod` and `%LOCALAPPDATA%\BoopiMod` (characters, memory, settings, downloaded mods).
<!-- removal-list:end -->
