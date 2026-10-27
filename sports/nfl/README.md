# NFL · History + 2026

Created October 2, 2026 for the existing Cursor Lens Preloaded data dropdown.

## Contents and provenance

- All 60 Super Bowl results, MVPs, venues, season/game years; extracted from ESPN's results and MVP tables. Franchise totals and Super Bowl score landmarks are computed from that table, keeping early Baltimore Colts distinct from later Baltimore Ravens.
- All 32 teams/divisions and 45 sourced entries covering records, league history, famous games, and 2025 awards presented in February 2026.
- 2026 Weeks 1-4: 64 games, 49 FINAL and 15 PENDING at `2026-10-02T22:46:06.578Z`. Includes completed-game scores and ESPN's leading passer/rusher/receiver. Team records are recomputed from completed games.

`curated.json` retains every curated entry's source ID, historical verification date, and source URL list. `season-2026.json` preserves compact scoreboard data, original leader display values, game IDs, source URLs, and snapshot time. Generated `src/nfl-trivia.js` includes all 30 sources. `NFL History + 2026.txt` exports the identical reference for manual import.

Size: 23,705 characters, approximately 5,927 tokens, below the existing 24,000-character limit. Only the selected pack enters the prompt; capture-time web searching is unchanged.

## Maintenance

From the repository root, `node scripts/build-nfl-trivia.mjs` rebuilds offline from the saved sources. Edit `curated.json`, then rebuild; do not hand-edit generated JavaScript or text. `node scripts/build-nfl-trivia.mjs --refresh` explicitly fetches the 2026 Weeks 1-4 ESPN scoreboard endpoints. It checks season, week, game count, and Weeks 1-3 completion before generating. The reference must fit before generated artifacts or the saved season snapshot are replaced. More completed Week 4 games may require compaction before a future refresh; size failures preserve existing artifacts. Do not raise the limit without measuring latency.

Catalog version 2 adds the new pack once to older lists with room, including previously empty lists. Existing packs and active selection are preserved. Startup persists only the migrated pack list and catalog version. Later removal survives reload, and a full ten-pack list is never evicted. The text export permits manual import.

Reload the unpacked extension, reopen the panel, and choose **NFL · History + 2026** under **Preloaded data**. The Week 1-3 pack remains a separate option.

## Verification and retained research limitations

Automated checks cover pack size, export equality, source IDs, all 60 season/game-year pairs, pending-game safeguards, selected-only prompts, migration, removal, full saved lists, and migration persistence during panel initialization with mocked browser storage. Live extension-manager access was blocked by the browser URL security policy, which allows only HTTP/HTTPS. The user will reload. Live dropdown appearance, screenshot-answer accuracy, and the five-second latency target remain unverified for this larger pack.

- The 2021 NFL season-record article lists the older 22.5 sack record. The pack supersedes it with the NFL's January 4, 2026 Garrett report: 23 in the 2025 season. Historical record-setting teams are not treated as current roster assignments.
- Pro Football Reference's Super Bowl page was bot-blocked; ESPN's successfully read tables supplied the data. Attempted ESPN record routes with No leaders available were not used. Attempted NFL Honors summary and Hall of Fame perfect-season URLs returned 404; successfully read alternate sources support the included entries.
- NFL's season player-stat and standings pages appeared incomplete/older. Current player-season leader claims were omitted. The standings source supplies division membership only; completed scoreboard games supply current records.
- TinyFish's rendered ESPN scoreboard JSON had malformed escaping. The generator uses the structured ESPN API directly, matching the existing Week 1-3 generator's approach.
- Initial builds exceeded the limit at 28,563 and 25,473 characters. Compact team abbreviations and yardage/TD displays brought the reference under the limit. Attempt/reception-count prefixes remain in the saved source snapshot. Facts are not blindly truncated; pending games retain no final score or leader stats.

The prior Week 1-3 snapshot/generator and separate trivia simulator were not changed.
