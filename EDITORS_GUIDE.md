# How we make a Codebasics case-study reel (Jio and Ramayana)

Explained simply, one point at a time. Every link opens the real file in this repo.

---

## 0. The big idea
- Claude Code builds the whole reel. We write the script, record the voice, and act as the boss who says yes or no.
- HyperFrames turns web pages into video. Every frame is HTML and code, so it is exact and repeatable.
- Everything Claude needs is in this one GitHub repo, so anyone gets the same result.
- See the real result first: the [Ramayana storyboard](#see-the-real-storyboard-ramayana) at the bottom of this page.

## 1. Get the system (first time only)
- The repo: [codebasics-all/Codebasics-Motion-graphics](https://github.com/codebasics-all/Codebasics-Motion-graphics). It holds all the code, the Codebasics brand, the style rules, the memory and the full process.
- Clone it to your PC.
- Follow [SETUP_NEW_PC.md](SETUP_NEW_PC.md) step by step: Node, FFmpeg, Python, Chrome, the Whisper and cut-out models, and the HyperFrames skills.
- Run `npm run setup:check` until every required line says OK ([the checker](scripts/setup-check.mjs)).
- Test it: in [projects/Ramayana/graphics/storyboard](projects/Ramayana/graphics/storyboard), run `node shoot.mjs`. You should get the same 66 frames as ours.
- Open the folder in Claude Code (`claude`). It reads [CLAUDE.md](CLAUDE.md) by itself, which tells it what to read first.

## 2. The rulebooks Claude follows (you don't need to memorise them)
- [CURRENT_STYLE.md](CURRENT_STYLE.md) is the latest look: colours, fonts, sizes, captions, motion. It always wins over older notes.
- [brain/](brain) is the full method; start at [brain/README_CODEBASICS.md](brain/README_CODEBASICS.md), then [the pipeline overview](brain/00-pipeline-overview.md).
- [claude-memory/](claude-memory) holds every rule we locked.
- [PROJECT_LOG.md](PROJECT_LOG.md) is the diary of every run.
- [projects/Ramayana/](projects/Ramayana) is the newest finished film, and every new film starts from its kit.
- The brand: [Codebasics Brand Guidelines/](Codebasics%20Brand%20Guidelines) and [theme/theme.json](theme/theme.json).

## 3. What we bring before starting
- The script, written by us.
- The voice-over, recorded by us (we used ElevenLabs).
- Any videos we want used (trailers and the like) in an "Assets by me" folder.
- A brief, usually just spoken into chat. Claude handles typos like "Geo" → Jio or "Kalpi" → Kalki ([the decoding list](brain/14-feedback-history.md#5-decoding-the-users-voice-dictated-briefs)).

## 4. How we prompt (start)
- Type `/new-case-study <name>` ([what that command does](.claude/commands/new-case-study.md)) and give the script, the VO and the brief in one message.
- Answer Claude's per-video questions:
  - Footage in black and white or colour?
  - Open with a news hook or the film's own footage?
  - How many blue "big moment" frames? (About 5.)
  - Music? (None; we add it ourselves.)
  - Voice speed? (1.10x.)
  - Are we OK with downloading YouTube clips?
- For a big film, say "ultracode" so Claude uses many helper agents ([the saved workflows](.claude/workflows)). For small fixes, use normal or high effort to save tokens.

## 5. Step 1: Sound comes first (the clock)
- Whisper writes down every spoken word with its exact time.
- Claude checks it word by word against our script and reports any mismatch.
- Every pause longer than 0.5 s is cut to 0.3 s ([trim-vo.mjs](projects/Ramayana/scripts/trim-vo.mjs)).
- Then the voice is sped up to 1.10x, same pitch ([speed-retime.mjs](projects/Ramayana/scripts/speed-retime.mjs)).
- The final word timings ([words.json](projects/Ramayana/graphics/storyboard/assets/words.json)) become the clock that every picture, caption and sound follows.
- More: [brain/07 audio](brain/07-audio-vo-sfx-mix.md).

## 6. Step 2: The plan (frame by frame)
- Every spoken phrase gets its own frame, and every word has a picture behind it ([the real plan: frames.mjs](projects/Ramayana/graphics/storyboard/frames.mjs)).
- For each line, Claude first asks what the ONE thing is the viewer must understand. Meaning first, looks second ([visual thinking](brain/01-creative-direction-and-visual-thinking.md)).
- Realism check: anything real in the line gets redrawn accurately in our style. That covers places, money, phones, tickets, buildings and logos ([how real things are converted](brain/03-real-world-to-style-conversion.md)).
- About 5 frames become full Codebasics-blue "big moment" frames, for the biggest numbers and turning points.
- Each new picture stays on screen at least 2.5 s, so people can read it.

## 7. Step 3: Research (helpers work in the background)
- Helper agents fact-check every number and date against real sources ([facts.json](projects/Ramayana/refs/facts.json)).
- They find real high-res photos, cut-outs of famous people, real company logos and real video clips, with credits ([clip credits](projects/Ramayana/refs/credits-clips.json)).
- They catalogue every shot in our trailers ([catalogues](projects/Ramayana/refs/catalog)) and write a premium design guide ([design-spec.md](projects/Ramayana/refs/design-spec.md)).
- Claude reads the fact-check first, because a wrong number changes the frame.
- More: [brain/02 research](brain/02-research-fact-check-and-sourcing.md).

## 8. Step 4: The storyboard (still pictures first)
- Claude builds one section perfectly first. It becomes the example every helper copies.
- Helpers build the other sections at the same time ([section code](projects/Ramayana/graphics/storyboard/sections)).
- A "strict teacher" agent reviews each section and lists mistakes. The section is fixed, then reviewed again (at least 2 rounds).
- Claude looks at every frame itself and makes a board: the [section sheets below](#see-the-real-storyboard-ramayana) plus a [text version](projects/Ramayana/STORYBOARD.md).
- **Rule: no animation until we approve the storyboard** ("First, storyboard is important").

## 9. How we give storyboard feedback
- Name the frame (F05, F17…) and say exactly what to change.
- Our notes from Ramayana became permanent rules:
  - no shadows ("plain overlay");
  - text OR captions, never both;
  - everything centred;
  - headline words appear only when spoken.
- A look correction that isn't about just one frame becomes the new default for all future videos ([every feedback round](brain/14-feedback-history.md)).

## 10. Step 5: Animation
- Claude applies our corrections everywhere first, after making a backup.
- One test section is animated first, to catch problems early.
- Then helper agents animate every section, plus one helper that cuts the footage clips ([the animation brief they got](projects/Ramayana/graphics/storyboard/ANIM_BRIEF.md)).
- Each helper checks its animation against the approved storyboard pictures.
- More: [brain/10 animation](brain/10-animation-build.md), [brain/05 motion](brain/05-motion-system.md).

## 11. Step 6: Put it together and check
- Every frame is measured and centred automatically ([measure.mjs](projects/Ramayana/graphics/storyboard/measure.mjs)).
- About 200 sound effects are placed on the key moments: soft pops, clicks, whooshes. No fake risers ([sfx.json](projects/Ramayana/graphics/storyboard/sfx.json)).
- Voice and SFX are mixed to Instagram loudness ([make-mix.mjs](projects/Ramayana/scripts/make-mix.mjs)).
- **Rule: the layout audit must be clean before every render** ([layout-audit.mjs](engines/hyperframes/scripts/layout-audit.mjs)). Nothing may go off-screen or overflow, like a % spilling out of a donut.

## 12. Step 7: Render and deliver
- HyperFrames renders the MP4: 1080x1920, 30 fps, about 40 minutes for a 2-minute film ([the composition](projects/Ramayana/graphics/storyboard/index.html)).
- Claude must say honestly what it checked and what it didn't (for example "duration only").
- More: [brain/12 render](brain/12-render-export-and-premiere.md).

## 13. Feedback rounds after the render
- Give notes with a timestamp or frame number.
- Claude restates the notes as a list first, then changes ONLY what we named. Everything else stays identical.
- "A bit more / less" means a small nudge from the last approved version, never a new effect.
- Each round is a new numbered version (v1, v2, v3, v4), and the old one is kept.
- Our senior reviewer's comments come through us and override older style rules.

## 14. The look rules (what makes it "ours"), all in [CURRENT_STYLE.md](CURRENT_STYLE.md)
- Off-white background (#F8F9FB) plus about 5 Codebasics-blue moments.
- Flat look: no shadows anywhere.
- Kanit for our text, Poppins for captions (white on a black box at y 1200), and the real font inside real objects (calculator, app, newspaper).
- Screen text shows only the spoken words, appearing 0.1 s before you hear them, never repeated.
- Smooth 30 fps motion, with exactly one "stop-motion" (posterized) element per scene. Charts are fully smooth.
- Charts always grow, draw and count. They are never static.
- Real companies keep their own logos and colours. Bad news is shown in grey, never alarm red.
- No emojis, nothing kiddish, no source tags on clips.
- End card: white, the Codebasics logo, and a Follow button that turns into Following.
- Where the style came from: the [reference reels](Reference%20Motion%20graphics) and their [frame-by-frame study](library/references/white-mg).

## 15. Jio extra: the news hook (10–13 s opening)
- Real news-reader voices and real clips: mostly black-and-white vintage, some colour with an old-news-channel look.
- Short white phrases of exactly what the voice says, kept away from faces.
- Hard cut to black on the last spoken word, a reverb tail, then our main voice starts.
- The real files: [hook composition](projects/jio-ipo/graphics/hook/index.html), [hook audio](projects/jio-ipo/scripts/make-hook-audio.mjs), [Jio IPO storyboard](projects/jio-ipo/STORYBOARD.md), [Jio "free was the bait" storyboard](projects/jio-free-bait/STORYBOARD.md), [brain/08 news hook](brain/08-news-hook-format.md).

## 16. After every run
- Claude updates [PROJECT_LOG.md](PROJECT_LOG.md) and the memory with what changed and which rules replaced older ones.
- Approved animations go into the [library](library) with `/save-to-library`.
- Commit and push to GitHub, so the next editor gets the latest.

## 17. Golden rules for editors
- Storyboard first, animation second.
- Meaning first, beauty second.
- Change only what's asked.
- Facts must be checked.
- Real things get redrawn, never pasted.
- Audit before every render.
- Be honest about what wasn't checked.
- Always push your work back to the repo.

---

## See the real storyboard (Ramayana)
The approved board Claude made before animating: 8 sections, 44 frames, each with its spoken line, visual, motion, captions and assets. These are the 2026-10-22 board sheets; the corrections in point 9 (no shadows, text OR captions, centring) were applied after this, during animation.

### S1 The price tag
![S1 The price tag](projects/Ramayana/graphics/storyboard/board/S1.png)

### S2 The math
![S2 The math](projects/Ramayana/graphics/storyboard/board/S2.png)

### S3 The producer
![S3 The producer](projects/Ramayana/graphics/storyboard/board/S3.png)

### S4 The money
![S4 The money](projects/Ramayana/graphics/storyboard/board/S4.png)

### S5 The risk
![S5 The risk](projects/Ramayana/graphics/storyboard/board/S5.png)

### S6 The real plan
![S6 The real plan](projects/Ramayana/graphics/storyboard/board/S6.png)

### S7 The bridge
![S7 The bridge](projects/Ramayana/graphics/storyboard/board/S7.png)

### S8 CTA
![S8 CTA](projects/Ramayana/graphics/storyboard/board/S8.png)
