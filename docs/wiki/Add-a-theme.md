# Add a theme

**Last updated:** October 20, 2026

A theme is one folder. Storybook, the docs pages, the tests and the package all find it on their own.

## Steps

1. **Copy a theme folder.** Copy the closest one in `tokens/themes/` and name the copy after the product, like `tokens/themes/voyager`. The folder's name is the theme's id.
2. **Name it.** Edit `theme.json` in the new folder:
   ```json
   { "name": "Starlight", "product": "Voyager", "order": 4, "alwaysDark": false }
   ```
   `name` is what people see in Storybook's Theme picker. `order` is its place in that list.
3. **Change the look, not the space.** Change colors, type, motion and art in the theme's files, and pick the roundness in `shape.json`: `square`, `standard` or `round`. Spacing and sizes stay in `tokens/base/`; a test fails if a theme sets them.
4. **Dark mode.** Put dark values in a `dark/` folder inside the theme, only for names the theme already has. A theme that's always dark has no `dark/` folder; set `"alwaysDark": true`. A theme that's mostly dark can still have a light mode for one part: Fireside's `dark/` folder changes only its work area ([D61](Decisions.md)).
5. **Fonts.** Add `src/fonts/<id>.css`, listing only the weights the type tokens use.
6. **Build and test.** Run `npm run test:update`. It builds the tokens, records the new theme's values in the token lock, and runs every check:
   - every shared token name is defined
   - text passes 4.5:1 contrast, in light and dark
   - no token is set twice in the theme
   - spacing is left to the base
7. **Look at it.** Run `npm run storybook`, then pick the new theme in the theme picker above any story.
8. **Open a pull request in lantern-code** and add the `update-screenshots` label, so every story gets screenshots in the new theme.
9. **Write it up in this repo.** In a second pull request here, add the theme to [Themes](Themes) and a decision to [Decisions](Decisions). Link the two pull requests to each other.

## A theme kept in its own repo

A theme for a client project stays in that project's private repo and is never added to lantern-code. It builds against Lantern's base and passes the same checks.

1. **Make the folder in the other repo,** like `tokens/themes/<id>`. It holds the same files as a theme here: `theme.json`, the token files and a `dark/` folder if it has dark mode. Its `fonts.css` (the weights its type tokens use) and any background images named in `theme.json` sit in the same folder.
2. **Name the art its glass sits on.** The glass contrast check needs the colors behind see-through glass, which a theme here names in the test itself. A theme kept outside lists them in `theme.json` instead, each a color or a token name in braces:
   ```json
   { "name": "Candle", "product": "Sample app", "order": 9, "alwaysDark": false, "glassOnArt": ["{color-accent-base}", "#5b0f1a"], "tilesOnArt": true }
   ```
   `tilesOnArt` is true when the page shell's tiles sit on that art, as in Spotlight's header: the check then uses the tiles' light focus glow. Leave it out when the art carries other components, which wear the theme's focus ring.
3. **Check it.** With lantern-code checked out next to the other repo:
   ```sh
   cd lantern-code && npm ci && npm run check-theme -- ../other-repo/tokens/themes/<id>
   ```
   It builds every theme into `build-theme-check/` and runs the contract, readability, spacing, roundness, once-per-token and glass contrast checks on all of them. Lantern's own build and token lock stay as they were.
4. **Take the build.** The built theme is `build-theme-check/css/<id>.css` and `build-theme-check/json/<id>.json`. Copy them into the other repo, next to where its app loads Lantern's `base.css` and `components.css`.
5. **Check it on every pull request there.** The other repo's workflow checks out lantern-code beside it, with a token that can read it, and runs step 3. A pull request there fails the way one here would.

The same checks run in both places. A shared token name added to Lantern's base shows up in the other repo as a failing contract check the next time it runs.

## What finds the new theme on its own

- The token build (`scripts/build-tokens.mjs`) builds every folder and writes `build/themes.json`. Folders named in `LANTERN_THEME_DIRS` are built too, and `LANTERN_BUILD_DIR` moves the output; `npm run check-theme` sets both.
- Storybook's Theme picker and the side-by-side view read `build/themes.json`.
- The Foundations pages and the visual tests read the built tokens and `build/themes.json`.
- The package serves its tokens at `themes/<id>.css` and its fonts at `fonts/<id>.css`.
