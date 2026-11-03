# Space Timer

Paste a script and see how long it takes to read at your speaking pace, split by section. Live at https://timer.shovonix.dev

Built by [Shovon Arifin](https://shovonix.dev). Part of the Space tools, with [Space Prompter](https://studio.shovonix.dev).

- **Your pace**: set words per minute, or measure it by reading a sample (or the start of your script) out loud.
- **Sections**: found from `# Heading`, `[BRACKETS]`, ALL CAPS lines or short lines ending in a colon. Without headings, each paragraph is a section.
- **Directions**: text in `[square brackets]` isn't counted. `[pause]` or `[pause 2s]` adds time.
- **Target**: set a length (e.g. `0:60`) to see how many words to cut or add.
- **Export**: copy as YouTube chapters (estimated), copy timings, or download CSV. "Open in Prompter" copies the script and opens Space Prompter.

Everything lives in `index.html`; there is no build step. Scripts and settings are stored in the browser (`localStorage`).
