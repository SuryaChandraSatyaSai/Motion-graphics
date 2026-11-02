# Project Log
Update at the end of every run. Newest first.

## 2026-11-02 Editors guide
- Added `EDITORS_GUIDE.md` (linked from README): the whole process point by point for fellow editors, every step linked
  to the real file, with the 8 Ramayana storyboard sheets shown inline. All links checked against tracked files.

## 2026-10-29 Re-check: added what only the brand-neutral copy had
- Added, adapted to the Codebasics folder (real names: `--blue`/`.blue`/Kanit/Poppins, `projects/Ramayana`, Codebasics
  logo; no theme-swap machinery): `/new-case-study` command, `case-study-motion` skill, the 3 saved workflows in
  `.claude/workflows/` (parse-checked), `scripts/setup-check.mjs` (`npm run setup:check`, theme check adapted).
- Added `tools/session-scripts/` (first-productions archive + ORIGINAL film-case-study scripts; 32 downloaded web pages dropped: their names were too long for a Windows clone).
- `brain/README_CODEBASICS.md`: kit-variable and helper mapping. START_HERE, README, SETUP_NEW_PC updated.
- `projects/jio-ipo/scripts/make-hook-audio.mjs`: SFX library paths outside the repo now overridable (HOOK_RISER / HOOK_BED).
- Memory: new `codebasics-org-repo`; `claude-memory/` synced.

## 2026-10-29 Pushed to the Codebasics org repo (branded)
- https://github.com/codebasics-all/Codebasics-Motion-graphics (private, main, commit bebffb0 on top of the org's
  initial README commit). 1828 files, plain git (no LFS; largest file 27 MB). This folder is now that repo's working copy.
