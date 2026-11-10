# Каталог экшнов и поз Добу и ПЭМ

Этот файл — для подбора движения под задачу. Сначала найди подходящий раздел по ситуации, затем клип по описанию и длине. Если ничего не подходит — анимируй сам по `character-animation-craft`, но сначала попробуй собрать из 2–3 клипов в NLA.

## Как применять клип (обе библиотеки)
1. Открыть файл шота, в нём персонаж — линк + override из рига (Добу `Dobu_Rig_v5`/`v12_5`, ПЭМ `Pa1m_rig_v4`).
2. File → Link/Append → `<библиотека>.blend` → Action → нужный экшн (Append, если будешь править).
3. NLA: экшн как стрип на нижний трек `BASE_clips`. Клипы начинаются с `c_pos`/`c_traj` = 0, поэтому персонаж остаётся там, где стоит; поворот/смещение — через `<char>_ctrl` или `c_traj` на верхнем слое.
4. Стык клипов: blend in/out 3–6 кадров. Первую/последнюю позу под шот менять на отдельном треке `POSE_layer` (COMBINE), а не внутри клипа.
5. Движение подгонять под камеру шота: можно зеркалить путь, разворачивать, менять скорость (Scale стрипа), брать часть клипа (Action Clip start/end).
6. `move`-клипы с большим перемещением и трюки (`fall_launch_away`, `rope_*`, `fly_*`) — шотовые: брать позы и тайминг, путь переделывать под сцену.
7. Лицо Добу — отдельно: позы `Face_*` на кадрах реплики/реакции (раздел «Лицо Добу»). Тело и лицо не смешивать в одном экшне.

Длина — в кадрах при 24 fps. «Источник» — эпизод и кадры исходного экшна (оттуда можно посмотреть контекст в ролике).

---

## Добу — клипы тела (256)
Файл: `01_ASSETS\01_CHARACTERS\DOBU\01_RIG\Dobu_AnimClips\Dobu_AnimClips_v001.blend` (Blender 4.5, риг `Final_rig\Dobu_Rig_v5` линком; клипы ставятся на любой риг Добу v2–v5 и v12_5 — имена контролов одинаковые). Видео-листы — `Dobu_AnimClips\sheets\`.
Имя: `Dobu_<act|move|jump>_<движение>_<эпизод>_<кадр начала>`. act — на месте, move — перемещение > 1.5 м, jump — подъём корня > 0.3 м.


### Айдлы и стойки (20)
**Когда:** фон во время чужой реплики, ожидание, «живой» холд; брать кусок и зацикливать, начало и конец сводить к базовой позе.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_act_back_view_idle_E19_725` | 142 | назад/спиной, вид, айдл | E19_RacingVote 725–866 |
| `Dobu_act_back_view_idle_E26_740` | 103 | назад/спиной, вид, айдл | E26_NotWinner 740–842 |
| `Dobu_act_badminton_ready_E27_101` | 41 | бадминтон, готовность | E27_Badminton 101–141 |
| `Dobu_act_fight_stance_E34_80` | 23 | драка, стойка | E34_LostBudget 80–102 |
| `Dobu_act_fight_stance_idle_E34_108` | 42 | драка, стойка, айдл | E34_LostBudget 108–149 |
| `Dobu_act_idle_arm_swing_E03_109` | 108 | айдл, рука, замах/раскачка | E03_Jenga 109–216 |
| `Dobu_act_idle_arm_swing_E11_8` | 12 | айдл, рука, замах/раскачка | E11_Platforms 8–19 |
| `Dobu_act_idle_back_E16_255` | 38 | айдл, назад/спиной | E16_Tamagochi 255–292 |
| `Dobu_act_idle_back_E40_1022` | 19 | айдл, назад/спиной | E40_Debug_Platform 1022–1040 |
| `Dobu_move_idle_leap_E38_13` | 141 | айдл, длинный прыжок; с перемещением | E38_Rope_Climbing 13–153 |
| `Dobu_act_idle_long_E14_64` | 113 | айдл, длинный | E14_BluePrince 64–176 |
| `Dobu_act_idle_look_E39_0` | 47 | айдл, смотрит | E39_TheGod 0–46 |
| `Dobu_act_idle_nervous_E19_1099` | 54 | айдл, нервно | E19_RacingVote 1099–1152 |
| `Dobu_act_idle_shift_E05_140` | 114 | айдл, перенос веса | E05_Mirror 140–253 |
| `Dobu_act_idle_stand_E38_93` | 20 | айдл, встаёт/стоит | E38_Rope_Climbing 93–112 |
| `Dobu_act_idle_turn_E37_177` | 49 | айдл, поворот | E37_FreeDay 177–225 |
| `Dobu_act_idle_weight_shift_E11_1260` | 51 | айдл, перенос веса | E11_Platforms 1260–1310 |
| `Dobu_act_ready_step_E27_135` | 29 | готовность, шаг | E27_Badminton 135–163 |
| `Dobu_act_stand_sway_E11_805` | 13 | встаёт/стоит, покачивая | E11_Platforms 805–817 |
| `Dobu_act_tiny_idle_E16_233` | 63 | крошечный, айдл | E16_Tamagochi 233–295 |

