# droidtop-theme-patches

Real ES-DE themes have no artwork or metadata for [droidtop](https://github.com/bi0shacker001/droidtop)'s
own invented "systems" -- the game-engine categories (Ren'Py, RPG Maker
MV/MZ/VX Ace, KiriKiri) droidtop detects and groups games by that aren't
part of real ES-DE's own system list, since they're not consoles.

This repo is a base for real per-system theme overlay fragments for
exactly those invented systems, in the same real per-system metadata
format ES-DE themes themselves use (`system/metadata/<id>.xml`, a
`<theme>`/`<variables>` block -- confirmed against the per-system
metadata files bundled with the decaffe-es-de theme).

**This repo intentionally starts with no filled-in content.** [systems.json](systems.json)
lists the real system ids that need a patch (droidtop's own
`${system.theme}`-style identifiers, from
`library-core/src/main/kotlin/dev/droidtop/library/EsDeArtwork.kt`).
[system/metadata/TEMPLATE.xml](system/metadata/TEMPLATE.xml) shows the
real field format to fill in. Contributions should use real, sourced
information (verifiable facts about the engine, real accent colors from
its own real branding, etc.) -- not invented/placeholder values.

droidtop clones this repo once (alongside whichever real ES-DE theme is
active) and layers any filled-in fragments in as an overlay AFTER
loading any theme -- bundled or downloaded -- so every theme droidtop
can load gets support for these systems, without forking or patching
the theme itself.

## Content

- `systems.json` -- the real system ids that need a patch.
- `system/metadata/TEMPLATE.xml` -- the real per-system metadata field
  format to copy from when adding `system/metadata/<id>.xml`.

Logo/box-art assets for these engines aren't covered yet either --
that's separate, real per-engine artwork work.
