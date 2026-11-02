# Motion Graphics & Autonomous Editing Pipeline

Stack: Claude Code x HyperFrames x Premiere Pro / After Effects. HyperFrames is the only engine.
Brand: Codebasics (user, 2026-10-09). Source: `Codebasics Brand Guidelines/` (Pantone palette, Saira + Kanit, logos).

## Read first, every session
1. `PROJECT_LOG.md`: current state, decisions, tool versions, open items.
2. `VISUAL_DIRECTION.md`: the look and feel (vibe, type, colours, motion, editing style).
3. `theme/theme.json`: ALL style values as tokens. Never hardcode them.
4. `HANDOFF.md`: the plan and what is still undecided.
5. `claude-memory/`: the locked style rules and user feedback (copy of the Claude memory; on a new PC/account, read all of it).
6. `brain/`: the full process (research, visual thinking, style, motion, QA, feedback history). Start at `brain/README_CODEBASICS.md`.
New PC: `SETUP_NEW_PC.md`.
User guide: `START_HERE.md`. Slash commands live in `.claude/commands/`.

## Visual direction summary
CURRENT DEFAULT for case-study reels = `CURRENT_STYLE.md` (latest, 2026-10-22): white-dominant #F8F9FB background with
about 5 full-blue beats, flat (no shadows), Kanit text, Poppins captions, real-world fonts inside objects, word-timed
text, measured centring. It overrides the older summary below where they differ. Change only what the user names.

Older summary (REFERENCE MODE, use only when the user asks for "the reference look"):
Editorial collage in the reference style (`Reference Motion graphics/`, see `library/references/white-mg/`), but in CODEBASICS COLOURS:
background = brand blue #307FE2, elements tinted to the brand palette (purple, slate, navy, lime, orange, green, pink; tokens in `theme/theme.json`).
Real companies keep their own logo (and logo colours); anything we create uses the brand colours. Fonts: Saira (headings) + Kanit (UI/body).
MUST follow `library/references/white-mg/RULES.md` + `STYLE_SPEC.md` (~70-80% of the reference style, never a copy).
Presenter: none by default; ask before adding one. Never use the reference host. Real premium assets only (`library/references/ASSET_SOURCES.md`).
Build with `engines/hyperframes/assets/mg-kit.js` + `mg-kit.css` + `mg-elements.js` (on-twos stepping, ghost-ink text, shot-in blur, whip, pops, designed elements). Export with `engines/hyperframes/scripts/export.mjs`.
NO EMOJIS in scenes (only the 3D heart is allowed): use designed elements, real icons (`scripts/get-icon.mjs`), real HTML UI.
Scene settings (place/environment/mood) are ILLUSTRATED in code (`assets/mg-scenes.js`), photos only as drawing reference, and in COLOUR behind B&W cutouts (public figures, or a presenter if one is added).
MEANING FIRST: every visual must convey what the line says; appeal is secondary.
For every line: REALISM CHECK first (if 0% scope, still choose the best visual for the line) (convert real places/objects into accurate illustrated elements), and pick a scene palette (floor gradient gold/green/red/blue/violet/purple/pink/teal) that fits, varied across scenes.
Graphics link `assets/theme.css` and use its variables (`--color-*`, `--font-*`); never hardcode brand values.

## Engine
HyperFrames only. Installed: `engines/hyperframes` (v0.8.141), commands in its README.
Start every HyperFrames task at the `/hyperframes` skill. New graphic: `node engines/hyperframes/scripts/new-graphic.mjs <project> [graphic]`.
Alpha for Premiere: `render --format mov` (ProRes 4444, verified).

## Brand & style
- Fonts and colours = Codebasics brand, stored in `theme/theme.json` (regenerate CSS: `node engines/hyperframes/scripts/theme-css.mjs`).
- Every component reads its values from the theme. Swapping the theme must restyle everything with no code changes.

## Workflow
1. Plan: analyse raw footage + reference, write an edit plan (timestamps, where graphics go, b-roll slots).
2. Graphics: build in HyperFrames.
   Render overlays WITH ALPHA so they sit on top of footage in Premiere.
3. Cuts/b-roll/captions: Whisper transcript + FFmpeg for silence and bad-take removal.
4. Premiere handoff: generate an FCP XML timeline (footage, cuts, b-roll, graphics on separate tracks), import into Premiere Pro.
5. After Effects only when layer/keyframe-level editing is needed.
Typical target: ~20 s of premium motion graphics inside a 60 s video, plus cuts and b-rolls.

## Reusable library
- `library/components/`: reusable animation components (text, charts, transitions, lower-thirds, overlays, 3d).
- `library/assets/`: fonts, logos, sounds, images.
- When I approve an animation, save it into the library as a reusable, theme-driven component and note it in `library/README.md`.
- Before building something new, check the library and reuse what fits.

## Stay current (mandatory)
Before any install, setup or new skill work, check the latest official docs/releases for
HyperFrames, Claude Code, Premiere Pro and After Effects. Adapt to new features and
breaking changes. Never rely on outdated knowledge. Label anything that is an estimate.

## Memory (mandatory)
At the end of EVERY run, update `PROJECT_LOG.md`: date, what was done, decisions, tool versions
installed, what changed, next steps. Keep it short and current.

## Rules
- Ask before installing system-wide software or deleting files.
- Keep answers short and simple unless asked for depth.
- Deliver usable outputs (renders, files, configs), not just explanations.
- Per-video work in `projects/<video-name>/` (copied from `projects/_template/`). Engines in `engines/`. Never edit `projects/_template/` for a real job.