### Ходьба (46)
**Когда:** проход по кадру, подход к объекту/персонажу, уход; для своего цикла сверяться с правилами походки в character-animation-craft.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_act_crouch_creep_E05_333` | 38 | присед, крадётся | E05_Mirror 333–370 |
| `Dobu_move_crouch_sneak_E02_205` | 43 | присед, крадётся; с перемещением | E02_Sphere 205–247 |
| `Dobu_move_hop_walk_E02_96` | 30 | подскок, ходьба; с перемещением | E02_Sphere 96–125 |
| `Dobu_act_shuffle_step_E02_125` | 66 | переминается, шаг | E02_Sphere 125–190 |
| `Dobu_act_sneak_E34_80` | 68 | крадётся | E34_LostBudget 80–147 |
| `Dobu_move_sneak_walk_crouch_E27_180` | 118 | крадётся, ходьба, присед; с перемещением | E27_Badminton 180–297 |
| `Dobu_act_step_lean_E40_724` | 18 | шаг, наклон | E40_Debug_Platform 724–741 |
| `Dobu_act_step_side_E23_300` | 31 | шаг, в сторону/боком | E23_Sleeper 300–330 |
| `Dobu_act_step_turn_E02_125` | 14 | шаг, поворот | E02_Sphere 125–138 |
| `Dobu_act_turn_walk_away_E40_550` | 29 | поворот, ходьба, прочь | E40_Debug_Platform 550–578 |
| `Dobu_move_walk_arms_out_E28_1` | 71 | ходьба, руки, в стороны; с перемещением | E28_Spoiled 1–71 |
| `Dobu_move_walk_arms_out_E37_515` | 90 | ходьба, руки, в стороны; с перемещением | E37_FreeDay 515–604 |
| `Dobu_move_walk_arms_up_E17_2` | 54 | ходьба, руки, вверх; с перемещением | E17_Shell 2–55 |
| `Dobu_move_walk_away_hop_E20_41` | 31 | ходьба, прочь, подскок; с перемещением | E20_Runner 41–71 |
| `Dobu_move_walk_away_turn_E37_242` | 58 | ходьба, прочь, поворот; с перемещением | E37_FreeDay 242–299 |
| `Dobu_move_walk_calm_E28_94` | 41 | ходьба, спокойно; с перемещением | E28_Spoiled 94–134 |
| `Dobu_move_walk_carry_E18_105` | 27 | ходьба, несёт перед собой; с перемещением | E18_ArnoldRoom 105–131 |
| `Dobu_move_walk_crouch_jump_E40_159` | 40 | ходьба, присед, прыжок; с перемещением | E40_Debug_Platform 159–198 |
| `Dobu_move_walk_dive_E40_1074` | 37 | ходьба, нырок/бросок вперёд; с перемещением | E40_Debug_Platform 1074–1110 |
| `Dobu_move_walk_fall_E29_827` | 44 | ходьба, падение; с перемещением | E29_Door 827–870 |
| `Dobu_move_walk_forward_E14_205` | 87 | ходьба, вперёд; с перемещением | E14_BluePrince 205–291 |
| `Dobu_move_walk_forward_E41_444` | 50 | ходьба, вперёд; с перемещением | E41_FIre 444–493 |
| `Dobu_act_walk_gesture_E41_181` | 118 | ходьба, жест | E41_FIre 181–298 |
| `Dobu_move_walk_gesture_turn_E11_1128` | 51 | ходьба, жест, поворот; с перемещением | E11_Platforms 1128–1178 |
| `Dobu_move_walk_hop_E37_0` | 28 | ходьба, подскок; с перемещением | E37_FreeDay 0–27 |
| `Dobu_move_walk_jump_E16_255` | 22 | ходьба, прыжок; с перемещением | E16_Tamagochi 255–276 |
| `Dobu_move_walk_long_E41_510` | 117 | ходьба, длинный; с перемещением | E41_FIre 510–626 |
| `Dobu_move_walk_off_E01_130` | 53 | ходьба, уходит; с перемещением | E01_Intro 130–182 |
| `Dobu_move_walk_push_forward_E18_37` | 63 | ходьба, толкает, вперёд; с перемещением | E18_ArnoldRoom 37–99 |
| `Dobu_move_walk_scratch_head_E01_143` | 47 | ходьба, чешет, голова; с перемещением | E01_Intro 143–189 |
| `Dobu_move_walk_short_E01_63` | 14 | ходьба, короткий; с перемещением | E01_Intro 63–76 |
| `Dobu_move_walk_side_E31_168` | 21 | ходьба, в сторону/боком; с перемещением | E31_LeftForever 168–188 |
| `Dobu_move_walk_side_long_E19_1` | 105 | ходьба, в сторону/боком, длинный; с перемещением | E19_RacingVote 1–105 |
| `Dobu_move_walk_side_short_E19_1` | 105 | ходьба, в сторону/боком, короткий; с перемещением | E19_RacingVote 1–105 |
| `Dobu_move_walk_side_slow_E19_1` | 105 | ходьба, в сторону/боком, медленно; с перемещением | E19_RacingVote 1–105 |
| `Dobu_move_walk_side_steady_E19_1` | 105 | ходьба, в сторону/боком, ровно; с перемещением | E19_RacingVote 1–105 |
| `Dobu_move_walk_side_turn_E19_883` | 64 | ходьба, в сторону/боком, поворот; с перемещением | E19_RacingVote 883–946 |
| `Dobu_move_walk_steps_E02_113` | 13 | ходьба, шаги; с перемещением | E02_Sphere 113–125 |
| `Dobu_move_walk_sway_arms_E27_165` | 62 | ходьба, покачивая, руки; с перемещением | E27_Badminton 165–226 |
| `Dobu_move_walk_to_camera_E16_125` | 62 | ходьба → на камеру; с перемещением | E16_Tamagochi 125–186 |
| `Dobu_move_walk_toward_E23_181` | 42 | ходьба, к камере; с перемещением | E23_Sleeper 181–222 |
| `Dobu_move_walk_turn_around_E18_131` | 39 | ходьба, поворот, кругом; с перемещением | E18_ArnoldRoom 131–169 |
| `Dobu_move_walk_turn_to_camera_E19_990` | 112 | ходьба, поворот → на камеру; с перемещением | E19_RacingVote 990–1101 |
| `Dobu_move_walk_wave_arms_E21_154` | 109 | ходьба, машет, руки; с перемещением | E21_ShortQueen 154–262 |
| `Dobu_move_walk_wave_stumble_E32_666` | 43 | ходьба, машет, спотыкается; с перемещением | E32_Builder 666–708 |
| `Dobu_move_walk_wobbly_E27_395` | 116 | ходьба, шатко; с перемещением | E27_Badminton 395–510 |

### Бег, рывки, нырки (20)
**Когда:** погоня, бегство, спешка, старт с места.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_move_dive_forward_E11_1081` | 19 | нырок/бросок вперёд, вперёд; с перемещением | E11_Platforms 1081–1099 |
| `Dobu_act_dive_low_E27_328` | 24 | нырок/бросок вперёд, низко | E27_Badminton 328–351 |
| `Dobu_move_run_arms_flail_E11_951` | 52 | бег, руки, размахивает руками; с перемещением | E11_Platforms 951–1002 |
| `Dobu_move_run_cycle_E32_403` | 34 | бег, цикл; с перемещением | E32_Builder 403–436 |
| `Dobu_move_run_dive_E05_446` | 10 | бег, нырок/бросок вперёд; с перемещением | E05_Mirror 446–455 |
| `Dobu_move_run_dive_E27_314` | 22 | бег, нырок/бросок вперёд; с перемещением | E27_Badminton 314–335 |
| `Dobu_move_run_hop_E40_597` | 64 | бег, подскок; с перемещением | E40_Debug_Platform 597–660 |
| `Dobu_move_run_hunched_E09_142` | 39 | бег, сгорбившись; с перемещением | E09_Liminal Space 142–180 |
| `Dobu_move_run_jump_E40_339` | 15 | бег, прыжок; с перемещением | E40_Debug_Platform 339–353 |
| `Dobu_move_run_jump_E40_583` | 13 | бег, прыжок; с перемещением | E40_Debug_Platform 583–595 |
| `Dobu_move_run_leap_E13_1` | 95 | бег, длинный прыжок; с перемещением | E13_LiminalRun 1–95 |
| `Dobu_move_run_long_E13_147` | 104 | бег, длинный; с перемещением | E13_LiminalRun 147–250 |
| `Dobu_move_run_look_back_E11_857` | 95 | бег, смотрит, назад/спиной; с перемещением | E11_Platforms 857–951 |
| `Dobu_move_run_lunge_E11_1100` | 26 | бег, выпад; с перемещением | E11_Platforms 1100–1125 |
| `Dobu_move_run_lunge_E27_257` | 27 | бег, выпад; с перемещением | E27_Badminton 257–283 |
| `Dobu_move_run_off_E11_222` | 32 | бег, уходит; с перемещением | E11_Platforms 222–253 |
| `Dobu_move_run_short_E27_355` | 24 | бег, короткий; с перемещением | E27_Badminton 355–378 |
| `Dobu_move_run_start_E40_681` | 14 | бег, старт; с перемещением | E40_Debug_Platform 681–694 |
| `Dobu_move_run_start_E40_878` | 13 | бег, старт; с перемещением | E40_Debug_Platform 878–890 |
| `Dobu_act_swing_run_E27_299` | 26 | замах/раскачка, бег | E27_Badminton 299–324 |

