# Setting up this folder on a new PC

Goal: the new PC renders exactly what the original PC renders. Verified 2026-10-29 on Windows 11: 64 of 66 storyboard
frames are bit-identical and 32 of 32 animation moments match; the other 2 frames differ only by logo-image decode
noise you can't see.
Rule (CLAUDE.md): check the latest official docs for HyperFrames and Claude Code first. These are the VERIFIED versions;
newer ones usually work but were not pixel-tested.

## 1. Tools (PowerShell; open a new terminal after each install)

```powershell
winget install Git.Git
winget install OpenJS.NodeJS.LTS
winget install Gyan.FFmpeg
winget install Python.Python.3.14
```

| Tool | Verified version |
|---|---|
| Node.js | 24.13.0 (needs >= 22) |
| FFmpeg | 8.1 full build (gyan.dev) |
| Python | 3.14.2 |
| HyperFrames | 0.8.141, always run as `npx --yes hyperframes@0.8.141 ...` (never install globally) |
| puppeteer-core | 25.13.0 (from `package.json`) |
| Chrome for Testing | 144.0.7559.96 |

## 2. Inside this folder

```powershell
npm install
npm run chrome
npx --yes hyperframes@0.8.141 --version
npm run setup:check
```

`npm run setup:check` lists every tool, version and model with OK / MISSING and the fix for each (run it again after step 3).

- `npm install` gets puppeteer-core (already included in `node_modules/`; running it again is safe).
- `npm run chrome` installs the pinned Chrome into `.cache/puppeteer/` (about 390 MB). The scripts find Chrome
  automatically via `engines/hyperframes/scripts/lib/chrome.mjs` (order: `CHROME_PATH`, `.cache/puppeteer`,
  `~/.cache/puppeteer`, system Chrome). Use the pinned build: other versions can shift anti-aliasing.

## 3. Python packages and models (for transcripts, cut-outs, clip downloads)

```powershell
py -3.14 -m pip install --user "openai-whisper==20250625" "torch==2.10.0" "rembg[cpu]==2.0.85" "onnxruntime==1.31.0" "pymatting==1.1.16" "yt-dlp==2026.8.19" "opencv-python==4.13.0.92" "pillow==12.3.0" "numpy==2.3.5"
py -3.14 -c "import whisper; [whisper.load_model(m) for m in ('base','small','medium','large-v3')]"
py -3.14 -c "from rembg import new_session; new_session('birefnet-portrait')"
```

- Whisper models go to `~/.cache/whisper` (base 139 MB, small 462 MB, medium 1.5 GB, large-v3 2.9 GB). `small` is the default.
- rembg `birefnet-portrait` (928 MB) gives the clean person cut-outs.
- HyperFrames' own cut-out model downloads on first use: `npx --yes hyperframes@0.8.141 remove-background <photo> -o out.png`.
- Do NOT install vtracer (crashes on Python 3.14, unused).

## 4. Claude Code and skills

Install Claude Code (official setup page), run `claude` once to sign in, then:

```powershell
npx skills add heygen-com/hyperframes --all
```

Restart Claude Code. The project's own commands and skill are in `.claude/`. Tell Claude to read `claude-memory/` and
`brain/README_CODEBASICS.md` on the first session (CLAUDE.md already lists them).

## 5. Test it (should match the original)

```powershell
cd projects/Ramayana/graphics/storyboard
node shoot.mjs
```

This writes 66 styleframes to `out/`. Animation stills: `node animshot.mjs F14`. Full video: `npm run render` in the same
folder (HyperFrames 0.8.141). For frame-exact on-twos MP4 or alpha MOV for Premiere, use
`node scripts/export.mjs <graphicDir> <outPath>` from `engines/hyperframes` (see its header).

## Not included (to keep the download small)

Final exported videos, render caches and the full source trailers / YouTube downloads were deleted. The list, with how to
re-download them, is in `projects/Ramayana/DELETED_MEDIA.md`. They are NOT needed to reproduce the output: the clips,
photos and audio actually used are inside `projects/Ramayana/graphics/storyboard/assets/`.
