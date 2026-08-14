# Tactical Compass

A compass for S.T.A.L.K.E.R. Anomaly in the spirit of S.T.A.L.K.E.R. 2, PUBG and
Squad, with a marker system that puts your PDA map spots right on it. Fully configurable
through MCM.

[ModDB page](https://www.moddb.com/members/explorerbee) ·
[Demonstration video](https://www.youtube.com/watch?v=boGvng0kotI) ·
[Русская версия](README.ru.md) ·
[Changelog](CHANGELOG.md)

## Features

- **Two compass styles** — S.T.A.L.K.E.R. 2 and the classic one, switchable in MCM at any time.
- **Two marker icon sets** — custom icons by Rier, or vanilla PDA icons that follow your own icon addons.
- **Nine marker categories**: quest targets, unique NPCs, sleeping spots, stashes, level
  transitions, NPC squads, corpses, campfires and water pumps.
- **Per-category settings** — enable or disable each type, set its display range, or make it
  always visible regardless of distance.
- **Distance to target**, shown when you look straight at a marker.
- **Elevation arrows** — a marker tells you whether the target is above or below you.
- **Distance fade** — markers fade out smoothly instead of popping in and out.
- **Drop shadows** so the compass and markers stay readable against a bright sky.
- **Scale slider**, including support for ultrawide monitors.

## Requirements

Mandatory:

- [Mod Configuration Menu](https://www.moddb.com/mods/stalker-anomaly/addons/anomaly-mod-configuration-menu)

Optional — each one unlocks the corresponding marker type:

| Addon | Adds |
| --- | --- |
| [Display Campfires on Map](https://www.moddb.com/mods/stalker-anomaly/addons/displaycampfiresonmap) by HarukaSai | campfires |
| [Fillable Canteens 2.0](https://www.moddb.com/mods/stalker-anomaly/addons/fillable-canteens-20) by HarukaSai | water pumps |
| [Body Dots on Minimap](https://www.moddb.com/mods/stalker-anomaly/addons/bodydotsminimap-white-dots-but-blue) by RavenAscendant | corpses |
| [Milspec PDA](https://www.moddb.com/mods/stalker-anomaly/addons/milspec-pda-for-anomaly-151-152-and-gamma) by Catspaw | corpses |
| [S.T.A.L.K.E.R. 2 Style HUD/UI](https://www.moddb.com/mods/stalker-anomaly/addons/stalker-2-style-ui) | pairs with the S2 compass style |

## Installation

1. Install the requirements.
2. Download this addon.
3. In Mod Organizer 2 press `Ctrl + M`, pick the archive and confirm. MO2 is strongly recommended.

## Updating from an older version

**Delete the previous version completely before installing this one.** The script files were
renamed in v5, and leftovers from the old version will keep running alongside the new ones —
you will end up with two compasses on screen at once. In MO2 that means removing the old mod
entry, not just overwriting it.

## Configuration

Everything lives in MCM under *Tactical Compass*:

- **Main settings** — compass style, position on screen (top or bottom), scale.
- **Markers** — icon set, drop shadow, and four options for each of the nine categories:
  display, display distance to target, always display, and display range.
- **Key binding** — the toggle key.

## Ultrawide monitors

The engine stretches the interface horizontally on anything wider than 16:9, which makes the
compass too wide. Set **Compass scale** to about `0.75` for 21:9 and `0.50` for 32:9. On
regular monitors the slider simply resizes the compass.

## Known issues

- The minimap reappears after changing screen resolution. This is an engine bug — it
  reproduces with the addon disabled.

## Project layout

```
gamedata/
  configs/
    text/{eng,rus}/mcm_compass.xml   MCM strings
    ui/ui_compass*.xml               compass layout, both styles
    ui/ui_markers*.xml               marker layout, both icon sets
    ui/textures_descr/               texture atlas regions
  scripts/
    tc_variables.script              layout constants, style presets, tuning
    tc_defs.script                   map spot to marker category tables
    tc_mcm.script                    MCM schema and cached settings
    tc_utils.script                  math and world-position helpers
    tc_markers.script                marker registry
    tc_hud.script                    the HUD window itself
    tc_binder.script                 engine callback wiring, applied at runtime
  textures/ui/tactic_compass/
```

The addon does not replace any vanilla script. `tc_binder.script` patches the actor binder at
runtime instead, so it will not conflict with other mods and survives Anomaly updates.

## Support and suggestions

- ModDB [page](https://www.moddb.com/members/explorerbee)
- Discord: **@explorerbee**

## Credits

The compass behaviour comes from the
[A.N.T.H.O.L.O.G.Y. modpack](https://ap-pro.ru/forums/topic/4266-anomaly-anthology-12/).

A huge thank you to **HypeR** and **Melinite** for the original compass, and to HypeR and the
A.N.T.H.O.L.O.G.Y. team for letting me use their design and HypeR's painted compass after the
fact.

- **VodoXleb**, **xcvb (bvcx)**, **RavenAscendant** — scripting help
- **morrazzzz** — found the `actor_map_location_added` callback the marker system is built on
- **EZ4E99** — compass texture
- **Rier** (RierSenpai) — custom marker icons ([DeviantArt](https://www.deviantart.com/riersenpai))