### Прыжки и подскоки (31)
**Когда:** радость, преодоление препятствия, запрыгивание; jump = корень поднимается > 0.3 м.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_move_cartwheel_E02_22` | 19 | колесо; с перемещением | E02_Sphere 22–40 |
| `Dobu_act_cheer_jump_arms_up_E02_95` | 11 | радость, прыжок, руки, вверх | E02_Sphere 95–105 |
| `Dobu_jump_climb_jump_E38_132` | 19 | лазание, прыжок | E38_Rope_Climbing 132–150 |
| `Dobu_jump_crouch_hop_E01_35` | 28 | присед, подскок | E01_Intro 35–62 |
| `Dobu_jump_crouch_jump_E01_19` | 54 | присед, прыжок | E01_Intro 19–72 |
| `Dobu_jump_faceplant_E31_429` | 54 | прыжок, лицом в пол | E31_LeftForever 429–482 |
| `Dobu_jump_flip_E29_683` | 73 | прыжок, сальто/переворот | E29_Door 683–755 |
| `Dobu_move_flip_headstand_E38_232` | 12 | сальто/переворот, на голове; с перемещением | E38_Rope_Climbing 232–243 |
| `Dobu_jump_flip_spin_E38_207` | 22 | прыжок, сальто/переворот, вращение | E38_Rope_Climbing 207–228 |
| `Dobu_jump_forward_E05_140` | 52 | прыжок, вперёд | E05_Mirror 140–191 |
| `Dobu_jump_hop_E27_368` | 21 | подскок | E27_Badminton 368–388 |
| `Dobu_move_hop_arms_back_E34_92` | 35 | подскок, руки, назад/спиной; с перемещением | E34_LostBudget 92–126 |
| `Dobu_act_hop_to_walk_E41_43` | 96 | подскок → ходьба | E41_FIre 43–138 |
| `Dobu_jump_hop_up_E38_580` | 16 | подскок, вверх | E38_Rope_Climbing 580–595 |
| `Dobu_act_hug_jump_E38_128` | 15 | обнимает, прыжок | E38_Rope_Climbing 128–142 |
| `Dobu_move_jump_flail_E38_198` | 49 | прыжок, размахивает руками; с перемещением | E38_Rope_Climbing 198–246 |
| `Dobu_act_jump_grab_E38_306` | 10 | прыжок, хватается | E38_Rope_Climbing 306–315 |
| `Dobu_move_jump_land_E34_9` | 32 | прыжок, приземление; с перемещением | E34_LostBudget 9–40 |
| `Dobu_act_jump_reach_up_E31_213` | 44 | прыжок, тянется, вверх | E31_LeftForever 213–256 |
| `Dobu_act_lunge_jump_E02_257` | 16 | выпад, прыжок | E02_Sphere 257–272 |
| `Dobu_jump_roll_E29_612` | 72 | прыжок, перекат | E29_Door 612–683 |
| `Dobu_act_small_hop_E11_634` | 34 | маленький, подскок | E11_Platforms 634–667 |
| `Dobu_jump_star_E02_290` | 17 | прыжок, звездой | E02_Sphere 290–306 |
| `Dobu_act_think_then_hop_E05_434` | 22 | думает, затем, подскок | E05_Mirror 434–455 |
| `Dobu_jump_tiny_hop_E16_186` | 39 | крошечный, подскок | E16_Tamagochi 186–224 |
| `Dobu_move_tumble_flip_E02_3` | 19 | кувырок, сальто/переворот; с перемещением | E02_Sphere 3–21 |
| `Dobu_move_tumble_flip_E38_416` | 20 | кувырок, сальто/переворот; с перемещением | E38_Rope_Climbing 416–435 |
| `Dobu_move_tumble_flip_fall_E02_284` | 37 | кувырок, сальто/переворот, падение; с перемещением | E02_Sphere 284–320 |
| `Dobu_jump_up_E11_66` | 50 | прыжок, вверх | E11_Platforms 66–115 |
| `Dobu_jump_up_E21_115` | 42 | прыжок, вверх | E21_ShortQueen 115–156 |
| `Dobu_move_wave_jump_E32_334` | 20 | машет, прыжок; с перемещением | E32_Builder 334–353 |

### Падения, кувырки, удары (38)
**Когда:** комедийные падения, споткнулся, отбросило взрывом/ударом, кувырок и подъём.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_act_collapse_E30_513` | 37 | оседает без сил | E30_Bomb 513–549 |
| `Dobu_act_crouch_lunge_E27_381` | 20 | присед, выпад | E27_Badminton 381–400 |
| `Dobu_move_drop_down_land_E05_507` | 32 | падает сверху, вниз, приземление; с перемещением | E05_Mirror 507–538 |
| `Dobu_act_fall_back_E29_556` | 17 | падение, назад/спиной | E29_Door 556–572 |
| `Dobu_act_fall_curl_E38_275` | 14 | падение, сворачивается | E38_Rope_Climbing 275–288 |
| `Dobu_act_fall_down_get_up_E11_1019` | 28 | падение, вниз, вверх | E11_Platforms 1019–1046 |
| `Dobu_act_fall_forward_E15_186` | 120 | падение, вперёд | E15_GoodMorning 186–305 |
| `Dobu_move_fall_launch_away_E11_253` | 67 | падение, улетает, прочь; с перемещением | E11_Platforms 253–319 |
| `Dobu_move_fall_sit_E02_512` | 13 | падение, сидит; с перемещением | E02_Sphere 512–524 |
| `Dobu_act_fall_to_sit_E17_489` | 22 | падение → сидит | E17_Shell 489–510 |
| `Dobu_act_hang_kick_E38_541` | 31 | висит, пинок | E38_Rope_Climbing 541–571 |
| `Dobu_act_kick_land_E34_153` | 51 | пинок, приземление | E34_LostBudget 153–203 |
| `Dobu_move_knocked_back_fall_E34_45` | 28 | отброшен ударом, назад/спиной, падение; с перемещением | E34_LostBudget 45–72 |
| `Dobu_act_lean_back_stagger_E03_43` | 69 | наклон, назад/спиной, шатается | E03_Jenga 43–111 |
| `Dobu_act_lean_forward_fall_E05_290` | 44 | наклон, вперёд, падение | E05_Mirror 290–333 |
| `Dobu_act_lunge_hit_E27_241` | 16 | выпад, удар | E27_Badminton 241–256 |
| `Dobu_act_lunge_reach_E27_341` | 22 | выпад, тянется | E27_Badminton 341–362 |
| `Dobu_act_lying_flail_E06_226` | 15 | лёжа, размахивает руками | E06_Moon 226–240 |
| `Dobu_act_lying_roll_E06_1` | 69 | лёжа, перекат | E06_Moon 1–69 |
| `Dobu_act_lying_roll_over_E40_1384` | 67 | лёжа, перекат, через себя | E40_Debug_Platform 1384–1450 |
| `Dobu_act_overhead_swing_E27_586` | 29 | над головой, замах/раскачка | E27_Badminton 586–614 |
| `Dobu_move_roll_get_up_E02_17` | 91 | перекат, вверх; с перемещением | E02_Sphere 17–107 |
| `Dobu_act_roll_get_up_E29_572` | 41 | перекат, вверх | E29_Door 572–612 |
| `Dobu_jump_rubber_legs_swing_E40_1215` | 19 | резиновые, ноги, замах/раскачка | E40_Debug_Platform 1215–1233 |
| `Dobu_act_stumble_back_flail_E03_1` | 37 | спотыкается, назад/спиной, размахивает руками | E03_Jenga 1–37 |
| `Dobu_act_stumble_crawl_E27_413` | 79 | спотыкается, ползёт | E27_Badminton 413–491 |
| `Dobu_move_swing_hang_settle_E40_1156` | 11 | замах/раскачка, висит, успокаивается; с перемещением | E40_Debug_Platform 1156–1166 |
| `Dobu_act_swing_low_E27_285` | 25 | замах/раскачка, низко | E27_Badminton 285–309 |
| `Dobu_act_trip_fall_E02_143` | 54 | спотыкается, падение | E02_Sphere 143–196 |
| `Dobu_move_trip_fall_forward_E22_182` | 59 | спотыкается, падение, вперёд; с перемещением | E22_Trustfall 182–240 |
| `Dobu_move_tumble_E13_122` | 10 | кувырок; с перемещением | E13_LiminalRun 122–131 |
| `Dobu_move_tumble_E34_128` | 14 | кувырок; с перемещением | E34_LostBudget 128–141 |
| `Dobu_move_tumble_flat_spin_E40_1278` | 27 | кувырок, плашмя, вращение; с перемещением | E40_Debug_Platform 1278–1304 |
| `Dobu_act_tumble_get_up_E15_150` | 21 | кувырок, вверх | E15_GoodMorning 150–170 |
| `Dobu_move_tumble_spin_E02_306` | 19 | кувырок, вращение; с перемещением | E02_Sphere 306–324 |
| `Dobu_move_tumble_spin_E31_258` | 11 | кувырок, вращение; с перемещением | E31_LeftForever 258–268 |
| `Dobu_move_tumble_spin_land_E34_63` | 86 | кувырок, вращение, приземление; с перемещением | E34_LostBudget 63–148 |
| `Dobu_move_tumble_stand_E02_21` | 69 | кувырок, встаёт/стоит; с перемещением | E02_Sphere 21–89 |

