# dobu-skill

Скилл для Claude по проекту **Добу** (Dobu, Dobudob, ПЭМ/PA1M): файлы и риги, библиотека поз ПЭМ, лицо Добу, стиль роликов, нейминг, Blender 5.2, плейбласт, эпизоды. База знаний лежит в `skills/dobu/knowledge/`.

Репозиторий публичный. Версия не закреплена — пользователи получают последний коммит.

## Установка

### Приложение Claude (claude.ai / десктоп)
1. Customize → Plugins → Personal plugins → **+** → **Add marketplace** → **Add from a repository**.
2. Вставить `muhtarovshyngys-pixel/dobu-skill`.
3. Установить плагин **dobu**.

### Claude Code
```
/plugin marketplace add muhtarovshyngys-pixel/dobu-skill
/plugin install dobu@waken-dobu
```
Автообновление: `/plugin` → Marketplaces → `waken-dobu` → **Enable auto-update**.

## Структура
```
.claude-plugin/marketplace.json   каталог (маркетплейс waken-dobu)
.claude-plugin/plugin.json        плагин dobu
skills/dobu/SKILL.md
skills/dobu/knowledge/            01–05 блоки, episodes/, refs/
```
