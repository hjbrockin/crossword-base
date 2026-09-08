# Crosspuzzle

Crosspuzzle is a browser-based crossword game and puzzle editor. It is implemented as a single static HTML page, so it can be opened locally or deployed directly to GitHub Pages without a build step.

## Features

- Generates a 15x15 crossword from a pool of words and clues.
- Displays separate Across and Down clue lists.
- Supports mouse, keyboard, and mobile input.
- Highlights the active word and selected cell.
- Checks answers, reveals individual letters, and clears the player grid.
- Includes zoom controls for the crossword grid.
- Provides an editor for adding, removing, and editing words and clues.
- Supports automatic word placement and manual placement by dragging words onto the preview grid.
- Allows switching between editor and player modes.

## Run Locally

Because this is a static page, no package installation is required.

1. Open `index.html` in a browser, or serve the repository with a local web server:

   ```bash
   python3 -m http.server 4173
   ```

2. Visit `http://localhost:4173`.

Serving the file over HTTP is recommended because it matches the way GitHub Pages hosts the application.

## Deploy to GitHub Pages

1. Push the repository to GitHub.
2. Open the repository's **Settings** tab.
3. Select **Pages** under **Code and automation**.
4. Choose the `main` branch and the repository root (`/`) as the source.
5. Save the configuration and open the generated Pages URL after deployment completes.

The page loads Tailwind CSS and the Poppins font from public CDNs, so the deployed page needs network access to display its intended styling.

## Editing Puzzle Content

The initial word pool is defined near the top of the script in `index.html`. Each entry has this shape:

```js
{ word: "ANSWER", clue: "Clue text", manualPlacement: null }
```

Words must contain letters only and be no longer than 15 characters. The editor can also add words while the page is running.

## Security Note

Editor access is implemented entirely in browser-side JavaScript. The password is therefore visible to anyone who can inspect the page source and should not be treated as secure authentication. Use this editor only for trusted or demonstrative content, or move authentication and puzzle management to a server-backed system for production use.

## Technology

- HTML, CSS, and vanilla JavaScript
- Tailwind CSS via CDN
- Google Fonts via CDN
- No build tool or runtime dependency
