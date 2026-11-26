# NeoJs Client

Fresh 26.3 base, rebranded as NeoJs Client with a custom image.

## Files

- **`NeoJs Client 26.3.html`** — the finished client. Open this one.
- `eagler26.3.html` — untouched original downloaded from the
  [eagler26.3 GitHub release](https://github.com/daditto2012/eaglercraft-versions/releases/tag/eagler26.3).
- `background.jpg` — `/Users/aldo188/Downloads/Image.jpg` converted to a real JPEG
  (the source file was WebP data with a `.jpg` name).
- `favicon.jpg` — 64×64 version of the same image.

## What was changed

- Title: `NeoJs Client 26.3`
- Favicon, boot splash, and custom-loading art: your image, embedded directly in the HTML
  so the client stays a single self-contained file.
- **In-game main menu background** (shown after skin selection): the six title-screen
  panorama textures inside the embedded `assets.epk` were replaced with your image, so the
  game menu uses it too.
- In-game brand text (bottom-left of the menu), credits title, pack description, and
  crash/rotate messages now read `NeoJs Client` instead of `Eaglercraft 26.3`.
- Boot screen title: `NeoJs Client` (centered over the image).
- Loading text: `Loading NeoJs Client 26.3…`
- The Mojang stage is removed entirely — no red screen, no logo swap. The image
  and `NeoJs Client` title stay on screen for the whole boot, then fade to the game.

### NeoJs Client add-ons

- **Custom FPS counter** — a small color-coded pill in the top-left (green/yellow/red).
  Toggle it with **F6**; your choice is remembered between launches.
- **Credits** — a `NeoJs Client` section was added at the top of the scrolling credits,
  crediting `Relesermton` and `Siento` for the client.
- **Mods list** — press **F7** to see what's installed.
- **Custom splashes** — the yellow title-screen lines include your five additions:
  "Smooth On Inside", "Coded In Pure 100% html", "Good In inside Good In outside",
  "Minecraft minecraft Minecraft", and "Why Bsod Is in Windows where the chrome book one".
- **Resource packs** — three optional packs (in `resourcepacks/`, or flat in the
  `github-pages/` upload folder): `NeoJs Branding.zip`,
  `NeoJs Menu Background.zip`, and `NeoJs Settings Text.zip`. Enable them in-game under
  Options → Resource Packs.
- The in-game menu buttons keep their **original vanilla labels** (Singleplayer,
  Multiplayer, Options..., Quit Game). The extra on-screen MODS button was removed —
  the mod list is opened with F7 instead.

The old `v2.6.0` build was left as-is.

The `work/` folder holds the extracted asset pack and the EPK tool used to swap the menu
background. It is not needed to run the client.

## Hosting on GitHub Pages

Use the flat `github-pages/` folder — upload its **contents** to the repo root, not the
folder itself. That build splits the old 76 MB single file into:

- `index.html` — about 2.4 MB (page code + boot art + Brotli decoder)
- `classes.wasm.br`, `mesh.wasm.br`, `server.wasm.br` — compressed runtime
- `assets.epk` — game assets
- `sounds.epk.part1`, `sounds.epk.part2` — sound data, split into two parts because
  GitHub's web uploader rejects individual files over 25 MB; the loader rejoins them

Tested over HTTP and on GitHub Pages: all files load and the game boots normally. Note that
this split build requires a web server (GitHub Pages works); it will not run by
double-clicking the file because browsers block `fetch()` from `file://`. Keep
`NeoJs Client 26.3.html` if you want the original double-clickable single-file version.

Live site: https://relesermton.github.io/NeoJs-Client-26.3/
