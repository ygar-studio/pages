# Ygar Studio — GitHub Pages

Static GitHub Pages site for **Ygar Studio**, an independent Android game studio.
Published at: `https://<username>.github.io/<repo>/` (configure in repo Settings → Pages → Source: GitHub Actions).

## Project structure

```
teststdy/
├── index.html                        # Studio landing page only (EN/FR toggle)
├── enko/
│   ├── index.html                    # Enko Clues app page (screenshots, features, categories)
│   └── privacy-policy.html           # Bilingual privacy policy (EN/FR toggle)
├── assets/
│   ├── logo.svg                      # Ygar Studio tablet logo (3D purple extrusion)
│   ├── enko-icon.svg                 # Enko Clues app icon (globe with grid lines)
│   └── enko/
│       ├── icon.png                  # App store icon (copied from enko/store/)
│       └── screenshots/1–4.jpg       # Store screenshots (copied from enko/store/)
├── .github/workflows/deploy.yml      # GitHub Pages Actions deploy
├── .nojekyll
├── .gitignore
└── CLAUDE.md
```

## Conventions

- Each app gets its own subfolder (`enko/`, future apps follow the same pattern).
- All pages use **Tailwind CSS CDN** with a shared custom config (colors + font families).
- **Fonts** (Google Fonts): Macondo Swash Caps (studio wordmark "ygar"), Metamorphous (headings), Noto Serif (body), Noto Sans (UI labels).
- **Bilingual** EN/FR everywhere via JS toggle — `lang-hidden` CSS class, `setLang()` function.
- Logo style: `font-script` ("ygar" in Macondo Swash Caps) + small-caps "Studio" label below, matching `ygar_studio_header.svg`.

## Source assets

All original assets live in **`C:\Users\Sesa725153\AndroidStudioProjects\enko`**:

| Asset | Source path |
|---|---|
| Studio logo SVG | `assets/ygar_studio_logo.svg` |
| App icon (Android vector) | `app/src/main/res/drawable/ic_launcher_foreground.xml` |
| Feature graphic SVG | `store/feature_graphic.svg` |
| Studio header SVG | `store/ygar_studio_header.svg` |
| Store screenshots | `store/Screenshot_*.jpg` |
| App description (EN) | `store/description_en.md` |
| App description (FR) | `store/description_fr.md` |
| Colors | `app/src/main/res/values/colors.xml` |

## Design tokens (Tailwind config)

| Token | Value |
|---|---|
| dark | `#050D1F` |
| card | `#0D1330` |
| accent | `#7C3AED` |
| accent-light | `#818CF8` |
| border | `#2D1A4A` |
| border-light | `#3D2A5A` |
| muted | `#9CA3AF` |

## App info

- **Name**: Enko Clues
- **Package**: `com.ygar.app.enko`
- **Publisher**: Ygar Studio 𒅗𒃻
- **Play Store**: `https://play.google.com/store/apps/details?id=com.ygar.app.enko`
- **Contact**: ygar.studio@gmail.com

## Privacy policy

- Lives at `enko/privacy-policy.html`.
- Single page with JS EN/FR language toggle.
- Covers: no data collection, local storage only, optional Google Play Games cloud save, INTERNET permission scope.
- **Both languages must be kept in sync** when updating policy text.
