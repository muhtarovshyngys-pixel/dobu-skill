# Добу — файлы, пайплайн, версии Blender

## Корень
`C:\Users\Admin\Yandex.Disk\Dobudob\` (Яндекс.Диск). В каждой папке README. Неактуальное лежит в `_archive`.

| Папка | Что там | Правило |
|---|---|---|
| `01_ASSETS\01_CHARACTERS\DOBU\01_RIG` | риги Добу v1–v6, vWEB, `Final_rig\Dobu_Rig_v5.blend`, `Dobu_Rig_v5_b51.blend` (под Blender 5.1), `Dobu_Girl_Rig.blend`, `_archive\Animation_Library\Dobu_Animation_Library*.blend` | брать последнюю версию |
| `01_ASSETS\01_CHARACTERS\PA1M\01_RIG` | `Pa1m_rig_v4.blend` — актуальный риг ПЭМ (рука); `PAM_PoseLibrary\` — библиотека поз ПЭМ (asset library) | |
| `01_ASSETS\02_ENVIRONMENTS\01_ReadyAsset` | `DobuHub_v05.blend` (~246 МБ) — актуальная хаб-локация; v02, v04 — старые | окружение для эпизодов |
| `01_ASSETS\02_ENVIRONMENTS\02_Textures` | Sky, SkyNight, SkyStars, Moon | |
| `01_ASSETS\02_ENVIRONMENTS\03_Model` | DobuBed, roomWEB (runner, Shop) | |
| `01_ASSETS\03_PROPS` | `02_AssetLibrary` (voxel_plants, tooth_brush, void_sphere_vfx, Outline), `03_Tools` (`DOBU RenderSettings v1`, Outline_v3/v4, vertex alpha group generator) | |
| `01_ASSETS\04_AUDIO_LIBRARY` | звуки и музыка | |
| `02_PRODUCTION` | проекты эпизодов, рефы, рендеры, композ | открывать можно; важные данные менять только после бэкапа |
| `03_OUTPUT` | только финальные видео со звуком и композом | см. 05_visual_style.md |
| `01_ASSETS\01_CHARACTERS\DOBU\01_RIG\Dobu_Final\` | **финальный риг Добу** `Rig\Dobu_Rig_v12_5_FaceAnim.blend` (мешевое GN-лицо; копия `04_GAME\01_Assets\Final\`) и библиотека лица `FacePoses\Dobu_FacePoses_v12_5.blend` | брать для эпизодов вместо текстурного лица |
| `04_GAME\02_Production\Dobu\Dobu_<Class>\` | файлы экшнов тела: `Dobu_Base_anims.blend`, `Dobu_artist_anim.blend`, `Dobu_Scientist_anim(1).blend`, `Dobu_BD_anims_F.blend`, `Dobu_BL_Work_Hammer.blend`, `Dobu_Farmer_anims.blend` + `viewport_render` (mp4/gif) | экшны можно брать для поз и эмоций: удобнее **append через `bpy.data.libraries.load`** |

Рабочие файлы — только на Яндекс.Диске: эпизоды в `02_PRODUCTION\<Ep>\02_ProjectFiles\` (озвучка — в `audio\` рядом). Папка «Загрузки» у каждого своя, пути на неё в файлы не вшивать.

## Нейминг (из Notion команды)
- Файл эпизода: `E<номер>_<Название>_<шот 010/020/…>_<этап layout|anim|light|render>_v<###>`. Пример: `E01_Name_010_light_v002`.
- При переходе на новый этап (layout → anim → light → render) — пересохранить. При значительном изменении — новая версия.
- Финальные видео: `E01_Intro_v001`; особые версии — `E01_Intro_Square_v001`, `_Horizontal_`.
- Игровые экшны тела: `D_<Class>_<State>_<Variant>`.
  - Классы: Base, Ar (artist), Scientist/SC, BL/BD (builder), FRM (farmer), Dr (doctor), MCH (mechanic).
  - Idle_X — дыхательный луп без жестов; Emote_X — всё с жестами.
- Экшны лица: `DobuFace_*`, ассеты поз лица — `Face_*`.

## Структура рига (для линковки)
- **Dobu v12_5:**
  - коллекция `Dobu_Link` (внутри `DOBU_Head`, `character1`, `shapes`);
  - арматура `rig` (531 кость, Auto-Rig Pro: `c_*` контролы, `c_head.x`, IK/FK);
  - меши `Body`, `DOBU_ Head`, `DOBU_ Face`, `FC9_FaceDraw` (GN-лицо);
  - аутлайн `GEO-char-outlines` + коллекция `CharOutlineTargets`.
  - Сохранён в Blender 4.5 (перевод на 5.2 — по правилу в SKILL.md).
  - Есть сцена: 24 fps, 1–95.
- **PA1M v4:**
  - коллекция `Pa1m_Link` (Hand, bones, Collection 3, character1);
  - арматура `rig` (103 кости, ARP, правая рука: `c_shoulder.r`, `c_hand_fk.r`, пальцы `c_index1_base.r` и т.д. со свойством `bend_all`);
  - меши `hand_low`, `knucles`, `falange_2_2_low`;
  - текстуры в `PA1M\02_Textures` (hand_fx_gradient.exr, hand_fx_mask.png, hand_mat_*.1001).
  - Сохранён в Blender 4.5, открывается в 5.1 (headless); перевод на 5.2 — по правилу в SKILL.md.
- Линковать коллекцию `*_Link` + Library Override. Отдельный риг ничего не перезаписывает.

## Версии Blender
- Вся команда работает в **Blender 5.2** — анимация, риги, шейдинг и окружение. Новые риги и файлы — в 5.2.
- Риги Dobu v12_5 и PA1M v4 и библиотека поз ПЭМ пока сохранены в 4.5 и открываются в 5.x. Перевод на 5.2 — по правилу «Переход на новую версию Blender» в SKILL.md (новая версия файла, проверка аддонов, драйверов, GN-лица, экшнов, headless-открытия и линковки).
- Известное из прошлых переходов: v12_1 падал в 5.1 из-за VertexAlpha в GN-лице (исправлено в v12_2); файлы новой версии в старой не открывать.
- С 4.4 экшны слотовые: `action.layers[0].strips[0].channelbag(slot).fcurves`.

## Проверка в контейнере
- bpy под нужную версию Blender (`pip install bpy==5.2.*` и т.п., у каждой версии свой python).
- Скрипт не называть `inspect.py`: перекрывает stdlib и роняет bpy.
- Путь к файлу передавать через env var.
- Загрузка файлов с компьютера пользователя медленная: большие файлы стейджить по одному, параллельными вызовами.
