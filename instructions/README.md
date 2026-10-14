<p align="center"><img src="../docs/images/banners/modders.jpg" alt="Руководства boopi_mod" width="100%"></p>

# <img src="../docs/images/icons/mods.png" width="56" align="absmiddle"> Руководства boopi_mod

🇷🇺 Русский · [🇬🇧 English](en/README.md) · [← На главную](../README.md)

> **Моддинг никогда не был так прост.** boopi_mod — прежде всего менеджер модов, в котором вы **создаёте**: свои анимации,
> сценарии, сцены и диалоги — вручную или с помощью ИИ. Эти руководства — путь от первой минуты до своего мода, которым
> можно поделиться одним файлом.

> [!WARNING]
> **Это бета (0.1.8):** возможны неточности и баги — пишите о них, чтобы я мог оперативно исправить. Жду обратной связи
> о проблемах и идеях — будем решать. [Открыть issue](https://github.com/boopi-coder/boopi_mod/issues/new/choose)

## С чего начать

| Хочу… | Читать |
|---|---|
| установить и запустить | [Установка и первый запуск](../README.md#установка-и-первый-запуск) |
| сделать свой диалог, сцену, мод | [Студия скриптов](SCRIPT_STUDIO.md) |
| проверить диалог, не запуская игру | [«▶ Сыграть диалог»](SCRIPT_STUDIO.md#31-играть-проверить-разговор-без-игры) |
| выложить свой мод на boopi.site | [Опубликовать на boopi.site](SCRIPT_STUDIO.md#97-опубликовать-на-boopisite) |
| импортировать анимации или нарисовать свою | [Импорт анимаций и редактор G.A.M.](ANIMATION_IMPORT.md) |
| свою историю: событие мира → разговор, сцена, квест | [Триггеры студии](SCRIPT_STUDIO.md#12-триггеры-своя-история), быстрее всего — [«+ История» и готовый пример](SCRIPT_STUDIO.md#128--история-и-готовый-пример) |
| вызывать анимации из диалогов и скриптов | [Анимации в модах](ANIMATION_GUIDE.md) |
| свободный разговор с людьми в игре | [ИИ-диалог](AI_DIALOGUE.md) |
| озвучку и голосовой ввод | [Голос](VOICE.md) |

## Все руководства

<table>
  <tr>
    <td width="72" align="center"><img src="../docs/images/icons/studio.png" width="64" alt=""></td>
    <td><b><a href="SCRIPT_STUDIO.md">Студия скриптов</a></b> · <a href="en/SCRIPT_STUDIO.md">EN</a><br>
    Свои диалоги, реплики из игры и ответвления от её колёс, озвучка с липсинком, «Сыграть диалог» без игры и версии файла,
    «Собрать и проверить», свой мод (<code>.ogmod</code>), установка чужого и публикация на boopi.site, анимации в репликах,
    триггеры своей истории («+ История» и готовый пример), Papyrus, ИИ-помощник и «Проверить в ИИ-режиме».</td>
  </tr>
  <tr>
    <td align="center"><img src="../docs/images/icons/import.png" width="64" alt=""></td>
    <td><b><a href="ANIMATION_IMPORT.md">Импорт анимаций и редактор G.A.M.</a></b> · <a href="en/ANIMATION_IMPORT.md">EN</a><br>
    Моды Fallout 4, анимации Skyrim, походки OAR, «перетащил — играет», свои сцены в 3D-редакторе: инструменты
    «Поворот / Сдвиг / Персонаж / Курс», IK-ручки, свет, лицо и камера сцены, ИИ-аниматор, библиотека сцен.</td>
  </tr>
  <tr>
    <td align="center"><img src="../docs/images/icons/gam.png" width="64" alt=""></td>
    <td><b><a href="ANIMATION_GUIDE.md">Анимации в модах на G.A.M.</a></b> · <a href="en/ANIMATION_GUIDE.md">EN</a><br>
    Жест и сцена, события сцены, камера, вызов из скриптов, диалогов и «Жизни», файлы сцен, мод для менеджера, проверка в игре, безопасность.</td>
  </tr>
  <tr>
    <td align="center"><img src="../docs/images/icons/ai-dialogue.png" width="64" alt=""></td>
    <td><b><a href="AI_DIALOGUE.md">ИИ-диалог</a></b> · <a href="en/AI_DIALOGUE.md">EN</a><br>
    Режим «Прогрессивный ИИ-диалог»: как включить, «Сказать своё…», ввод с клавиатуры (в том числе по-русски), голос на
    <b>V</b>, виджеты <b>F10</b>, что ИИ может и чего не может; для мододелов — проверка диалога в ИИ-режиме.</td>
  </tr>
  <tr>
    <td align="center"><img src="../docs/images/icons/voice.png" width="64" alt=""></td>
    <td><b><a href="VOICE.md">Голос</a></b> · <a href="en/VOICE.md">EN</a><br>
    Озвучка (Edge, ElevenLabs, OpenAI, XTTS-v2, Silero), клонирование голоса, распознавание речи и push-to-talk.</td>
  </tr>
</table>

## Пути из руководств

| Что | Где |
|---|---|
| Данные и настройки | `%APPDATA%\BoopiMod\` |
| Свои диалоги | `%APPDATA%\BoopiMod\talk` |
| Версии файлов студии | `%APPDATA%\BoopiMod\talk\.history` |
| Установленные моды студии | `%APPDATA%\BoopiMod\studio_mods` |
| Диапазоны записей деревьев | `%APPDATA%\BoopiMod\plugin\tree_slots.json` |
| Сцены G.A.M. | `%APPDATA%\BoopiMod\gam\scenes` |
| Свои контексты G.A.M. | `%APPDATA%\BoopiMod\gam\contexts` |
| Сохранённые моды | `Документы\BoopiMod\Mods` |
| Журналы | `%APPDATA%\BoopiMod\logs` |
| Программа | обычно `C:\Games\boopi_mod` |