- Not committed (.gitignore): node_modules, .cache, render out/ folders, refs/data/*/url*.txt (expiring signed YouTube
  URLs with the downloader's IP).
- Fresh clone test: npm install + shoot.mjs: 66/66 frames bit-identical to the original, 32/32 animation moments identical.
- Next: commit + push after each run (`git add -A`, `git commit`, `git push`).

## 2026-10-29 Folder made up to date and portable for OneDrive (Codebasics branding kept)
- Cleanup 2.9 GB -> ~0.9 GB (user-approved): deleted exports v1-v4 + zip, the 4 full trailers in "Assets by me",
  storyboard out/ renders, refs/yt, refs/data/s3-src. List + re-download notes: projects/Ramayana/DELETED_MEDIA.md.
- Portable: 7 scripts no longer hardcode Chrome/puppeteer paths (engines/hyperframes/scripts/lib/chrome.mjs + root
  package.json with puppeteer-core 25.13.0). Added SETUP_NEW_PC.md.
- Latest-only docs: NEW `CURRENT_STYLE.md` = the newest rules (Ramayana 2026-10-22) in Codebasics values; CLAUDE.md,
  VISUAL_DIRECTION.md, HANDOFF.md, theme.json note and memory now point to it (older blue-background notes = reference mode).
- Added `brain/` (full process docs) + `brain/README_CODEBASICS.md`, `claude-memory/` (memory copy, + new
  case-study-style-latest), restored code of projects/jio-ipo and jio-free-bait (recovered from file history, no media).
- Private brand pack theme/github-repo-private/ made self-contained (fonts + logos + relative paths) for the GitHub repo.
- Verified after cleanup: 64/66 storyboard frames bit-identical (F06a logo decode noise, F25b noise), 32/32 animation
  moments identical. Second fresh-clone test of the GitHub repo: 23/23 setup, theme byte-identical, frames/animation match.

## 2026-10-27 Brand-neutral GitHub repo pushed
- Repo: https://github.com/sreevignesh5/Business-Case-Study-Motions-Graphics-and-visuals (private, branch main, single commit 10b7367).
- Contents: brain/ (19 process docs), memory/, CLAUDE.md + setup docs, engine (theme-css with alias fonts BrandDisplay/BrandCondensed/BrandText/BrandCaption, apply-theme, portable Chrome launcher, setup-check), library + 9 reference reels (Git LFS), Ramayana example (code only), earlier telecom productions recovered from Claude file-history, rescued session tools, 3 saved workflows.
- No client branding in the repo (leak scan 0 hits; pre-commit guard). Verified: with our theme restored, the example renders pixel-identical (66 styleframes, 352 animation moments; only tiny shade swaps max 18/255); the neutral example theme re-skins cleanly.
- Our brand theme for the new repo (private, never commit): theme/github-repo-private/theme.local.json -> copy to <repo>/theme/theme.local.json on this PC.
- History rewritten with user approval (force-push): the old README commit with the client email is gone. Unlogged older runs are written up in the repo's PROJECT_LOG.
- New-PC test (fresh clone from GitHub into an empty folder): npm install, setup-check 22/23 (only "theme not generated", expected), theme + example render: 66/66 frames OK, matches the original (same tiny accepted diffs), 48/48 animation moments match, new graphic passes hyperframes check, MP4 render 1080x1920 30 fps OK.
- Next: run SETUP_NEW_PC.md on the other computer; copy the private theme file there yourself (it is not in git).


## 2026-10-24 Skill-pack export (logged late)
- Built `exports/case-study-motion-reel.zip` (SKILL.md, README, chat.md summary, storyboard kit + scripts + briefs; no
  media/fonts). Deleted in the 2026-10-29 cleanup; the same content now lives in brain/ and the GitHub repo.

## 2026-10-22 Ramayana animation v1-v4 (logged late)
- Storyboard corrections applied globally before animating (user 03:34): NO shadows anywhere ("plain overlay"); each
  white/blue frame shows text OR captions; footage always captioned; MG frames centred; one caption per cut in the
  three-film montage; Oscars headline removed; bridge frame = 0.8 s trailer shot + 3D camera dive (stones drop one by
  one); audio re-cut (silences > 0.5 s, then 1.10x), visuals re-timed.
- Build: 8 section agents + 1 footage cutter, shared ANIM_BRIEF.md; 207 SFX cues. v1 exported 1080x1920 30 fps 122.8 s.
- v2 (09:08): centre + middle-align every MG frame (measure.mjs -> layout.json dy); captions drop below the graphic only
  where they overlap; price tags in the caption font (₹ subset); every phrase/headline line starts with a capital;
  movie footage never freezes (live frame sequences in shapes). Effort switched from ultracode to high.
- v3 (09:42): tight crowned close-up replaced by wide / full-figure shots.
- v4 (10:42): footage bar 300 -> 340 px; headline words invisible until spoken (ghost 0, no reflow).

## 2026-10-22 Ramayana storyboard delivered (projects/Ramayana)
- 44 frames / 65 styleframe panels, 2:02 runtime (VO 1.10x).
  - Board: graphics/storyboard/board/STORYBOARD.html + S1-S8.png sheets.
  - Text version: projects/Ramayana/STORYBOARD.md.
  - Regenerate: node graphics/storyboard/shoot.mjs, then node board.mjs.
- Kit upgrades:
  - ₹ glyph fixed (local Kanit/Poppins/Roboto subsets had no U+20B9; ₹-only faces via scripts/rupee-fonts.mjs).
  - Golden ticket v2 (foil, guilloche, punched holes, red serial).
  - Polar bend bar→pie (SB.bentBar); depth tokens.
- Build: one agent per section, with adversarial review → fix → review again.
  - S5 fixes were applied by hand after the session limit cut the agents off: Ramayana pins, Ranbir fade, debt weight hang, real month grid.
- Facts used on screen:
  - Ormax 83.2 Cr tickets; ₹161 avg ticket.
  - PFOCUS peak 2.09x on 22 Sep 2026 (₹357.45), ₹275.50 as of 21 Oct.
  - Ranbir 12.5 lakh @ ₹120 (filing); debt ₹5,062 Cr Mar 2026.
  - Sony outside India; Sacnilk booking est.
- Open for the user:
  - Script line "for one film" (₹4,000 Cr covers both parts).
  - Inception/Interstellar shots come from third-party 4K uploads.
  - refs/data/kalki-2160/url.txt holds an expiring signed YouTube URL (safe to delete, ask first).
- Later the same day: the resumed workflow ran one more review/fix round on all sections (06:36-07:44), so the board was rebuilt and re-sent. F18b seam fixed by hand. The F42 LA card now flips to real Hollywood Sign footage (trademark caution noted). F24 adds an illustrative Tokyo arc.
- Next: on approval, build the HyperFrames animation from the styleframes (graphics/story).

## 2026-10-21 Ramayana case study: storyboard in progress (projects/Ramayana)
- VO: whisper transcript matches the script; silences trimmed (raw/vo-trim.wav 134.3 s), 1.10x (raw/vo-110.wav, 122.1 s). Word clock in graphics/story/assets/words.js (DNEG, Dussehra, Codebasics spellings fixed).
- Research workflow done:
  - Shot catalogues of all 4 trailers (refs/catalog).
  - Fact-check (refs/facts.json). Avg ticket ₹161; Prime Focus peaked at 2.09x (Sep 2026), now +61%; Ranbir 12.5 lakh shares @ ₹120; debt ₹5,062 Cr (Mar 2026); Sony distributes outside India only; Ram Setu must be illustrated.
  - Logos, photos, clips and design spec are in graphics/story/assets + refs.
- The user's "Rise of a Legend" asset is truncated (11.6 s of picture). The full T-Series upload is in refs/yt/ram-rise/.
- Storyboard system in graphics/storyboard:
  - frames.mjs: 44 frames / 64 panels with auto captions per the v13 spec.
  - kit/: image bars, poster pie, golden ticket, price tag.
  - shoot.mjs: render + safe-box audit.
  - BRIEF.md: rules for the section builders.
  - scripts/still.mjs: 9:16 trailer stills.
- S1 (F01-F07) is drafted. Next: S2-S8 styleframes (workflow, one agent per section + adversarial review), alignment check x2, then the storyboard board (HTML + PNG sheets + STORYBOARD.md) for approval.

## 2026-10-15 Jio IPO case study v13: new caption spec (from Surya Chandra)
- All captions (hook + main) now follow the spec:
  - Poppins Medium 44px/1.2, -0.005em, white, no shadow, one line per phrase (balanced splits).
  - Black box: padding 8/22/10, radius 4, box top fixed at y 1200, centred.
  - In: the phrase all at once (fade 0.1s, scale 0.92→1 and rise 8px over 0.18s, back.out). Out: 0.06s fade before the next phrase.
- The hook's bold key words were dropped (the spec is Medium only). Font file: Poppins-500.woff2 (@fontsource 5.2.7).
- Backups: `refs/index-v9.html`, `refs/hook-v4.html`. Export: `exports/jio-ipo-casestudy-v13.mp4` (= hook-v7 + main-v13).

## 2026-10-14 (e) Jio IPO case study v12
- The user found v11's repeat-echo too loud and asked for "the last version, a bit higher". Removed the echo layer; v10's hall reverb is now at -2 dB (was -5 dB), so the tail runs ~2-3 dB louder than v10.
- Export: `exports/jio-ipo-casestudy-v12.mp4` (= hook-v6 + main-v9). Hook-audio level reference: wet hall -2 dB.

## 2026-10-14 (d) Jio IPO case study v11
- Hook ending: bigger echo on "book":
  - Distinct repeats every 230 ms (aecho 230/460/690/920 ms, decays .5/.34/.22/.13), plus a slightly fuller hall tail.
  - Momentary level about -15 to -25 LUFS in the black, below the voice; it fades out before the main VO.
- Script: `scripts/make-hook-audio.mjs` (previous version at `refs/make-hook-audio-v2.mjs`).
- Export: `exports/jio-ipo-casestudy-v11.mp4` (= hook-v5 + main-v9, 117.5 s, -14.4 LUFS).

## 2026-10-14 (c) Jio IPO case study v10: FINAL (user: "we are good to go")
- Hook cut moved onto the word "book" (11.47 s; was 11.74). All clips and text cut to black there, and the hall reverb rings out over ~1.07 s of black before "Think about this". The last caption holds until the cut.
- Export: `exports/jio-ipo-casestudy-v10.mp4` (= hook-v4 + main-v9, 117.5 s, 1080x1920, 30 fps, -14.4 LUFS). The hook-v3 composition is backed up at `refs/hook-v3.html`.
- Open: delete raw downloads in `refs/hook-src`, `refs/v8-src`, `refs/v9-src` (~4.5 GB+) when the user confirms. Update CLAUDE.md, theme and template to the new white-dominant / Kanit / TikTok Sans system.

## 2026-10-14 (b) Jio IPO case study v9
- Captions: the black box is built per word, so each word brings its own piece of box (no empty bar ahead of the words).
- The PUBG trailer shot is replaced by real people playing PUBG on phones (The Quint, 2020 PUBG-ban B-roll, B&W vintage): `c28b-people-pubg.mp4`.
- Retimed so the Facebook & Google scene is on screen when "Facebook" is said:
  - F27 news ends at 72.85.
  - F28 photo 72.85-73.5 ("And you got free").
  - F28b PUBG people 73.5-74.1 ("internet.").
  - F29 from 74.1.
- Export: `exports/jio-ipo-casestudy-v9.mp4` (= hook-v3 + main-v9).

## 2026-10-14 Jio IPO case study v8 (user feedback list)
- **Hook:**
  - Captions are TikTok Sans 500 (key words 700), white on a black box, with no shadows.
  - The 4-8 s phrases moved down to y 1300.
  - Phrases hand off on the same frame (no overlap).
  - Riser removed; a great-hall echo tail on "in the book" (aecho, wet under dry) rings into the 0.8 s black.
- **Main look:**
  - White-dominant background (#F8F9FB).
  - Kanit black-grey text animations, no text shadows.
  - Captions are TikTok Sans 500, white on a black box.
  - Cast-shadow parallelograms removed; soft neutral blur shadows only.
- **Real-world fonts in visuals:** DSEG7 calculator, VT323 feature phone, JioType (local) / Nunito Sans for the Jio screens, Roboto for WhatsApp and stocks, Arial for documents and calendar, Courier New receipt, Permanent Marker price tags, Arial Black stamps, Unifraktur + Georgia/Times newspapers. Fonts are in `graphics/story/assets/fonts` (@fontsource 5.3, dseg 0.46).
- **Fixes:**
  - Airtel shot is now a real 4K Airtel Center B-roll clip (c11-airtel.mp4).
  - Tower signal rings no longer clipped.
  - Zuckerberg and Pichai cutouts uncropped (contain).
  - Newspaper uses the real Ambani WEF 2017 photo.
  - New F28b: PUBG Mobile trailer drop shot, B&W vintage, 73.95-74.75 s.
  - Pie slices stay inside the circle.
  - "50 crore" highlighted.
  - 25% badge is neutral dark.
  - Underline sits below "win the price war".
  - End card is clean white, no sparkles.
  - Masthead on one line, receipt fits, COST fits, post-blue frames return to white.
- Backups: `refs/index-v5.html`, `refs/hook-v2.html`, `refs/real-kit-v7.js`, `refs/beats-v7.json`, `refs/make-hook-audio-v1.mjs`.
- Export: `exports/jio-ipo-casestudy-v8.mp4` (= hook-v3 + main-v8).

## 2026-10-13 (i) Jio IPO case study v7: hook text per user
- Hook text now shows only the spoken words:
  - 2-4 word centred phrases in white Saira 500 with key words in 800 (fonts added: Saira 500/600, Kanit 500, from @fontsource 5.2.5).
  - Each phrase pops in 0.1 s early.
  - Removed every big context line.
- Context = small red label in the top-left corner with the year (e.g. "2016 · Jio launch", "Aug 2026 · SEBI approval").
- Export: `exports/hook-v2.mp4`; `exports/jio-ipo-casestudy-v7.mp4` (117.5 s, -14.3 LUFS). The previous hook is backed up at `refs/hook-v1.html`.

## 2026-10-13 (h) Jio IPO case study v6: news hook
- The user's reference: Downloads/jio-free-bait-master.mp4, a ~10 s news voice over B&W and colour clips, then ~1 s of black.
- Built `graphics/hook/` (12.54 s):
  - **Voices:** real news and AGM soundbites (`assets/news/`, sources in `news.json`):
    - Mukesh 2016: "The era of paying for voice calls is ending."
    - CNBC-TV18: "Vodafone and Idea had to merge to survive."
    - CNBC-TV18: "SEBI has waved the green flag."
    - Republic: "Jio is coming to crush every record in the book."
  - **Clips:** 10 real clips (`assets/raw/` + `broll.json`). 7 are graded B&W vintage and 3 old-news colour with scanlines (`scripts/grade-hook.mjs`). The news frames are letterboxed like an old TV.
  - **Text:** big white hook text kept off faces; white word-timed captions of the real speech.
  - **Audio:** the user's riser (creatorshome-long-riser) peaks exactly at the cut, then 0.8 s of calm black. A very low serious bed (user's hitslab track) runs under the news part only. `scripts/make-hook-audio.mjs` normalises everything to the main VO loudness.
- Export: `exports/hook.mp4`; `exports/jio-ipo-casestudy-v6.mp4` = hook + v5 (117.5 s, -14.3 LUFS).
- Raw downloads in `refs/hook-src/` (~4.5 GB) can be deleted when no longer needed (ask the user first).

## 2026-10-13 (g) Jio IPO case study v5
- F29: the Facebook/Google labels moved off the slices into a legend under the pie (the % counts as each slice sweeps in).
- F30: the +25% badge now sits above the card (no overlap); the new price counts up from ₹0 to ₹299.
- Export: `exports/jio-ipo-casestudy-v5.mp4`. The v4 composition is backed up at `refs/index-v4.html`. The audit is clean.

## 2026-10-13 (f) Jio IPO case study v4
- End card: after the click, the Follow button turns into a white "Following" button with a tick. The F04 "365 days a year" tag now appears right after the first calendar.
- Export: `exports/jio-ipo-casestudy-v4.mp4`. The v3 composition is backed up at `refs/index-v3.html`. The layout audit is clean.

## 2026-10-13 (e) Jio IPO case study v3 (user feedback on v2)
- Donut (F23) rebuilt:
  - The % sits inside the ring, with the Vi logo in the centre.
  - Legend chips go under the donut instead of a tag running off-frame.
  - Soft round shadow.
- New `engines/hyperframes/scripts/layout-audit.mjs`: seeks every scene (mid and end) and flags text, labels and cards outside the Instagram-safe box (x 70-1010, y 260-1560), text overflowing its box, and SVG text outside its graphic. Run it before every render.
- Graph scenes: no posterized motion, smooth only.
- Text sync:
  - Every headline shows ONLY words spoken in that frame; repeats across frames were removed (e.g. "And it gets worse", "₹82 crore profit", "It was cheap").
  - Each word appears about 0.1 s before it is spoken.
  - Number headlines stay hidden until their count starts.
  - Captions appear 0.08 s early.
- Retimed: F31 84.3, F32 84.3-86.05, F33 starts on "37,700".
- Export: `exports/jio-ipo-casestudy-v3.mp4`. The v2 composition is backed up at `refs/index-v2.html`.

## 2026-10-13 (d) Jio IPO case study v2 (user feedback on v1)
- VO at 1.10x, pitch unchanged: `scripts/speed-retime.mjs` (ffmpeg atempo) writes `raw/vo-110.wav` (104.6 s), retimed `beats.json` (1x kept as `beats-1x.json`) and `graphics/story/assets/words.js/json` (word clock).
- Sync:
  - Every key visual lands on its spoken word (`W(word)` / `off()` / `o.w`).
  - SFX use the same word clock.
  - Removed the riser and low hit at 0:50 ("too AI-ish").
- Professional chart motion:
  - Bars grow from their base and numbers count.
  - Lines draw on and area fills reveal.
  - The donut ring draws, then the arc sweeps with a counting %; pie slices sweep out on each name.
  - Stamps slam with a camera shake; the stopwatch sweeps.
  - The balance beam tips with physics; chess pawns topple; the receipt prints.
- Captions:
  - Exact VO words, aligned word by word, balanced lines, no orphan page.
  - F07 and F31 extended so the last spoken words are captioned.
- Export: `exports/jio-ipo-casestudy-v2.mp4` (105 s, 30 fps). The v1 composition is backed up at `refs/index-v1-1x.html`.

## 2026-10-13 (c) Jio IPO case study: animated video
- Storyboard approved. Change asked for and made: F10 now has 2 drawn people (blink, nod, "You" turns worried when the free one is hired).
- Motion per user request:
  - Smooth at 30 fps everywhere (no on-twos stepping).
  - Exactly ONE posterized element per scene: the hero object breathes at 7.5 fps; in F10 the people blink and nod.
  - Smooth zoom-blur transitions between scenes.
  - Smooth disc wipes both ways (tint to blue and blue to tint).
- Audio: `scripts/make-sfx.mjs` (no music): whooshes, pops, click, riser and 2 low hits. Mixed with the trimmed VO into `raw/mix.wav` (-14.3 LUFS) and also used in the composition.
- Export: `exports/jio-ipo-casestudy.mp4` (hyperframes render, 30 fps, quality delivery). The storyboard version is backed up at `refs/index-storyboard-v1.html`.

## 2026-10-13 (b) Jio IPO case study: final storyboard (new script)
- Locked the approved v6 style for future work:
  - Tint-white motion graphics with full-blue highlights.
  - Real B&W clips with captions and NO source tags.
  - Full-frame photos with NO tags.
  - Rebuilt newspapers.
  - Clean high-res cutouts.
  - Frames of 2.5–3 s or longer (photos 1–1.5 s); text kept in the safe band (y 300–1540).
- Project `projects/jio-ipo/`:
  - VO `raw/vo.flac` (121 s), trimmed to `raw/vo-trim.wav` (115.0 s, 21 cuts).
  - Transcripts in `transcript.json` and `transcript-trim.json`.
  - Fact-checked figures in `STORYBOARD.md`.
- Storyboard composition `graphics/story/` (HyperFrames):
  - 39 beats in `beats.json`; `node build.mjs` writes the clip tags.
  - Animated and ready to become the final film.
  - Frames: `exports/storyboard/F01–F39.png`. Board: `jio-ipo-storyboard-p1..p4.png` plus `-overview.png`.
- Installed (user level): yt-dlp 2026.08.19, rembg[cpu] (birefnet-portrait cutouts) and vtracer (unused, can be removed).
- Real media:
  - Clips (yt-dlp, B&W graded): `refs/video-src/credits.json`.
  - Photos, cutouts and logos: `refs/downloads/credits.json`. The Ambani photo is CC BY-NC-SA.
- Next: user review of the storyboard, then full animation with SFX and export. After approval, put the tint background into CLAUDE.md, the theme and the template.

## 2026-10-13 (new direction: deeper case study, style samples)
- Senior feedback: go deeper. New look: solid white-blue tint background (`--color-tint` #EAF2FC), blue accent + blue text, FULL BLUE replaces orange for ~5 highlight beats (white text), B&W real clips with grain + line screen + rolling white captions (1.5-3 s, muted), full-frame real photos (~1 s), real website / rebuilt newspaper clippings with highlighter. MG scenes recreated from real references (reference Japan-style), real brands keep their colours.
- Theme tokens added: tint, blueDeep, blueSoft. Samples: `projects/jio-free-bait/graphics/samples/` -> `graphics/samples-out/` (board + 15 s reel). Footage: Commons CC clips (refs/video).
- Open: user to send the new script + audio; decide on YouTube/news footage (Ambani AGM, SIM queues) = copyright + needs yt-dlp install (ask).

## 2026-10-09 (jio-free-bait: music removed, SFX kept)
- User kept the SFX, dropped the background music. `SFX_ONLY=1 node scripts/make-music.mjs ...` writes whooshes + risers + bait hit at the original gain (`raw/sfx.wav`); remixed with the trimmed VO, same ducking -> `raw/mix-sfx.wav` (-14.3 LUFS). Picture unchanged (no re-render).
- Updated `exports/jio-free-bait.mp4`, `exports/jio-free-bait-master.mov` (video stream copied), and `graphics/main/assets/mix.wav` (Studio matches).

## 2026-10-09 (jio-free-bait animated, v5)
- Audio: `scripts/trim-vo.mjs` cut 11 silences > 0.5 s to 0.3 s (0.15 s kept each side, speech untouched): 45.09 -> 42.12 s; `transcript-trim.json`,
  `raw/beats-trim.json`. Beats re-anchored 0.1 s before each line's first word. Music: `scripts/make-music.mjs` (original synth bed, D minor,
  thinned under question/price hike, hit on "bait", whooshes on colour changes), ducked under VO (sidechaincompress), mix -14 LUFS, music ~ -30 LUFS.
- Animation (`graphics/main/index.html`, frames kept from v4 = `refs/index-v4-frames.html`): reference grammar studied frame by frame
  (shot-in 3f blur + 1.18x settle, objects enter defocused, shadows wipe in after landing, pull-back camera, 3f defocus out, stem-then-wipe labels,
  ghost-ink, posterized pose toggles). One posterized element per beat (7.5/10 fps). Counters, draw-ons, swings, walk cycle, bubbles, cursor clicks.
  Blue <-> orange = smooth expo disc wipe from the frame centre. Check passes. Stepped tweens snap to the 15 fps grid (holds line up).
- Exports: `exports/jio-free-bait.mp4` (H.264 CRF 15 + AAC 320k, 42.8 s, -14.3 LUFS) and `exports/jio-free-bait-master.mov` (ProRes, frame-exact).
- Next: user review notes; optional swap of the synth bed for a licensed track; Premiere handoff if cuts/b-roll are added.

## 2026-10-09 (jio-free-bait F03, F04, F19 fixes)
- Phone frames F03 + F19: glass shine rounded to the phone corners (square corner artefact gone), soft rounded drop shadow on the phone, ₹299 sized to fit the card.
- F04: Ambani head re-cropped centred on the plate (`assets/photos/ambani-head.png`). Other frames unchanged. Check passes.

## 2026-10-09 (jio-free-bait final frames, v4)
- User approved v3 elements + realistic shadows, wanted v1's headline drop shadow back. Added `.hero` hard shadow 0.055em (navy; white on orange).
- Cast shadows moved to a per-scene layer under all objects (planes/beams prepended to the back). Text auto-fits x 90-930 after fonts load
  (build wrapped in document.fonts.ready); labels can centre on x 510 (`label(s, text, "c", y)`). Right-side reels buttons + bottom caption zone kept clear.
- F25: water depth gradient + sharp bubbles near fish/hook + blurred foreground bubbles. F26: logo + Follow + small stars only ("Next..." removed).
- F10 headline stacked on two lines. Check passes (only warnings: sub-composition split, two small-contrast samples mid blur-in).
- Backups: `refs/index-v3.html`. Frames + board in `graphics/frames/`.
- Next: animation pass (sub-compositions per beat, choreography, transitions, SFX) -> export.

## 2026-10-09 (jio-free-bait v3: reference grammar)
- User rejected v2 (real photos pasted as-is looked amateur, ₹500 looked fake). New rule RULES 7h + memory: photos only for big-name people; all other
  real things redrawn from real references in the white-mg rendering (gradients, no outlines, long cast shadows, beams/planes, ghost words).
- Studied all 9 reference key-frame sheets. New `graphics/main/assets/real-kit.js`: Jio SIM (from real red SIM), SIM chip side, ₹500 note redrawn
  (RBI GODL crops for portrait/emblem/seal), note bundle with strap, peel calendar, calculator, results report, kraft price tag, ATM, kettle, chai glass,
  tapri, chalkboard, silhouettes, stopwatch, hook, door, 3D bars, fish. Element board: `graphics/kit-board/`.
- Rebuilt all 26 beats (one hero object each; Ambani = B&W head on lime 8-gon + stick limbs). Shadows attach to object bases (`el(...,{shadow})`).
  Check passes. v1/v2 kept in `refs/index-v1-icons.html`, `refs/index-v2-photos.html`.
- Weak spots to iterate if the user wants: crowd silhouettes (F16) still simple, ATM (F10) plain, Ambani limbs basic.
- Next: user notes -> animation pass -> export.

## 2026-10-09 (jio-free-bait v2: real photos)
- User: v1 felt "iconish"; wants a real case-study feel with real photos in our style. New RULES 7h.
- 10 Commons photos (licences in `projects/jio-free-bait/CREDITS.md`): Jio SIM pack, ₹500 note (RBI, GODL), Mukesh Ambani (CC0),
  chai-wala stall, kettles, cutting chai glass, Kolkata crowd (CC0), Jio World Centre, man on phone. Originals in `refs/downloads/`.
- Treatments: photo cards (`.photo`), B&W people on 8-gon plates with head pop-out (`bust()`), note photo stacks (`notes()`),
  glass via clip-path. `hyperframes remove-background` (u2net_human_seg) only cuts PEOPLE cleanly; objects -> photo cards.
  Cutout alpha cleaned with ffmpeg geq (threshold 110) or the white sticker edge turns faint haze into a box.
- 18 beats updated; drawn icons kept only for metaphors/data (tags, machine, hook, door, charts, calendars). Check passes.
- v1 kept at `refs/index-v1-icons.html`. Board + F01-F26 regenerated in `graphics/frames/`.
- Next: user notes -> animation pass (sub-compositions, choreography, transitions, SFX) -> export.

## 2026-10-09 (jio-free-bait story frame board)
- New project `projects/jio-free-bait/` (45.09 s ElevenLabs VO in raw/). Word timings via local openai-whisper (small) -> `transcript.json`
  (hyperframes transcribe had no whisper runtime; python `whisper` was already installed, models cached).
- Facts checked: ₹30,049 Cr = Jio Platforms FY26 PAT (+15.1% vs ₹26,109 Cr FY25); ₹82 Cr/day; 100M users in 170 days (Feb 2017);
  tariffs +12-25% from 3 Jul 2024 (₹239 -> ₹299). Table in `STORYBOARD.md`.
- Built `graphics/main/index.html`: 26 back-to-back beat clips (F01-F26) timed to the VO, audio attached, shot-in + ink + pops per beat;
  `assets/story-kit.js` = brand-tinted illustrations (calendars, money, phone UI, SIM, chai stall, machine, hook, fish, door, stopwatch...).
  Orange beats: F09-F10, F19-F20, F25. Check passes (warnings only: split into sub-compositions for the animation pass).
- Board: `graphics/frames/jio-free-bait-storyboard.png` + F01-F26.png. Real-object colours (aluminium kettle, wood, tea) are the only non-theme fills.
- Next: user notes on frames -> animation pass (sub-composition per beat, per-beat choreography, transitions, SFX) -> export.

## 2026-10-09 (Codebasics brand + jio-ipo sample frames)
- User: brand = Codebasics (`Codebasics Brand Guidelines/`). Same reference style, but background brand blue #307FE2, elements in the brand palette; real companies keep their logo.
- `theme/theme.json` now Codebasics: blue #307FE2, purple #7C55C6, slate #3F4A76, navy #1E1A34, lime #E3E935, orange #FF7E31, green #00C488, pink #E31C78 (sampled from CB-PANTONE-Palette.png); fonts Saira 800/300, Saira Condensed 700, Kanit 400/600. `theme.css` regenerated (woff2 from Google Fonts).
- Template now links `assets/theme.css`, default bg = brand blue. CLAUDE.md, RULES 5, STYLE_SPEC palette/type, VISUAL_DIRECTION updated (old "never Codebasics" rule removed on user request).
- Built `projects/jio-ipo/graphics/main` (2.8 s composition, check passes): A "Jio" logo on white 8-gon sticker + name tag; B "launched its" logo lifts off an illustrated BSE tower (drawn from 3 Commons photos); C "IPO" hero + real-UI IPO card (price band/dates blurred), cursor on Apply.
- Fact check (2026-10-09): Jio Platforms IPO NOT open yet; BSE + NSE listing per DRHP, dates/price band tentative -> no numbers on screen.
- Frames: `projects/jio-ipo/graphics/frames/` (1-jio, 2-launched-its, 3-ipo, jio-ipo-board.png). No video rendered (user asked for frames only).
- Leftover: old Inter/JetBrains woff2 still in `engines/hyperframes/assets/fonts` (unused now; delete only with user OK).
- Next: user feedback on frames; then animate/export. BSE tower can become an `MGS` part after approval.

## 2026-10-09 (clean copy: HyperFrames-only, no presenter)
- This folder is a cleaned copy of the pipeline. It is now **HyperFrames-only** and has **no presenter** (presenter: none by default; ask before adding one).
- Removed (~1.77 GB):
  - Personal presenter: character boards/PNGs, head photos and cutouts, `My image reference/`, engine `assets/character/heads/`, demos character-board, character-export, setting-test, kit-test, `library/elements/setting-japan.png`.
  - Remotion: `engines/remotion/`, root `package.json`, `.claude/skills/remotion-*` (12), the 7 Remotion `.tsx` library components, `tests/5s-shootout/`, `renders/setup-test/`.
  - One-off work: every project except `projects/_template/`, `renders/out.mov`, engine `index.html` setup test, demo `snapshots/`.
- Kept the rig `assets/character/me-character.js`, now with no head bundled (`HEADS` empty, draws the body only until a head is registered). `scripts/presenter-heads.mjs` now takes `<photosDir> <outDir>`.
- Template no longer loads the character. Docs updated (CLAUDE, START_HERE, HANDOFF, README files, skill, /setup, RULES, STYLE_SPEC). All style rules unchanged.
- Verified: search finds no "remotion", "Sree", "presenter/heads" or "My image reference" anywhere. "MeChar" remains only as the rig's internal name. Test scaffold `zz-check` with an `MG.ink` word reveal and an `MGE.place` bulb passed `npx --yes hyperframes@0.8.141 check` (lint, runtime, layout, motion, contrast). Then deleted.
- Not touched: user-wide skills in `~/.claude/skills` (hyperframes*, remotion-to-hyperframes).
- Next: user sends a brief; build it with `/new-graphic` or `/new-edit`.

## Carried over (still valid)
- Engine: HyperFrames 0.8.141 in `engines/hyperframes`. Alpha: `render --format mov` = ProRes 4444 (yuva444p12le). Env: Node 24.13.0, npm 11.6.2, FFmpeg 8.1.
- Theme: `scripts/theme-css.mjs` builds `assets/theme.css` from `theme/theme.json` (fonts must be local files). Fonts/colours still placeholder.
- Kit: `mg-kit.js` / `mg-kit.css` (on-twos stepping, ghost-ink, shot-in, whip, pops, floor-plane palettes), `mg-elements.js` (25 designed elements + search bar), `mg-scenes.js` (illustrated settings), `scripts/get-icon.mjs`, `scripts/place-photo.mjs`, `scripts/export.mjs` (keeps on-twos holds; HF built-in MP4 smears them).
- Style: white-collage reference analysis in `library/references/white-mg/` (RULES.md, STYLE_SPEC.md, MOTION_NOTES, metrics); assets research in `library/references/ASSET_SOURCES.md`.
- Downloaded once (user cache): HyperFrames bg-removal model (u2net_human_seg, ~168 MB) + onnxruntime-node.
- Optional upgrade (needs user OK): HeyGen CLI sign-in unlocks `media-use resolve`; 3dicons.co CC0 pack.
