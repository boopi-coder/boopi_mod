# Убрать boopi_mod из игры

🇷🇺 Русский · [🇬🇧 English](en/REMOVE.md) · [← Руководства](README.md)

boopi_mod кладёт в папку игры (`Data`) немного файлов: свои моды он собирает в архивы BA2 рядом с плагином
(`BoopiCorp.esp` + `BoopiCorp - Main.ba2` + `BoopiCorp - Textures.ba2`), а не тысячами отдельных файлов, и каждый
файл записывает в журнал — поэтому может убрать всё обратно, до байта. Если игру запускаете из **Mod Organizer 2**,
моды boopi_mod можно держать там, а не в папке игры: «Моды → Другие менеджеры модов → Держать моды в MO2».

## 1. Из программы

**«Моды» → «Убрать boopi_mod из игры» → «Убрать из игры…».** Уйдут все файлы, которые программа положила в игру
(и моды других авторов, установленные через неё), вернутся файлы, что стояли там раньше, plugins.txt и наши строки в
настройках игры станут как были, папка `Data\GAM` (сцены G.A.M. из студии) и старые копии наших файлов уйдут в Корзину.
Файл, который вы меняли сами, останется на месте — программа назовёт его. Сама программа и скачанные моды останутся:
«Установить» вернёт всё обратно.

## 2. Из Windows — даже если папку программы уже удалили

**«Параметры» → «Приложения» → «Установленные приложения» → boopi_mod → «Удалить».** Программа хранит копию своего
журнала в `%LOCALAPPDATA%\BoopiMod\uninstall` — удаление работает по ней, даже без программы и без её папки с данными.
Оно убирает из игры то же, что и пункт 1, а потом спрашивает, удалить ли данные программы и её папку (в Корзину).

## 3. Если вы уже удалили всё вручную

Тогда уберите остатки сами — вот всё, что boopi_mod мог положить в игру. Моды других авторов, которые программа
ставила (F4SE, Address Library, Buffout 4, неофициальный патч, High FPS Physics Fix, MCM, Baka ScrapHeap), — это их
файлы: удаляйте их как обычные моды, если они вам не нужны.

<!-- removal-list:start -->
**Файлы boopi_mod** — удалите (в папке игры, обычно `C:\Games\Fallout 4` или `...\steamapps\common\Fallout 4`):

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

**Папки, которые пишет только boopi_mod** (старые версии клали туда тысячи отдельных файлов) — удалите целиком:

- `Data\GAM\`
- `Data\F4SE\Plugins\BoopiUI\`
- `Data\Sound\Voice\BoopiCorp.esp\`
- `Data\Sound\Voice\OldGenStory.esp\`
- `Data\Textures\Boopi\`
- `Data\Materials\Boopi\`
- `Data\Meshes\Boopi\`
- `Data\Materials\Props\BoopiPrn001.BGSM … BoopiPrn011.BGSM`

**Наши копии файлов игры** — удалите, если ни один другой ваш мод не меняет эти файлы (тогда игра снова возьмёт свои):

- `Data\Interface\MainMenu.swf`
- `Data\Interface\HUDMenu.swf`
- `Data\Interface\MapMarkers.swf`
- `Data\Interface\Pipboy_MapPage.swf`
- `Data\Interface\FontConfig.txt`
- `Data\Textures\SetDressing\Signage\AdvertsPosters02_d.DDS … AdvertsPosters07_d.DDS`
- `Data\Textures\SetDressing\Signage\BillboardsLrg*.DDS (8)`
- `Data\Unofficial Fallout 4 Patch - RU.esp`
- `Data\Unofficial Fallout 4 Patch - RU.txt`

**plugins.txt** (`%LOCALAPPDATA%\Fallout4\plugins.txt`) — уберите строки:

- `BoopiCorp.esp`
- `OldGenStory.esp`
- `Unofficial Fallout 4 Patch - RU.esp`

**Журналы наших плагинов** (`Документы\My Games\Fallout4\F4SE`): `BoopiUI.log`, `OldGenAI.log`, `GAM.log`.

**Данные программы**: `%APPDATA%\BoopiMod` и `%LOCALAPPDATA%\BoopiMod` (персонажи, память, настройки, скачанные моды).
<!-- removal-list:end -->
