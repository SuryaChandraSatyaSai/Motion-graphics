# Current style: the latest rules only (Codebasics case-study reels)

State as of the Ramayana film (animation v4, 2026-10-22), the newest approved work. This page wins over older notes
(CLAUDE.md summary, VISUAL_DIRECTION.md, HANDOFF.md, `library/references/white-mg/RULES.md` / `STYLE_SPEC.md`, older
memory). Full detail with reasons and history: `brain/04-style-system.md`, `brain/05-motion-system.md`,
`brain/06-text-captions-and-typography.md` (written brand-neutral; translate with `brain/README_CODEBASICS.md`).
Working reference production: `projects/Ramayana/graphics/storyboard/` (kit, sections, build, shoot, animshot, measure).

Precedence: the latest dated user instruction wins. A correction to the look that is not limited to one frame becomes
the new default. Change ONLY what the user names; keep everything else (LOCKED 2026-10-13).

## Two modes
- **Case-study mode = DEFAULT** for every narrated explainer / case-study reel. Everything below.
- **Reference mode** (blue background, Saira heroes, on-twos stepping, ghost-ink, cast shadows, floor planes): only when
  the user asks for "the reference look". That is what `theme/theme.json` and the engine kit defaults (`mg-kit.*`) still
  describe.

## Canvas
1080x1920, 30 fps. MG content band x 90-930, y 260-1540. Keep content x < 940 (Reels rail).

## Colour (Codebasics)
| Use | Value |
|---|---|
| MG scene background | white-dominant `#F8F9FB`; end card pure `#FFFFFF` |
| Highlight beats | about 5 per ~2 min, full Codebasics blue `#307FE2` with white text; reserved in the frame plan; the next frame returns to white |
| Accent word on white / on blue | blue `#307FE2` / lime `#E3E935` |
| Hero text / kicker | `#1F2328` / `#6B7280` |
| Bad news (debt, price rise, risk) | neutral: slate `#3F4A76` + iron greys. Never pink/red alarm |
| Other brand hues for things we draw | purple `#7C55C6`, navy `#1E1A34`, orange `#FF7E31`, green `#00C488`, pink `#E31C78`, tint `#EAF2FC`, deep `#1D5BB5`, soft `#C9DDF7` |
| End-card button | logo blue `#3B82F6` |
| Real companies / real objects | their own logo and material colours (plate logos on white chips) |
Balance 60-30-10: neutral white + ink, one scene colour (vary across scenes), one accent.

## Look
- FLAT: no shadows of any kind (drop, cast, contact, floor planes, glow pools, reflections). "I need plain overlay"
  (2026-10-22). Allowed: shading inside an object's own contour, object thickness, a warm light behind a hero.
- Real objects are REDRAWN accurately from real references in this style. Real photos only for big-name people and
  full-frame photos. No emojis (only the 3D heart), nothing kiddish, no icon/thick-outline cartoons.
- No source tags on footage or photos. Person cut-outs clean and high-res (rembg birefnet-portrait).
- Footage grade per video: the subject's own footage full colour + light grain; archival/news B&W vintage.

## Typography
| Element | Font | Size |
|---|---|---|
| Hero headline | Kanit 600, `#1F2328`, letter-spacing -0.01em | 110-150 px (default 150), top y 374 |
| Kicker | Kanit 400, `#6B7280` | 58-62 px, top y 300 |
| Chart values / counters | Kanit 600, fixed digit slots (Kanit has no tabular figures) | 84-92 px |
| Units ("Cr", "%") / ₹ | Kanit 400 at 0.52em / same font at 0.78em (₹-only subset faces) | |
| Labels, tags, chips | Kanit 500/600 (`.tag` 600 32 px on blue, pad 12/24/10, radius 6) | 30-40 px |
| Corner label | Kanit 500, at (70, 270) | 30 px |
| Price tags | Poppins 600 + ₹ subset | |
| Captions | Poppins Medium 500, white on black box | 44 px |
| Text inside real objects | the object's real font (DSEG7 calculators, VT323 feature phones, Roboto apps/stocks/WhatsApp, Arial documents, Courier New receipts, Unifraktur + Georgia newspapers, Nunito Sans for Jio screens) | as the object |
- NEVER Saira (or any brand font) inside visuals. Saira = reference mode only.
- No text shadows. Two weights per frame, kicker-to-hero jump >= 1.8x. Minimum text 18 px. Auto-fit width to 840 px.

## Text rules
- On-screen text = ONLY the words spoken in that frame; never repeated in two frames; no slogans.
- Words are invisible until spoken (no ghost), appear 0.1 s early, keep their layout slot.
- Each MG frame shows EITHER headline text OR captions, never both. Footage is always captioned.
- Every caption phrase and headline line starts with a capital. "Cr" only next to ₹; counts spell "crore".

## Captions (team spec 2026-10-15)
Poppins Medium 500, 44 px, line-height 1.2, letter-spacing -0.005em, white, no stroke/shadow/bold. One line; balanced
phrases, no one-word tails. Box `#000`, padding 8/22/10, radius 4. Box top y 1200, centred (MG frames may drop it below
the graphic via `capTop` in `layout.json`; footage always 1200). In: whole phrase, fade 0.1 s + scale 0.92->1 + rise
8 px over 0.18 s back.out. Out: 0.06 s fade before the next phrase.

## Layout
Every MG frame centred and middle-aligned in the safe area, MEASURED (`measure.mjs` -> `layout.json` `dy`), never
hard-coded. One horizontal axis per section (540 when sharing the screen with captions). Run
`engines/hyperframes/scripts/layout-audit.mjs` and fix every flag before rendering; also check x 90-930 by eye.

## Motion
- Smooth 30 fps; exactly ONE posterized element per non-graph scene (7.5 fps default); chart scenes fully smooth.
- Text in: opacity 0->1 + rise 10 px, 0.22 s power3.out. Scene transition: zoom-blur IN 1.06 + blur 12 -> 1/0 in
  0.42 s power3.out; OUT 1 -> 1.05 + blur 10 in 0.24 s power2.in. Into a blue beat: circle wipe from the object 0.5 s
  expo.inOut.
- Eases: expo.out enter, power3.out grow, power3.inOut move, back.out(1.6) small pops only, power2.in exit.
- Charts grow, draw and count; never static (a donut draws while its % counts). Numbers land 0.1 s before the word.
- Holds: each new visual idea >= 2.5 s; static photos 1-1.5 s; 1-3 % drift on every hold. Movie footage never freezes.
- Footage bar 340 px. Everything keyed to the word clock (`assets/words.json`).

## Audio
VO: silences > 0.5 s cut to 0.3 s, then 1.10x (atempo, pitch kept). SFX: soft whooshes, pops, clicks; no synthetic
risers/hits ("too AI-ish").

## Hook (news-hook format, ~10-13 s)
Real news/speaker voices (yt-dlp, with consent). 70 % B&W vintage clips, 30 % old-news colour. Hook text = only the
spoken words, short centred phrases, kept off faces; context in a small label with the year. No riser: a great-hall
reverb tail on the last words (wet -2 dB), cut everything to black on the last spoken word, then the main VO.
Templates: `projects/jio-ipo/graphics/hook/` and `scripts/make-hook-audio.mjs`.

## End card (LOCKED)
Pure white, Codebasics logo box (230, 640) 620x284, Follow button (320, 1010) 440x124 radius 30 in logo blue, Kanit 600
60 px label, turns into "Following" (white, 4 px ring + tick). Pixel cursor. No sparkles.
