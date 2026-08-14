# Changelog

## 1.0 Release

### Added
- Compass style (S.T.A.L.K.E.R. 2 / classic) is switchable in MCM — no separate install option.
- Marker icons (custom / vanilla) are switchable in MCM — no separate install option.
- Compass scale slider, with ultrawide monitor support.
- Drop shadows on the compass and markers. The marker shadow can be turned off in MCM.
- Full compatibility with DX8 / DX9 renderers.

### Fixed
- "Always display" for a marker category also forced the distance readout on, ignoring that
  category's own checkbox.
- Markers were positioned for the S2 compass width even on the classic style, and the classic
  compass itself sat a few pixels off centre.
- Distance numbers wrapped onto two lines at 100 and above.
- Markers could break or disappear after changing level.
- Marker UI elements piled up over a long session instead of being released.
- The addon overwrote a shared engine value used by other scripts.

### Performance
- The compass and markers no longer query MCM or allocate memory every frame.
- Nothing is computed while the HUD is hidden (inventory, PDA, hidden HUD).
- Level load: the map spot scan is faster on first visit and skipped entirely on return.

### Compatibility
- The addon no longer replaces `axr_main.script` and `bind_stalker.script`. It will not
  conflict with other mods touching those files, and it survives Anomaly updates.

> **Updating:** delete the previous version completely before installing this one. Script
> files were renamed; leftovers from the old version will run alongside the new ones.

## v4-rc
- Fixed `ui_markers` / `ui_compass` file name mismatch.

## v3-rc
- Fixed vanilla medic icon display.

## v2-rc
- Added blue stash icon.

## v1-rc
- New compass texture (thanks EZ4E99) and new marker texture (thanks Rier).
- Fully reworked and optimised marker display system.
- New MCM options: display range per marker type, always visible, and distance to target text.
- Reworked alpha calculation for markers.
- Distance to target is shown only when the marker is centred.

## v0.3-pre
- New marker types: unique NPCs, sleeping spots, level transitions, stashes, NPC squads,
  campfires, water pumps, corpses and unknown enemies.
- Fixed performance issues (thanks xcvb, RavenAscendant, morrazzzz).
- Distance to target for quest markers, and marker transparency based on distance.
- Fixed diagonal marker positioning (thanks _V_O_IN_ and his friend) and marker displacement
  at very close range.
- MCM options for marker display range.
- Option to switch the compass to the mini-map (RavenAscendant's code).
- Removed Dynahud support.

Later fixes in this line: `v0.31-pre` quest markers, `v0.32-pre` disable-HUD crash,
`v0.33-pre` `distance_threshold` crash.

## Earlier beta versions
`v0.12` – `v0.16`: initial marker position maths, interpolation, English MCM translation
(thanks guns_bel), task-type marker icons, Dynahud support, MCM compass position option.