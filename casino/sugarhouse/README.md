# Casino · SugarHouse Games

Created October 10, 2026 as the fourth bundled Cursor Lens preload, for the King Cash "Royal Court" trivia (10 multiple-choice questions about the casino games on the site).

## Contents and provenance

- **Lobby snapshot** (`catalog.json`): 1,705 games across 44 lobby categories from the public PlaySugarHouse PA lobby API, with each game's provider, platform and exclusive flag. Category order is the lobby's own ranking. Refresh with `node scripts/refresh-casino-catalog.mjs`, which replaces the snapshot only if every category downloads and validates.
- **Hand facts** (`curated.json`): provider brand names, Lion Link / Huff N Puff / Lightning Link series, live-casino games, terms, a short table-game section, checked examples. Each series cites source IDs.
- **Selection**: new, hot, featured, staff-pick, top-10 and exclusive games weigh most, then branded, sports and live games. Games are added by score until the reference reaches the target in `curated.json` (23,700 characters, under the 24,000 cap). Every game in EXCLUSIVES, LATEST_RELEASES, TOP_PLAYED_NEW_GAMES, FEATURED, STAFF_PICKS, TOP_10_SLOTS, LIONLINK, HUFFNPUFF, SPOOKY_NEW and EAGLES_GAMES is guaranteed present (a test enforces it).
- Output: 23,684 characters (~5,921 tokens), 762 of the 1,705 games, grouped by provider with tags (^ exclusive, + new, * featured/top 10, ~ hot).

## Maintenance

`node scripts/refresh-casino-catalog.mjs` then `node scripts/build-casino-sugarhouse.mjs` (`--check` fails on stale generated files; the test suite runs it). Edit `curated.json` for hand facts; never hand-edit `src/casino-sugarhouse.js` or the `.txt` export.

## Not verified (needs a person)

- Release date of **Lion Link Fortune Bat**. The lobby lists it first and exclusive, but no source with its date was found, so the "newest animal" is only established up to Horse (Aug 2026).
- The **Bacon Bros Building Company** series = Huff N Puff: from the captured answer key and the pig-construction theme, not an official statement.
- Real-world brand names for lobby codes WHITEHAT, DGC, DWG, ODDSWORKS, RS_DIGITAL, ATOSLOTLAB, ALCHEMYBET and similar. They are written as the lobby's own codes.
- Whether the quiz names providers by brand (SG, Everi, IGT seen in captures) exactly as written here.
- Table-game numbers and Evolution game details come from standard published rules, not from this site.
- The snapshot is the logged-out Pennsylvania lobby; a logged-in lobby can differ (My Games, bonus offers).
