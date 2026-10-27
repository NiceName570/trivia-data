# Horror Movies · 1990s

Created October 4-5, 2026 as the third bundled Cursor Lens preload.

## Contents and provenance

- 158 horror and horror-adjacent films first released 1990-1999 (36 tier 1, 81 tier 2, 41 tier 3), researched from each film's English Wikipedia article. Every film and fact keeps its source IDs in `curated.json`.
- 23 curated facts: Oscars, box-office records, debuts/casting, behind the scenes, quotes, international horror.
- Size: 23,011 characters, approximately 5,753 tokens, below the 24,000-character cap.

Tier controls rendered detail so the pack fits: tier 1 gets director, writer, source work, setting, three cast members and villain; tier 2 gets director and one lead; tier 3 gets director only. Fields over their length cap are omitted, never truncated. `curated.json` retains fuller research (extra cast, notes, box office) for future use.

## Maintenance

Edit `curated.json`, then run `node scripts/build-horror-90s.mjs`. It is offline only. `--check` fails if `src/horror-90s.js` or `Horror Movies 1990s.txt` is stale; the test suite runs it. Do not hand-edit generated files.

## Verification limits

Research agents read sources directly, but the planned independent fact-check pass did not run (session limit), and the franchise/debut theme agent failed; debut facts come from the per-year agents. Treat this as unverified-by-second-pass data and correct `curated.json` as live testing finds errors. Six non-horror crowd favorites (Hocus Pocus, The Nightmare Before Christmas, The Crow, Blade, Seven, The Stand) were demoted from tier 1 to tier 2 to fit.