### Сидя, лёжа, ползком (38)
**Когда:** отдых, усталость, сон, после падения, игра на полу.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_act_belly_hands_E28_381` | 37 | на животе, руки | E28_Spoiled 381–417 |
| `Dobu_jump_belly_slide_E05_456` | 10 | на животе, скользит | E05_Mirror 456–465 |
| `Dobu_act_bend_forward_E11_152` | 26 | наклон, вперёд | E11_Platforms 152–177 |
| `Dobu_act_clasp_crouch_E22_80` | 38 | сцепил руки, присед | E22_Trustfall 80–117 |
| `Dobu_act_crawl_E05_472` | 15 | ползёт | E05_Mirror 472–486 |
| `Dobu_move_crawl_belly_E40_1179` | 10 | ползёт, на животе; с перемещением | E40_Debug_Platform 1179–1188 |
| `Dobu_move_crawl_close_E02_405` | 17 | ползёт, близко; с перемещением | E02_Sphere 405–421 |
| `Dobu_move_crawl_forward_E09_86` | 25 | ползёт, вперёд; с перемещением | E09_Liminal Space 86–110 |
| `Dobu_act_crouch_to_reach_E02_247` | 43 | присед → тянется | E02_Sphere 247–289 |
| `Dobu_act_crouch_to_stand_E40_360` | 12 | присед → встаёт/стоит | E40_Debug_Platform 360–371 |
| `Dobu_act_crouch_work_E32_237` | 98 | присед, работает руками | E32_Builder 237–334 |
| `Dobu_act_curl_into_ball_up_E38_459` | 62 | сворачивается, в, в комок, вверх | E38_Rope_Climbing 459–520 |
| `Dobu_move_grow_from_tiny_crouch_E21_358` | 56 | растёт, из, крошечный, присед; с перемещением | E21_ShortQueen 358–413 |
| `Dobu_jump_land_crouch_E38_464` | 60 | приземление, присед | E38_Rope_Climbing 464–523 |
| `Dobu_move_lie_slide_E32_473` | 50 | лечь, скользит; с перемещением | E32_Builder 473–522 |
| `Dobu_act_lie_to_sit_E23_120` | 60 | лечь → сидит | E23_Sleeper 120–179 |
| `Dobu_act_lying_sit_up_E06_118` | 14 | лёжа, сидит, вверх | E06_Moon 118–131 |
| `Dobu_act_lying_spread_out_E40_1336` | 10 | лёжа, раскинулся, в стороны | E40_Debug_Platform 1336–1345 |
| `Dobu_act_reach_then_crouch_E05_305` | 29 | тянется, затем, присед | E05_Mirror 305–333 |
| `Dobu_move_sit_get_up_E32_353` | 51 | сидит, вверх; с перемещением | E32_Builder 353–403 |
| `Dobu_act_sit_ground_get_up_E38_245` | 23 | сидит, на земле, вверх | E38_Rope_Climbing 245–267 |
| `Dobu_act_sit_ground_rock_E09_54` | 31 | сидит, на земле, покачивается | E09_Liminal Space 54–84 |
| `Dobu_act_sit_hands_head_E31_97` | 28 | сидит, руки, голова | E31_LeftForever 97–124 |
| `Dobu_act_sit_idle_E11_127` | 15 | сидит, айдл | E11_Platforms 127–141 |
| `Dobu_act_sit_lean_back_E23_7` | 21 | сидит, наклон, назад/спиной | E23_Sleeper 7–27 |
| `Dobu_act_sit_lie_back_E37_27` | 45 | сидит, лечь, назад/спиной | E37_FreeDay 27–71 |
| `Dobu_act_sit_lie_back_hands_head_E06_149` | 21 | сидит, лечь, назад/спиной, руки, голова | E06_Moon 149–169 |
| `Dobu_act_sit_reach_feet_E09_187` | 21 | сидит, тянется, к ступням | E09_Liminal Space 187–207 |
| `Dobu_act_sit_rock_E09_213` | 24 | сидит, покачивается | E09_Liminal Space 213–236 |
| `Dobu_move_sit_scoot_E32_438` | 36 | сидит, ёрзает; с перемещением | E32_Builder 438–473 |
| `Dobu_act_sit_to_lie_E23_6` | 39 | сидит → лечь | E23_Sleeper 6–44 |
| `Dobu_act_sit_to_stand_E31_56` | 36 | сидит → встаёт/стоит | E31_LeftForever 56–91 |
| `Dobu_move_slide_stand_E02_324` | 64 | скользит, встаёт/стоит; с перемещением | E02_Sphere 324–387 |
| `Dobu_move_squashed_flat_slide_E19_866` | 95 | сплющен, плашмя, скользит; с перемещением | E19_RacingVote 866–960 |
| `Dobu_act_squat_hands_E21_201` | 77 | на корточках, руки | E21_ShortQueen 201–277 |
| `Dobu_act_squat_hands_E21_346` | 28 | на корточках, руки | E21_ShortQueen 346–373 |
| `Dobu_act_stand_then_crouch_E02_125` | 56 | встаёт/стоит, затем, присед | E02_Sphere 125–180 |
| `Dobu_move_upside_down_slide_E19_867` | 65 | вверх ногами, вниз, скользит; с перемещением | E19_RacingVote 867–931 |

### Танец, йога, баланс (14)
**Когда:** праздник, тренировка, балансирование на краю.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_act_arms_out_balance_E17_286` | 53 | руки, в стороны, баланс | E17_Shell 286–338 |
| `Dobu_move_arms_out_balance_E37_757` | 141 | руки, в стороны, баланс; с перемещением | E37_FreeDay 757–897 |
| `Dobu_act_arms_out_wobble_E01_4` | 23 | руки, в стороны, покачивание | E01_Intro 4–26 |
| `Dobu_move_dance_arms_out_2_E37_299` | 138 | танец, руки, в стороны; с перемещением | E37_FreeDay 299–436 |
| `Dobu_move_dance_arms_out_E37_0` | 137 | танец, руки, в стороны; с перемещением | E37_FreeDay 0–136 |
| `Dobu_act_dance_moves_E28_257` | 86 | танец, движения | E28_Spoiled 257–342 |
| `Dobu_act_dance_point_up_E28_166` | 94 | танец, указывает, вверх | E28_Spoiled 166–259 |
| `Dobu_move_lean_back_balance_E40_1143` | 11 | наклон, назад/спиной, баланс; с перемещением | E40_Debug_Platform 1143–1153 |
| `Dobu_act_yoga_flow_E25_164` | 89 | йога, связка | E25_CrowdYoga 164–252 |
| `Dobu_act_yoga_plank_to_stand_E25_147` | 134 | йога, планка → встаёт/стоит | E25_CrowdYoga 147–280 |
| `Dobu_act_yoga_to_plank_E25_70` | 80 | йога → планка | E25_CrowdYoga 70–149 |
| `Dobu_act_yoga_to_plank_E25_72` | 64 | йога → планка | E25_CrowdYoga 72–135 |
| `Dobu_act_yoga_warrior_E25_1` | 72 | йога, воин (йога) | E25_CrowdYoga 1–72 |
| `Dobu_act_yoga_warrior_E25_1_2` | 39 | йога, воин (йога) | E25_CrowdYoga 1–39 |

