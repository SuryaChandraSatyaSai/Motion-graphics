# Handoff: where we are

## Now (2026-10-29)
- Style is SET and locked: `CURRENT_STYLE.md` (Codebasics case-study mode, latest 2026-10-22). Fonts and colours are
  decided (the "Still open" item 1 below is done).
- Newest full production: `projects/Ramayana` (storyboard approved, animation v4 delivered 2026-10-22). Earlier:
  `projects/jio-ipo` (hook template) and `projects/jio-free-bait` (code recovered, no media).
- Process knowledge: `brain/` (start at `brain/README_CODEBASICS.md`). Claude memory copy: `claude-memory/`.
- New PC: `SETUP_NEW_PC.md`. Brand-neutral copy for other companies: the private GitHub repo (see PROJECT_LOG 2026-10-27).
- Still open: Premiere handoff (FCP XML) untested; the OPEN items listed in `brain/04-style-system.md` section 6.

## History (2026-10-09 state, kept as a record)

## Decided
- General-purpose pipeline, not tied to any brand.
- Workflow: Claude Code plans -> HyperFrames graphics -> Premiere Pro edit (After Effects optional).
- HyperFrames is the only engine (`engines/hyperframes`, v0.8.141).
  Alpha export confirmed: `render --format mov` -> ProRes 4444 (yuva444p12le).
- One skill (`.claude/skills/motion-pipeline`) + one local library (`library/`), backed up with Git.
- All brand values live in `theme/theme.json` (placeholders for now).
- Presenter: none by default; ask before adding one.

## Still open
1. **Final fonts, typography, colours.** User will provide; then replace `theme/theme.json`.
2. **Premiere handoff method.** Plan: alpha overlays + FCP XML timeline. Needs testing.

## Verified setup commands (checked 2026-10-08, re-check before running)
Requirements: Node.js 22+ (HyperFrames needs 22+), FFmpeg, Git.

HyperFrames:
    npx hyperframes init hyperframes-test
    cd hyperframes-test
    npx hyperframes skills update     # or: npx skills add heygen-com/hyperframes --all
    npx hyperframes preview
    npx hyperframes render
    npx hyperframes render --format mov -o out.mov   # transparent ProRes 4444

## Estimates (not measured)
- 60 s video with ~20 s premium graphics: roughly 2-4 h first time, 1-2 h once the library exists.
- Disk: keep ~10 GB free for renders.

## Next step
Run `/new-graphic <name>` or `/new-edit <name>` and give the brief.
