# Codebasics Motion Graphics

Claude Code x HyperFrames system that makes Codebasics case-study reels (9:16, 30 fps): research, visual thinking,
real-world-to-style conversion, storyboard, animation, captions, audio and render, in the Codebasics brand.

## Start here
0. Editors new to this: read [EDITORS_GUIDE.md](EDITORS_GUIDE.md) (the whole process point by point, with the real storyboard).
1. New PC: follow [SETUP_NEW_PC.md](SETUP_NEW_PC.md) (exact tool versions, models, Chrome).
2. Open the folder in Claude Code (`claude`). [CLAUDE.md](CLAUDE.md) tells Claude what to read first.
3. The look: [CURRENT_STYLE.md](CURRENT_STYLE.md) (latest rules, Codebasics values). Everyday commands: [START_HERE.md](START_HERE.md).

## What is where
| Path | What |
|---|---|
| `CURRENT_STYLE.md` | Latest style rules: colours, fonts, sizes, captions, layout, motion, audio, hook, end card |
| `brain/` | Full process docs (start at `brain/README_CODEBASICS.md`) |
| `claude-memory/` | Copy of the Claude memory (locked style + user feedback) |
| `PROJECT_LOG.md` | Every run, newest first |
| `theme/` | Brand tokens (`theme.json`; full set in `theme/github-repo-private/`) |
| `Codebasics Brand Guidelines/` | Official palette, fonts, logos |
| `engines/hyperframes/` | HyperFrames engine, kits, scripts (export, layout audit, theme) |
| `library/` | Reusable components, assets and the reference-style study |
| `Reference Motion graphics/` | The 9 style-reference reels |
| `projects/Ramayana/` | Newest full production (storyboard + animation v4) with its assets |
| `projects/jio-ipo/`, `projects/jio-free-bait/` | Earlier productions (code only; jio-ipo has the news-hook template) |
| `.claude/` | Slash commands (incl. `/new-case-study`), skills (`case-study-motion`, `motion-pipeline`), saved multi-agent workflows (research, styleframes, animation) |
| `scripts/setup-check.mjs` | `npm run setup:check`: checks tools, versions, models, Chrome, fonts |
| `tools/session-scripts/` | Helper scripts rescued from the working sessions (sourcing, cut-outs, clip cutting, news-voice cutting) |

## Check it works
```bash
npm install
npm run chrome
cd projects/Ramayana/graphics/storyboard && node shoot.mjs
```
This renders the 66 storyboard frames to `out/`. Verified on 2026-10-29: 64 of 66 are bit-identical to the original
renders and the other 2 differ only by invisible decode noise.

Not in the repo: final exports, render caches and the full source downloads. They're not needed for the same output;
see `projects/Ramayana/DELETED_MEDIA.md`.
