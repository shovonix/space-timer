# Space Timer

Paste a script, see how long it takes to read at your pace, split by section. Live at https://timer.shovonix.dev

## How this repo works
- Everything is in `index.html`. No build step, no framework, no npm. Keep it that way unless Shovon asks.
- Scripts and settings live in the browser (`localStorage`). Nothing is sent to a server.
- Preview locally: `python3 -m http.server 8000`, then open http://localhost:8000
- `landing/space-timer/` is the landing page.

## Space key (signature of every Space app)
- Tap Space = pace stopwatch. Hold Space = big read-time screen.
- Uses the shared `SpaceKey` helper and the on-screen keycap (`#spacehint`). It never fires while typing in a field.
- Keep the Space key working and fun after every change. If you add a feature, ask whether it deserves the Space key.

## Design
- Black and white only. Tokens at the top of `index.html`: `--bg #070707`, `--fg #F0F0EE`, `--hair #2A2A2C`. `--red #E8463A` is for warnings only.
- Fonts: Archivo (UI), JetBrains Mono (numbers, keycap).

## Rules
- After changing any cached file, bump `CACHE` in `sw.js` (e.g. `space-timer-v1` → `v2`) so installed copies update.
- No analytics or tracking scripts. Traffic stats come from nginx logs on the server.
- Licence: all rights reserved, no open-source licence. Don't add one.
- Ask before adding a dependency, a build step, or a backend.

## Workflow
- Work on the Mac in `~/Sites/space/space-timer`. Preview locally, commit small, push to `main`.
- Live files: `/home/timer/htdocs/timer.shovonix.dev` (CloudPanel site user `timer`). Landing page lives on the hub: `/home/shovonix/htdocs/shovonix.dev/space-timer/`.
- Deploy: push to `main`, then on the VPS run `deploy-space timer` as root. It pulls `main` as user `timer` (fast-forward only) and checks the site returns 200.
- Git data lives outside the web root at `/home/timer/space-timer.git` (so `.git` is never served). `landing/`, `README.md` and `CLAUDE.md` are excluded from the live folder via sparse-checkout.
- Never edit the live files on the VPS directly.
