# Tactical Compass

Компас для S.T.A.L.K.E.R. Anomaly в духе S.T.A.L.K.E.R. 2, PUBG и Squad, вместе с
системой маркеров, которая выводит на неё метки с карты КПК. Полностью настраивается через MCM.

[Страница на ModDB](https://www.moddb.com/members/explorerbee) ·
[Демонстрация работы мода](https://www.youtube.com/watch?v=boGvng0kotI) ·
[English version](README.md) ·
[История изменений](CHANGELOG.md)

## Возможности

- **Два стиля компаса** — в духе S.T.A.L.K.E.R. 2 и классический, переключаются в MCM в любой момент.
- **Два набора иконок** — авторские от Rier или ванильные иконки КПК, которые подхватывают
  установленные у вас моды на иконки.
- **Десять категорий маркеров**: цели заданий, уникальные NPC, места для сна, тайники,
  переходы между уровнями, отряды NPC, трупы, костры, колонки с водой и пины Personal
  Adjustable Waypoint.
- **Настройки для каждой категории** — включение, дистанция отображения и режим «показывать
  всегда» независимо от расстояния.
- **Подсветка отслеживаемого задания** — задание, выбранное в КПК, выделяется на компасе.
- **Настройка высоты прямо в игре** — двигаете компас и сразу видите результат.
- **Работает на начатом сохранении** — метки, поставленные до установки, тоже появляются.
- **Цвета тайников как в G.A.M.M.A.** — опцией в MCM.
- **Дистанция до цели**, показывается когда смотришь прямо на маркер.
- **Стрелки высоты** — маркер сообщает, находится цель выше или ниже вас.
- **Плавное угасание** — маркеры растворяются по мере удаления, а не исчезают рывком.
- **Тени** у компаса и маркеров, чтобы они читались на фоне светлого неба.

## Требования

Обязательно:

- [Mod Configuration Menu](https://www.moddb.com/mods/stalker-anomaly/addons/anomaly-mod-configuration-menu)

Опционально — каждый мод открывает соответствующий тип маркеров:

| Мод | Дополнительно |
| --- | --- |
| [Display Campfires on Map](https://www.moddb.com/mods/stalker-anomaly/addons/displaycampfiresonmap) от HarukaSai | костры |
| [Fillable Canteens 2.0](https://www.moddb.com/mods/stalker-anomaly/addons/fillable-canteens-20) от HarukaSai | колонки с водой |
| [Body Dots on Minimap](https://www.moddb.com/mods/stalker-anomaly/addons/bodydotsminimap-white-dots-but-blue) от RavenAscendant | трупы |
| [Milspec PDA](https://www.moddb.com/mods/stalker-anomaly/addons/milspec-pda-for-anomaly-151-152-and-gamma) от Catspaw | трупы |
| [Personal Adjustable Waypoint](https://www.moddb.com/mods/stalker-anomaly/addons/personal-adjustable-waypoint-for-anomaly-151-152-and-gamma) от Catspaw | пины игрока |
| AlphaLion's Reworked Stash Quest and Map Markers (входит в G.A.M.M.A.) | цвета тайников G.A.M.M.A. на ванильных иконках |
| [S.T.A.L.K.E.R. 2 Style HUD/UI](https://www.moddb.com/mods/stalker-anomaly/addons/stalker-2-style-ui) от EZ4E99 | сочетается со стилем компаса S2 |

Рекомендуются modded exes: с ними поиск меток, поставленных до установки, работает быстрее.
Без них он тоже работает.

Совместим с Wearable Devices.

## Установка

1. Установите требования.
2. Скачайте аддон.
3. В Mod Organizer 2 нажмите `Ctrl + M`, выберите архив и подтвердите. MO2 настоятельно рекомендуется.

## Обновление с прошлой версии

**Удалите предыдущую версию полностью перед установкой этой.** В релизной версии файлы скриптов были
переименованы, и остатки старой версии продолжат работать вместе с новой — вы получите два
компаса на экране одновременно. В MO2 это означает удалить старую запись мода, а не
устанавливать поверх.

## Настройка

Всё находится в MCM в разделе *Tactical Compass*:

- **Основные настройки** — стиль компаса и кнопка, открывающая настройку высоты прямо в игре.
- **Маркеры** — набор иконок, тень, подсветка отслеживаемого задания, цвета тайников
  G.A.M.M.A. и по четыре опции для каждой из десяти категорий: отображение, показ дистанции
  до цели, «отображать всегда» и дальность отображения.
- **Горячие клавиши** — клавиша переключения и режим нажатия (одиночное, двойное, удержание).

## Структура проекта

```
gamedata/
  configs/
    text/{eng,rus}/mcm_compass.xml   строки MCM
    ui/ui_compass*.xml               вёрстка компаса, оба стиля
    ui/ui_markers*.xml               вёрстка маркеров, оба набора иконок
    ui/textures_descr/               регионы атласов текстур
  scripts/
    tc_variables.script              константы вёрстки, пресеты стилей, настройки
    tc_defs.script                   таблицы соответствия меток и категорий
    tc_mcm.script                    схема MCM и кеш настроек
    tc_utils.script                  математика и получение мировых координат
    tc_markers.script                реестр маркеров
    tc_hud.script                    само окно HUD
    tc_position.script               панель настройки высоты в игре
    tc_binder.script                 подключение движкового колбэка в рантайме
  textures/ui/tactic_compass/
```

## Поддержка и предложения

- Страница на [ModDB](https://www.moddb.com/members/explorerbee)
- Discord: **@explorerbee**

## Благодарности

Реализация поведения компаса взята из модпака
[A.N.T.H.O.L.O.G.Y.](https://ap-pro.ru/forums/topic/4266-anomaly-anthology-12/).

Огромное спасибо **HypeR** и **Melinite** за оригинальный компас, а также HypeR и команде
A.N.T.H.O.L.O.G.Y. за разрешение использовать их наработки и нарисованный HypeR компас
постфактум.

- **VodoXleb**, **xcvb (bvcx)**, **RavenAscendant** — помощь со скриптами
- **morrazzzz** — нашёл колбэк `actor_map_location_added`, на котором построена система маркеров
- **EZ4E99** — текстура компаса (STALKER 2)
- **Rier** (RierSenpai) — авторские иконки маркеров ([DeviantArt](https://www.deviantart.com/riersenpai))