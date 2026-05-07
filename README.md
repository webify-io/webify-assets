[![Maintained by Webify](https://img.shields.io/badge/Maintained%20by-Webify®-blue)](https://www.webify.org.za)

# webify-assets

> Centralised static assets for all Webify projects — served globally via jsDelivr CDN.

---

## Folder Structure

```
webify-assets/
├── webify-branding/    ← Webify org logos, favicons, and site.webmanifest
├── mockups/            ← Client project mockup screenshots
├── branding/           ← Client logos and brand SVGs
├── branding-gray/      ← Grayscale trusted-brand logos (for marquees etc.)
├── backgrounds/        ← Full-page background and hero images
├── placeholders/       ← Placeholder UI images for dev/staging
├── gif/                ← Animated GIFs
└── images/             ← General-use images
```

### Folder Reference

| Folder | What Goes Here |
|---|---|
| `webify-branding/` | Webify org assets — `logo.png`, `logo-white.png`, favicons, `site.webmanifest` |
| `mockups/` | Client site mockups — named `mockup_<client>.png` |
| `branding/` | Client SVG logos and brand marks (prefer SVG) |
| `branding-gray/` | Grayscale versions of well-known logos for trust sections |
| `backgrounds/` | Large background/hero images — max 1920px wide |
| `placeholders/` | Placeholder images for wireframes and staging |
| `gif/` | Animated GIF files |
| `images/` | Everything else — photos, illustrations, screenshots |

---

## File Naming

Use lowercase, hyphenated, descriptive names:

```
✅ mockup_cosmeri_homepage.png
✅ logo-acme-corp.svg
✅ hero-background-dark.jpg
❌ img1.png
❌ Screenshot 2025-01-01.png
❌ LOGO_FINAL_v3.PNG
```

---

## CDN Usage

**Base URL:**
```
https://cdn.jsdelivr.net/gh/webify-io/webify-assets@<ref>/<folder>/<file>
```

### Branch-based (development)
```
https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/logo.svg
```

### Versioned tag (production — recommended)
```
https://cdn.jsdelivr.net/gh/webify-io/webify-assets@v1.0.0/branding/logo.svg
```

### Cache busting (when a file changes name but stays on `@main`)
```
https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/logo.svg?v=20250101
```

**Creating a release tag:**
```bash
git tag v1.1.0
git push origin v1.1.0
```

---

## Quick Examples

**HTML**
```html
<img src="https://cdn.jsdelivr.net/gh/webify-io/webify-assets@v1.0.0/branding/logo.svg" alt="Logo" />
```

**React / JSX**
```jsx
const CDN = 'https://cdn.jsdelivr.net/gh/webify-io/webify-assets@v1.0.0';
<img src={`${CDN}/mockups/mockup_cosmeri.png`} alt="Cosmeri preview" />
```

**Markdown**
```markdown
![Preview](https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/mockups/mockup_cosmeri.png)
```

---

## Image Compression — Before You Upload

Always compress before pushing. Target sizes:

| Format | Use Case | Target |
|---|---|---|
| `.webp` | Photos, mockups, screenshots | < 150 KB |
| `.jpg` | Photos (fallback) | < 200 KB |
| `.png` | Logos with transparency | < 100 KB |
| `.svg` | Icons, logos, illustrations | < 30 KB |
| `.gif` | Short animations | < 500 KB |

Recommended tools: [Squoosh](https://squoosh.app) · [TinyPNG](https://tinypng.com) · [SVGOMG](https://jakearchibald.github.io/svgomg/)

---

## Best Practices

| Rule | Reason |
|---|---|
| Use `.webp` for photos/mockups | 25–35% smaller than JPEG/PNG |
| Use `.svg` for logos/icons | Infinite scale, tiny file |
| Use versioned tags in production | Immutable, reliable caching |
| Use `@main` + cache-bust in dev | Fast iteration without tag management |
| Never modify a tagged release | Breaks cache immutability |
| One canonical location per file | Don't duplicate across folders |

---

## Useful Links

- jsDelivr CDN docs: [jsdelivr.com/github](https://www.jsdelivr.com/github)
- GitHub Releases docs: [docs.github.com](https://docs.github.com/en/repositories/releasing-projects-on-github)

---

*Part of the [webify-io](https://github.com/webify-io) organisation*
