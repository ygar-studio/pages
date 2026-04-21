# Ygar Studio — GitHub Pages

Static GitHub Pages site for **Ygar Studio**, an independent Android game studio.

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

Shared config — Enko accent colors. Studio home uses gold overrides via inline styles.

| Token | Value | Usage |
|---|---|---|
| dark | `#050D1F` | Page background |
| card | `#0D1330` | Card background |
| accent | `#7C3AED` | Enko purple (buttons, borders) |
| accent-light | `#818CF8` | Enko purple light (labels) |
| border | `#2D1A4A` | Card/section borders |
| border-light | `#3D2A5A` | Hover borders |
| muted | `#9CA3AF` | Secondary text |

Studio home gold overrides (inline styles):
- Gold accent: `#D4A947`
- Hero glow: `rgba(185,132,12,0.14)`

Studio logo (`assets/logo.svg`): gold extrusion `#1A1200` → `#916E00`, white front face.

## Typography
- **Studio logo**: Macondo Swash Caps (Google Font) — must be used for 'ygar' in studio logo.
- **Titles**: Metamorphous (Google Font)
- **Body / UI text**: Noto Sans (Google Font) — clean, readable sans-serif with broad Unicode support

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
