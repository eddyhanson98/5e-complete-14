# 5e Complete — updated for Foundry VTT v14

This is the "5e Complete Compendium" module (originally by btbias, v0.3.3),
rebuilt to install and run on **Foundry VTT v13/v14** with the **D&D5e 5.x** system.

## What changed
- **Compendium packs converted from NeDB (`.db`) to LevelDB folders.** This is the
  real reason the old copy wouldn't load past Foundry v11 — Foundry dropped the old
  `.db` format after v11. Every pack is now a folder under `packs/`.
- **`module.json` updated:**
  - Core compatibility: minimum 13, verified 14 (no maximum, so it won't block future cores).
  - D&D5e system relationship: minimum 5.0.0, verified 5.3.3.
  - Pack entries: removed the obsolete `entity` field, dropped the `.db` from each
    path, and tagged every pack with `system: "dnd5e"`.
  - Module version bumped to 0.4.0.
- All content (spells, items, creatures, classes, etc.) preserved exactly as it was.

## How to install
1. Close Foundry (or at least the world).
2. Copy the whole `5e-complete` folder into your Foundry data folder under
   `Data/modules/` — so you end up with `Data/modules/5e-complete/module.json`.
   (In Foundry: Setup → "Configure" shows your Data Path. Windows default is usually
   `%localappdata%\FoundryVTT\Data\modules\`.)
3. If you already have an old `5e-complete` in there, delete it first.
4. Launch Foundry, open your world, enable "5e Complete Compendium" in
   Manage Modules, and reload.

## Heads-up on the content itself
Two things worth knowing before you lean on this in a session — flagged honestly
rather than glossed over:

- **The creature statblocks are mostly stubs — in the original.** Of 1,962 creatures,
  only 37 actually have full stats (HP, AC, abilities). The other ~1,925 have empty
  data blocks. That's how the module shipped ("a work in progress," per the author's
  README), not something the conversion changed. I didn't invent stats to fill them.
- **Spells/items are authored for the old D&D5e 2.x data model.** D&D5e 5.x runs its
  own migration when it imports old documents, and it handles most of it, but the jump
  is large (the whole "activities" rework happened in between). Expect that some items
  may need a manual look — especially anything with damage/save/attack automation.
  If a specific spell or item looks broken when you open it, that's where.

To pull content into your world, drag it from the compendium into your world (or
right-click the compendium → Import All). Foundry runs the migration at import time.
