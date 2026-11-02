# START HERE

## Every time
1. Open a terminal in this project folder
2. Run: `claude`
3. Type one of the commands below.

## Commands (type in Claude Code)
| Command | Use it when |
|---|---|
| `/setup` | First time only: checks/installs Node, FFmpeg, Git, HyperFrames. |
| `/new-case-study <name>` | Full Codebasics case-study reel from a VO + script: research, storyboard, your approval, animation, render (follows `CURRENT_STYLE.md`). |
| `/new-edit <name>` | New video to edit (cuts, b-roll, captions, graphics, Premiere timeline). |
| `/new-graphic <name>` | Just a motion graphic / animation, no full edit. |
| `/update-style` | You changed fonts, colours or visual direction. |
| `/save-to-library` | You liked a graphic and want to reuse it later. |
| `/status` | See where things stand and what is next. |

## Starting a new video (2 minutes)
1. Run `/new-edit my-video` → it creates `projects/my-video/`.
2. Drop files in:
   - `raw/` → your raw footage
   - `refs/` → reference videos or screenshots
   - `broll/` → any b-roll you have
3. Fill `projects/my-video/BRIEF.md` (or just tell Claude in chat).
4. Say "go". Claude plans first, shows you, then builds.

## Where things end up
- Graphics: `projects/<name>/graphics/`
- Premiere timeline: `projects/<name>/timeline.xml` → Premiere: File > Import
- Final renders: `projects/<name>/exports/`
