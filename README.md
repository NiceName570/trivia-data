# trivia-data

Public fact data for Cursor Lens AI. The extension code lives in a separate private repo. This repo is only data.

## Layout

Each folder is one topic. `curated.json` is the source of truth for that topic. The `.txt` file is a flat fact file built from it, and `parts/` holds the raw research pieces it was assembled from.

| Folder | Topic in the database |
|---|---|
| `casino/sugarhouse/` | `casino` |
| `movies/horror-90s/`, `movies/horror-00s/` | `movies` |
| `sports/nfl/`, `sports/mlb-postseason/` | `sports` |

## Getting edits into the database

Edit a `curated.json` here and push. Then, from the CursorLensAI repo's `database/` folder, run:

```
npm run load:remote
```

That rebuilds the Cloudflare D1 search database from this folder.

Folder READMEs were written when this data lived in `CursorLensAI/data/`, so the paths they mention are the old ones.
