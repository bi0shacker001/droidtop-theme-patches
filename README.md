# droidtop-theme-patches

Real ES-DE themes have no artwork or metadata for [droidtop](https://github.com/bi0shacker001/droidtop)'s
own invented "systems" -- the game-engine categories (Ren'Py, RPG Maker
MV/MZ/VX Ace, KiriKiri) droidtop detects and groups games by that aren't
part of real ES-DE's own system list, since they're not consoles.

This repo holds per-system theme overlay fragments for exactly those
invented systems, in the same real per-system metadata format ES-DE
themes themselves use (`system/metadata/<system id>.xml`, a `<theme>`
`<variables>` block: `systemName`/`systemDescription`/
`systemManufacturer`/`systemReleaseYear`/`systemReleaseDate`/
`systemHardwareType`/`systemColor`/etc. -- confirmed against the real
per-system metadata files bundled with the decaffe-es-de theme).

droidtop clones this repo once (alongside whichever real ES-DE theme is
active) and layers these fragments in as an overlay AFTER loading any
theme -- bundled or downloaded -- so every theme droidtop can load gets
real support for these systems, without forking or patching the theme
itself.

System ids match droidtop's own `${system.theme}`-style identifiers
(`library-core/src/main/kotlin/dev/droidtop/library/EsDeArtwork.kt`):
`renpy`, `rpgmaker_mv`, `rpgmaker_mz`, `rpgmaker_vxace`, `kirikiri`.

## Content

- `system/metadata/<id>.xml` -- per-system metadata (name, description,
  manufacturer, release year, accent colors), same real format ES-DE
  theme authors use for their own bundled console metadata.

Logo/box-art assets for these engines are intentionally not included yet
-- real per-engine artwork is separate, real design work, not attempted
here.
