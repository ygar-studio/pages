# Ygar Studio — GitHub Pages

Static GitHub Pages site for **Ygar Studio**, an independent Android game studio.
Published at: `https://<username>.github.io/<repo>/` (configure in repo Settings → Pages → branch `master`, root `/`).

## Project structure

```
teststdy/
├── index.html           # Landing page (studio + Enko Clues)
├── privacy-policy.html  # Bilingual privacy policy (EN / FR, JS toggle)
├── assets/
│   ├── logo.svg         # Ygar Studio tablet logo (3D purple extrusion)
│   └── enko-icon.svg    # Enko Clues app icon (globe with grid lines)
├── .nojekyll            # Disables Jekyll, serves plain HTML
├── .gitignore
└── CLAUDE.md
```

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
| Fonts | `app/src/main/res/font/` |

## Design system

Mirrors the Enko app aesthetic exactly:

| Token | Value |
|---|---|
| bg-dark | `#050D1F` |
| bg-card | `#0D1330` |
| bg-gradient-end | `#1A0D2E` |
| accent | `#7C3AED` |
| accent-light | `#818CF8` |
| text-secondary | `#9CA3AF` |
| border | `#2D1A4A` |

**Fonts** (Google Fonts): Metamorphous (headings), Noto Serif (body/clues), Noto Sans (UI labels).

## App info

- **Name**: Enko Clues
- **Package**: `com.ygar.app.enko`
- **Publisher**: Ygar Studio 𒅗𒃻
- **Play Store**: `https://play.google.com/store/apps/details?id=com.ygar.app.enko`
- **Version**: 1.0.1 (versionCode 2)
- **Languages**: English & French (bilingual)

## GitHub Pages setup

1. Push to `master` (or `main`).
2. Repo Settings → Pages → Source: branch `master`, folder `/` (root).
3. `.nojekyll` is already present — no Jekyll processing, files served as-is.
4. Optional: add a custom domain in Settings → Pages → Custom domain, then create a `CNAME` file at root.

## Privacy policy

- Single page `privacy-policy.html` with JS language toggle (EN/FR).
- Covers: no data collection, local storage only, optional Google Play Games cloud save, INTERNET permission scope.
- Contact: nds.thomas@gmail.com
- Last updated: April 2026.
- **Both languages must be kept in sync** when updating policy text.
