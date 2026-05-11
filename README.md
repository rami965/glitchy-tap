# GlitchyTap — Mobile Games

Independent mobile game studio. This repository is the source for the GlitchyTap GitHub Pages site — a unified hub for all game landing pages, privacy policies, and studio information.

**Live site:** `https://rami965.github.io/glitchy-tap/`

---

## What This Repo Is

One repo, one deployment. Every game published by GlitchyTap gets its own subdirectory here with:
- A landing page (`index.html`)

No build tools, no frameworks, no dependencies. Pure HTML/CSS served directly by GitHub Pages.

---

## Repository Structure

```
/
├── index.html                        # Studio hub — lists all games
├── README.md                         # This file
│
├── deep-break/
│   ├── index.html                    # Deep Break landing page
│   └── privacy-policy/
│       └── index.html                # Deep Break privacy policy
│
└── [future-game]/
    ├── index.html
    └── privacy-policy/
        └── index.html
```

---

## Games

| Game | Directory | Platform | Status |
|---|---|---|---|
| Deep Break | `/deep-break/` | Android (Google Play) | Live |

---

## Design System

### Studio root (`index.html`)
- **Aesthetic:** Dark editorial — `#0c0c0c` background, `#c8ff00` acid lime accent
- **Fonts:** Archivo Black (display) + Plus Jakarta Sans (body)
- **Pattern:** Game card grid — each card links to its respective game subdirectory

### Game pages
Each game defines its own visual identity. Guidelines:
- Maintain the shared footer link structure (`Privacy Policy` / `All Games`)
- Keep the back-nav pattern consistent across privacy policy pages
- Use the same HTML structure so adding a game follows the same template

### Deep Break (`/deep-break/`)
- **Aesthetic:** Bioluminescent depth — deep navy, cyan `#00d4ff`, violet `#7b2fff`
- **Fonts:** Syne 800 (display) + Space Mono (labels) + DM Sans (body)

---

## Adding a New Game

1. **Create the directory**
   ```
   mkdir -p [game-slug]/privacy-policy
   ```

2. **Add the landing page**
   Copy `deep-break/index.html` as a starting point and replace all content.
   Update the back link in the footer to `../`.

3. **Add the privacy policy**
   Copy `deep-break/privacy-policy/index.html`.
   Update game name, dates, and contact details.
   Update the back link to `../` (game page) and `../../` (studio root).

4. **Add a card to the studio hub**
   In `index.html`, duplicate the `.game-card` block inside `.games-grid`.
   - Set `href` to `[game-slug]/`
   - Update the thumbnail CSS class (or add a new `thumb-[game-slug]` style)
   - Update title, description, and genre tags
   - Update the `game-count` label

5. **Commit and push**
   ```bash
   git add .
   git commit -m "Add [game name] landing page"
   git push origin main
   ```

GitHub Pages deploys automatically within ~2 minutes of every push.

---

## Stack

| Layer | Choice | Reason |
|---|---|---|
| Hosting | GitHub Pages | Free, no domain management, auto-deploy on push |
| Framework | None | Zero dependencies, instant load, no build step |
| Fonts | Google Fonts (per page) | Loaded only where needed |
| Styling | Vanilla CSS with custom properties | Maintainable, no toolchain |
| Scripting | None / minimal inline JS | Performance and simplicity |

---

## Studio

**GlitchyTap** builds mobile games that are offline-first, ad-free, and privacy-respecting.
All games collect zero personal data.

**Contact:** ramisaid33@gmail.com
**Developer:** Rami Saeed