### Жесты и реакции (разговор, эмоции) (35)
**Когда:** реплики Добу, реакции на ПЭМ, радость, недоумение, указание; лицо добавлять позами `Face_*`.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_act_arm_gesture_talk_E14_2` | 50 | рука, жест, говорит | E14_BluePrince 2–51 |
| `Dobu_act_arms_flap_E16_84` | 13 | руки, машет как крыльями | E16_Tamagochi 84–96 |
| `Dobu_act_arms_out_point_E22_96` | 22 | руки, в стороны, указывает | E22_Trustfall 96–117 |
| `Dobu_act_cheer_arms_up_E22_197` | 70 | радость, руки, вверх | E22_Trustfall 197–266 |
| `Dobu_act_finger_up_idea_E32_200` | 12 | палец, вверх, идея (палец вверх) | E32_Builder 200–211 |
| `Dobu_act_gesture_turn_away_E40_289` | 19 | жест, поворот, прочь | E40_Debug_Platform 289–307 |
| `Dobu_act_hands_head_raise_arm_E01_183` | 33 | руки, голова, поднимает, рука | E01_Intro 183–215 |
| `Dobu_act_hands_on_head_E09_113` | 27 | руки, на, голова | E09_Liminal Space 113–139 |
| `Dobu_act_head_touch_wave_E05_237` | 12 | голова, касается, машет | E05_Mirror 237–248 |
| `Dobu_act_hold_device_idle_E16_267` | 26 | держит, с предметом в руках, айдл | E16_Tamagochi 267–292 |
| `Dobu_act_hold_device_look_E16_257` | 35 | держит, с предметом в руках, смотрит | E16_Tamagochi 257–291 |
| `Dobu_act_hold_device_point_E16_276` | 17 | держит, с предметом в руках, указывает | E16_Tamagochi 276–292 |
| `Dobu_act_hold_device_step_E16_262` | 30 | держит, с предметом в руках, шаг | E16_Tamagochi 262–291 |
| `Dobu_act_hold_device_turn_E16_281` | 12 | держит, с предметом в руках, поворот | E16_Tamagochi 281–292 |
| `Dobu_act_land_arms_out_E40_232` | 30 | приземление, руки, в стороны | E40_Debug_Platform 232–261 |
| `Dobu_act_look_around_E16_306` | 65 | смотрит, кругом | E16_Tamagochi 306–370 |
| `Dobu_act_look_back_step_E40_378` | 23 | смотрит, назад/спиной, шаг | E40_Debug_Platform 378–400 |
| `Dobu_act_look_back_step_E40_416` | 27 | смотрит, назад/спиной, шаг | E40_Debug_Platform 416–442 |
| `Dobu_act_point_side_far_E32_436` | 17 | указывает, в сторону/боком, далеко | E32_Builder 436–452 |
| `Dobu_act_push_forward_E18_169` | 26 | толкает, вперёд | E18_ArnoldRoom 169–194 |
| `Dobu_act_reach_forward_E01_1` | 58 | тянется, вперёд | E01_Intro 1–58 |
| `Dobu_act_scratch_head_E05_200` | 24 | чешет, голова | E05_Mirror 200–223 |
| `Dobu_act_shrug_E22_13` | 29 | пожимает плечами | E22_Trustfall 13–41 |
| `Dobu_act_stretch_up_reach_E05_333` | 49 | тянется, вверх, тянется | E05_Mirror 333–381 |
| `Dobu_act_talk_gesture_turn_E03_214` | 66 | говорит, жест, поворот | E03_Jenga 214–279 |
| `Dobu_act_turn_around_E16_307` | 112 | поворот, кругом | E16_Tamagochi 307–418 |
| `Dobu_act_turn_around_idle_E40_48` | 33 | поворот, кругом, айдл | E40_Debug_Platform 48–80 |
| `Dobu_act_turn_shrug_E32_618` | 46 | поворот, пожимает плечами | E32_Builder 618–663 |
| `Dobu_act_wave_E20_131` | 70 | машет | E20_Runner 131–200 |
| `Dobu_act_wave_both_arms_E32_47` | 43 | машет, обеими, руки | E32_Builder 47–89 |
| `Dobu_move_wave_flop_E32_452` | 22 | машет, плюхается; с перемещением | E32_Builder 452–473 |
| `Dobu_act_wave_small_E21_46` | 37 | машет, маленький | E21_ShortQueen 46–82 |
| `Dobu_act_wave_step_E32_547` | 65 | машет, шаг | E32_Builder 547–611 |
| `Dobu_act_wave_turn_away_E31_270` | 129 | машет, поворот, прочь | E31_LeftForever 270–398 |
| `Dobu_act_wave_up_E32_522` | 19 | машет, вверх | E32_Builder 522–540 |

### Полёт, канат, лазание, мультяшные деформации (14)
**Когда:** шотовые трюки: полёт, подъём на канате, висение, сплющивание, рост из крошечного.

| Экшн | Кадров | Что происходит | Источник |
|---|---|---|---|
| `Dobu_jump_climb_pull_E38_184` | 11 | лазание, подтягивается | E38_Rope_Climbing 184–194 |
| `Dobu_jump_climb_pull_E38_225` | 11 | лазание, подтягивается | E38_Rope_Climbing 225–235 |
| `Dobu_jump_climb_pull_E38_245` | 21 | лазание, подтягивается | E38_Rope_Climbing 245–265 |
| `Dobu_move_climb_up_E38_194` | 22 | лазание, вверх; с перемещением | E38_Rope_Climbing 194–215 |
| `Dobu_move_fly_fast_across_E40_202` | 29 | полёт, быстро, поперёк кадра; с перемещением | E40_Debug_Platform 202–230 |
| `Dobu_move_fly_superman_E02_9` | 13 | полёт, как супермен; с перемещением | E02_Sphere 9–21 |
| `Dobu_act_fly_superman_E11_327` | 19 | полёт, как супермен | E11_Platforms 327–345 |
| `Dobu_move_rope_pulled_up_E38_282` | 82 | канат, тянут, вверх; с перемещением | E38_Rope_Climbing 282–363 |
| `Dobu_move_rope_zip_up_E38_324` | 14 | канат, резко едет, вверх; с перемещением | E38_Rope_Climbing 324–337 |
| `Dobu_move_spin_land_recover_E02_41` | 55 | вращение, приземление, восстанавливается; с перемещением | E02_Sphere 41–95 |
| `Dobu_move_squash_dive_E34_49` | 10 | сплющивание, нырок/бросок вперёд; с перемещением | E34_LostBudget 49–58 |
| `Dobu_act_squashed_flat_E19_958` | 46 | сплющен, плашмя | E19_RacingVote 958–1003 |
| `Dobu_act_squashed_flat_hold_E19_1001` | 112 | сплющен, плашмя, держит | E19_RacingVote 1001–1112 |
| `Dobu_move_swim_fly_flat_E40_1234` | 28 | плывёт, полёт, плашмя; с перемещением | E40_Debug_Platform 1234–1261 |


---

## ПЭМ — клипы (61)
Файл: `01_ASSETS\01_CHARACTERS\PA1M\01_RIG\PAM_AnimClips\PAM_AnimClips_v001.blend` (риг `Pa1m_rig_v4` линком), листы — `PAM_AnimClips\sheets\`. Имя: `PAM_<тип>_<движение>_<эпизод>_<кадр>`. Клипы начинаются с `c_pos`/`c_traj` = 0, `c_hand_ik.r` перенесён на `c_traj` (кроме E19 и E41).
Влёт/вылет ПЭМ в кадр берутся из эпизодов (каталог влётов в SKILL.md, напр. E40 716–746 справа налево, E40 866–886 вылет вправо, E33 ~7 с сверху слева) и подгоняются под камеру шота.

### Айдлы и лупы (3)
**Когда:** ПЭМ слушает/ждёт, фон под репликой Добу; парение = `float_idle`.

| Экшн | Кадров | Что происходит |
|---|---|---|
| `PAM_idle_breath_soft_E17_464` | 36 | тихий айдл, дыхание |
| `PAM_idle_fingers_idle_E41_1` | 32 | айдл пальцев |
| `PAM_idle_float_idle_E41_521` | 97 | айдл с покачиванием (парит) |

### Лупы (1)
**Когда:** повторяемый жест на реплике («нет-нет»).

| Экшн | Кадров | Что происходит |
|---|---|---|
| `PAM_loop_finger_wag_E27_273` | 28 | покачивание указательным («нет-нет»), цикл 28 кадров |

### Жесты (смена формы кисти) (29)
**Когда:** акценты реплики ПЭМ: счёт, указание, «стоп», хват, раскрытие ладони. Жест ставить на ударный слог.

| Экшн | Кадров | Что происходит |
|---|---|---|
| `PAM_gesture_rise_count3_E19_20` | 22 | поднимается и показывает три пальца |
| `PAM_gesture_count_3to2_E19_45` | 13 | счёт: три → два (V) |
| `PAM_gesture_count_2to1_E19_68` | 16 | счёт: два → один |
| `PAM_gesture_point_side_E19_95` | 15 | палец вверх → указывает в сторону |
| `PAM_gesture_open_to_fist_E19_1046` | 13 | раскрытая → кулак (хват) |
| `PAM_gesture_point_to_fist_E27_418` | 8 | указывает → кулак |
| `PAM_gesture_fist_thumb_point_E27_505` | 64 | кулак → большой палец → указательный вверх |
| `PAM_gesture_fist_to_point_E29_781` | 14 | кулак → указывает |
| `PAM_gesture_point_to_open_E29_796` | 16 | указывает → раскрывает ладонь |
| `PAM_gesture_fingers_settle_E30_1` | 34 | пальцы раскрываются и оседают |
| `PAM_gesture_fingers_small_E30_139` | 18 | мелкое движение пальцев |
| `PAM_gesture_open_to_relaxed_E30_181` | 23 | раскрытая → расслабленная |
| `PAM_gesture_thumb_out_E30_376` | 14 | отводит большой палец |
| `PAM_gesture_spread_E30_416` | 30 | растопыривает пальцы |
| `PAM_gesture_fist_bounce_E30_469` | 10 | кулак, короткий толчок |
| `PAM_gesture_fist_to_point_E30_487` | 13 | кулак → указывает |
| `PAM_gesture_two_fingers_small_E30_602` | 33 | два пальца, мелкое движение |
| `PAM_gesture_fist_to_open_E33_335` | 32 | кулак → раскрытая ладонь |
| `PAM_gesture_peace_thumb_E35_112` | 11 | V с движением большого пальца |
| `PAM_gesture_pinch_to_open_E35_350` | 19 | щепоть → раскрытая |
| `PAM_gesture_index_down_E36_240` | 16 | указательный вверх → сжать |
| `PAM_gesture_thumb_in_E36_423` | 24 | большой палец прячется |
| `PAM_gesture_dip_two_fingers_E36_651` | 28 | кивок и два пальца |
| `PAM_gesture_fist_tilt_E39_438` | 9 | кулак наклоняется |
| `PAM_gesture_open_wave_E40_472` | 20 | раскрывает и машет |
| `PAM_gesture_index_up_hold_E40_756` | 41 | указательный вверх, «внимание» |
| `PAM_gesture_index_to_open_E40_800` | 45 | указательный вверх → раскрыть |
| `PAM_gesture_open_wave2_E40_954` | 24 | раскрывает и машет |
| `PAM_gesture_spread_to_open_E41_619` | 9 | растопыренная → раскрытая |

### Длинные сыгранные куски (7)
**Когда:** целая реплика или монолог ПЭМ; резать на части под фразы.

| Экшн | Кадров | Что происходит |
|---|---|---|
| `PAM_acting_wave_fidget_E29_643` | 86 | машет, потом перебирает пальцами |
| `PAM_acting_fidget_E29_730` | 37 | перебирает пальцами |
| `PAM_acting_roll_to_fist_E33_236` | 93 | сворачивается в кулак с разворотом |
| `PAM_acting_long_gesture_E39_54` | 98 | длинный жест |
| `PAM_acting_long_idle_gesture_E40_659` | 84 | длинный айдл с жестом |
| `PAM_acting_long_travel_E40_1188` | 92 | длинный проход с жестами |
| `PAM_acting_fingers_count_E41_83` | 85 | перебирает пальцы |

### Повороты кисти (8)
**Когда:** смена ракурса кисти к камере, «встаёт», показывает ладонь.

| Экшн | Кадров | Что происходит |
|---|---|---|
| `PAM_turn_flip_to_side_E02_321` | 19 | переворот с ладони на ребро |
| `PAM_turn_stand_show_palm_E02_341` | 47 | встаёт и показывает ладонь |
| `PAM_turn_fist_open_stand_E17_337` | 56 | из кулака раскрывается и встаёт |
| `PAM_turn_turn_upright_E17_538` | 44 | поворот в вертикаль и оседание |
| `PAM_turn_rotate_open_E30_281` | 48 | поворот раскрытой кисти |
| `PAM_turn_fist_turn_E35_1` | 41 | кулак разворачивается |
| `PAM_turn_flip_to_V_E35_41` | 64 | переворот → V |
| `PAM_turn_lean_E35_129` | 9 | наклон кисти |

### Перемещения (13)
**Когда:** вход/уход и перемещение по кадру; шотовые — переделать путь под камеру.

| Экшн | Кадров | Что происходит |
|---|---|---|
| `PAM_move_finger_walk_E02_247` | 48 | идёт на пальцах |
| `PAM_move_jump_away_E02_299` | 21 | прыжок/перелёт (шотовое) |
| `PAM_move_hops_E17_396` | 48 | подпрыгивания на месте |
| `PAM_move_dash_short_E30_174` | 8 | короткий рывок в сторону |
| `PAM_move_travel_E30_249` | 33 | перемещение по кадру (шотовое) |
| `PAM_move_fist_to_point_away_E30_469` | 37 | кулак → указывает, уходит назад |
| `PAM_move_slide_side_E30_513` | 23 | скользит в сторону |
| `PAM_move_slide_back_E30_540` | 11 | небольшой сдвиг назад |
| `PAM_move_travel_gesture_E30_650` | 64 | перемещение с жестами (шотовое) |
| `PAM_move_travel_thumb_E31_291` | 68 | перемещение с большим пальцем (шотовое) |
| `PAM_move_point_travel_E40_563` | 17 | указывает и перемещается |
| `PAM_move_spread_away_E40_873` | 13 | растопыривает и уходит |
| `PAM_move_shift_E40_1003` | 37 | сдвиг кисти |


---

## ПЭМ — позы (112 ассетов)
Файл: `01_ASSETS\01_CHARACTERS\PA1M\01_RIG\PAM_PoseLibrary\PAM_PoseLibrary_v002.blend` — папка подключена как Asset Library `PAM_PoseLibrary` (в папке держать только этот .blend, иначе дубли). Каталоги в Asset Browser — по ракурсу: «Ладонь к камере», «Тыльная сторона», «Пальцами в камеру», «Со стороны запястья», «Профиль — большой палец», «Профиль — мизинец», «00 Игровые (PA1M_Poses)» (`PAM_GA_*` — позы из игры).
Имя: `PAM_<форма>_<ракурс>_<номер>`. **Ракурс** — какой стороной кисть смотрела в камеру в эпизоде, где поза снята: выбирай ракурс под свою камеру, тогда поза читается так же. Позы без `c_traj`/`c_pos` — ставятся на месте.
Как применять: выделить кости рига ПЭМ в Pose Mode → в Asset Browser/полке поз двойной клик (или Blend Pose с перетягиванием). Держать позу 7–10 кадров (минимум 5) с лёгким шевелением, переходы ease in/out.

| Форма | Смысл / когда | Ассеты (ракурс) |
|---|---|---|
| **Раскрытая, пальцы растопырены** (25) | приветствие, «вау», удивление, «стоп!», показать себя целиком, взрыв эмоций | ладонь к камере: `PAM_GA_open_spread_palm_01`, `PAM_open_spread_palm_01`, `PAM_open_spread_palm_02`, `PAM_open_spread_palm_03`, `PAM_open_spread_palm_04`; пальцами в камеру: `PAM_GA_open_spread_tips_01`, `PAM_open_spread_tips_01`, `PAM_open_spread_tips_02`, `PAM_open_spread_tips_03`, `PAM_open_spread_tips_04`; со стороны запястья: `PAM_open_spread_wrist_01`, `PAM_open_spread_wrist_02`, `PAM_open_spread_wrist_03`; профиль — большой палец: `PAM_open_spread_thumbside_01`, `PAM_open_spread_thumbside_02`, `PAM_open_spread_thumbside_03`, `PAM_open_spread_thumbside_04`, `PAM_open_spread_thumbside_05`, `PAM_open_spread_thumbside_06`, `PAM_open_spread_thumbside_07`, `PAM_open_spread_thumbside_08`, `PAM_open_spread_thumbside_09`, `PAM_open_spread_thumbside_10`, `PAM_open_spread_thumbside_11`; профиль — мизинец: `PAM_open_spread_pinkyside_01` |
| **Раскрытая ладонь, пальцы вместе** (34) | нейтральная базовая форма: объясняет, предлагает, «вот», «держи», плавные проходы | ладонь к камере: `PAM_open_palm_01`, `PAM_open_palm_02`, `PAM_open_palm_03`, `PAM_open_palm_05`, `PAM_open_palm_06`, `PAM_open_palm_07`, `PAM_open_palm_08`; тыльная сторона: `PAM_open_back_01`, `PAM_open_back_02`, `PAM_open_back_04`; пальцами в камеру: `PAM_GA_open_tips_01`, `PAM_open_tips_01`, `PAM_open_tips_02`, `PAM_open_tips_03`, `PAM_open_tips_04`, `PAM_open_tips_05`, `PAM_open_tips_06`, `PAM_open_tips_07`; со стороны запястья: `PAM_open_wrist_01`, `PAM_open_wrist_02`, `PAM_open_wrist_03`, `PAM_open_wrist_04`; профиль — большой палец: `PAM_open_thumbside_01`, `PAM_open_thumbside_02`, `PAM_open_thumbside_04`, `PAM_open_thumbside_05`, `PAM_open_thumbside_06`, `PAM_open_thumbside_07`, `PAM_open_thumbside_08`; профиль — мизинец: `PAM_open_pinkyside_01`, `PAM_open_pinkyside_02`, `PAM_open_pinkyside_04`, `PAM_open_pinkyside_05`, `PAM_open_pinkyside_06` |
| **Мягко раскрытая** (4) | спокойный разговор, расслабленность, переход между жестами | ладонь к камере: `PAM_soft_open_palm_01`, `PAM_soft_open_palm_02`, `PAM_soft_open_palm_03`; профиль — мизинец: `PAM_soft_open_pinkyside_01` |
| **Расслабленная, пальцы согнуты** (4) | айдл, усталость, парение без реплики | пальцами в камеру: `PAM_GA_relaxed_bent_tips_01`, `PAM_relaxed_bent_tips_01`; профиль — мизинец: `PAM_relaxed_bent_pinkyside_01`, `PAM_relaxed_bent_pinkyside_02` |
| **Кулак** (5) | решимость, угроза, хват/захват предмета или Добу, «соберись» | ладонь к камере: `PAM_GA_fist_palm_01`; пальцами в камеру: `PAM_fist_tips_01`; со стороны запястья: `PAM_fist_wrist_01`; профиль — большой палец: `PAM_fist_thumbside_01`, `PAM_fist_thumbside_02` |
| **Указательный палец** (15) | указать на объект/Добу, «внимание!», «вот это», поднятый палец — идея/правило | ладонь к камере: `PAM_GA_point_palm_01`, `PAM_point_palm_01`, `PAM_point_palm_02`, `PAM_point_palm_03`, `PAM_point_palm_04`; тыльная сторона: `PAM_GA_point_back_01`, `PAM_GA_point_back_02`, `PAM_point_back_01`, `PAM_point_back_02`; пальцами в камеру: `PAM_point_tips_01`, `PAM_point_tips_02`; со стороны запястья: `PAM_point_wrist_01`, `PAM_point_wrist_02`; профиль — большой палец: `PAM_point_thumbside_01`, `PAM_point_thumbside_02` |
| **Два пальца (V)** (8) | счёт «два», «мир/победа», «идти пальцами» | ладонь к камере: `PAM_two_fingers_palm_01`, `PAM_two_fingers_palm_02`, `PAM_two_fingers_palm_03`; тыльная сторона: `PAM_two_fingers_back_01`, `PAM_two_fingers_back_02`, `PAM_two_fingers_back_03`; профиль — большой палец: `PAM_two_fingers_thumbside_01`; профиль — мизинец: `PAM_two_fingers_pinkyside_01` |
| **Большой палец отведён** (4) | «класс», одобрение, «вон там» большим пальцем | ладонь к камере: `PAM_thumb_out_palm_01`; тыльная сторона: `PAM_thumb_out_back_01`; пальцами в камеру: `PAM_GA_thumb_out_tips_01`, `PAM_thumb_out_tips_01` |
| **OK (кольцо)** (4) | «отлично», «всё в порядке», согласие | ладонь к камере: `PAM_ok_palm_01`; пальцами в камеру: `PAM_ok_tips_01`; профиль — большой палец: `PAM_ok_thumbside_01`; профиль — мизинец: `PAM_GA_ok_pinkyside_01` |
| **Щепоть** (1) | взять маленький предмет/Добу двумя пальцами, точность | ладонь к камере: `PAM_pinch_palm_01` |
| **Коза (рожки)** (2) | шутка, «рок», дурачество | ладонь к камере: `PAM_horns_palm_01`; профиль — мизинец: `PAM_horns_pinkyside_01` |
| **Смешанная (пальцы по-разному)** (6) | промежуточная/характерная форма, перебирание пальцами, счёт | ладонь к камере: `PAM_mixed_palm_01`, `PAM_mixed_palm_02`, `PAM_mixed_palm_03`, `PAM_mixed_palm_04`; со стороны запястья: `PAM_mixed_wrist_01`; профиль — большой палец: `PAM_mixed_thumbside_01` |


---

## Лицо Добу — 45 ассетов `Face_*`
Файл-библиотека: `01_ASSETS\01_CHARACTERS\DOBU\01_RIG\Dobu_FacePoses\Dobu_FacePoses_v12_5.blend` (риг `..\Dobu_Rig_v12_5_FaceAnim.blend` линком). Те же ассеты есть в самом риге v12_5. Правка поз — только в этом файле.
Как применять: в шоте выделить кости лица (или `cc_fc_root.x`) → ассет с полки поз. Анимации-ассеты дают последовательность, позы — одну форму. Доводить зрачками (`cc_fc_pupil.l/.r`) и мастерами; ключи только на контролах лица. Зеркальный вариант — кнопка «Mirror Face» (аддон `dobu_face_mirror`, активная кость `cc_fc_root.x`), встроенный Paste X-Flipped ломает лицо. Лицо меняется на акцентах реплики/реакции, между ними — моргания.
Типовой выбор: радость — 211/205/smile; хитрость — 209/wink; сомнение, side eye — 207/210; вина — 213 + взгляд в пол; страх — 215/206/214; злость — 203/annoyed/noise; после удара — dizzy; грусть — sad/cry; скука, сон — 204/sleepy.

| Ассет | Тип | Эмоция и когда использовать |
|---|---|---|
| `Face_blink` | анимация | моргание (1–25 кадров). Ставить каждые 2–4 с, на смене взгляда и после акцента |
| `Face_blink_2` | анимация | вариант моргания (girl_blink, 1–30) — для девочки |
| `Face_smile` | анимация | появление улыбки (1–30): приятно, понравилось |
| `Face_wink` | анимация | подмигивание (1–45): хитрость, «я знаю», шутка |
| `Face_annoyed` | анимация | раздражение (1–75): «ну опять», недовольство ПЭМ |
| `Face_sad` | анимация | грусть (1–65): неудача, расстроился |
| `Face_cry` | анимация | плач со слезой (1–95): сильная обида/горе; кадр 22 = поза плача |
| `Face_dizzy` | анимация | головокружение (1–105): после падения, удара, вращения |
| `Face_noise` | анимация | каракули/«шум» (1–95): злость, замешательство, перегрузка |
| `Face_sleepy` | анимация | засыпает (1–85): скука, усталость, ночь |
| `Face_curious` | поза | любопытство (= cry кадр 5): заметил что-то, «а что это?» |
| `Face_202_calm_closed_smile` | поза | спокойная улыбка с закрытыми глазами: умиротворение, доволен |
| `Face_203_angry_glare` | поза | злой взгляд исподлобья: угроза, возмущение |
| `Face_204_bored` | поза | скука: ждёт, неинтересно |
| `Face_205_big_grin` | поза | широкая улыбка: восторг, победа |
| `Face_206_surprised_oh` | поза | удивление «о!»: неожиданность, испуг слабый |
| `Face_207_skeptical` | поза | скепсис, side eye: не верит, подозревает |
| `Face_208_content_closed` | поза | довольный, глаза закрыты: наслаждается |
| `Face_209_smug` | поза | самодовольный: хитрость, «я же говорил» |
| `Face_210_unimpressed` | поза | не впечатлён: «и что?», сарказм |
| `Face_211_happy_smile` | поза | счастливая улыбка: радость, приветствие |
| `Face_212_cute_smile` | поза | милая улыбка: умиление, просьба |
| `Face_213_worried` | поза | тревога: виноват, сомневается |
| `Face_214_worried_more` | поза | сильная тревога: страшно, вот-вот случится плохое |
| `Face_215_scared` | поза | испуг: опасность, падение, крик |
| `Face_216_angry` | поза (девочка) | злость |
| `Face_219_blush` | поза (девочка) | смущение с румянцем |
| `Face_220_blush_happy` | поза (девочка) | смущённая радость |
| `Face_221_blush_smile` | поза (девочка) | смущённая улыбка |
| `Face_223_closed_eyes` | поза (девочка) | глаза закрыты |
| `Face_224_neutral` | поза (девочка) | нейтральное лицо, база |
| `Face_225_teary` | поза (девочка) | слёзы на глазах |
| `Face_226_bored` | поза (девочка) | скука |
| `Face_227_surprised` | поза (девочка) | удивление |
| `Face_228_happy_closed` | поза (девочка) | радость, глаза закрыты |
| `Face_229_laugh` | поза (девочка) | смех |
| `Face_230_heart_eyes` | поза (девочка) | глаза-сердечки: влюблённость, восторг |
| `Face_231_calm` | поза (девочка) | спокойствие |
| `Face_234_sad` | поза (девочка) | грусть |
| `Face_235_sleep` | поза (девочка) | спит |
| `Face_236_curious` | поза (девочка) | любопытство |
| `Face_237_sleepy` | поза (девочка) | сонная |
| `Face_238_wink_tongue` | поза (девочка) | подмигивает с языком: дурачится |
| `Face_239_happy` | поза (девочка) | радость |
| `Face_240_wink` | поза (девочка) | подмигивание |
