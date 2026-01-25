# Webify Assets

Centralized static assets (logos, images, branding files) served globally via **jsDelivr CDN**.

This repository is designed to act as a fast, reliable asset host for websites and applications using GitHub + jsDelivr.

---

## 🚀 CDN Base URL (jsDelivr)

jsDelivr allows you to serve files directly from a GitHub repository with global edge caching.

**Base format:**

```

https://cdn.jsdelivr.net/gh/](https://cdn.jsdelivr.net/gh/)<owner>/<repo>@<ref>/<path>

```

Where:
- `<owner>` — GitHub user or organization
- `<repo>` — Repository name
- `<ref>` — Branch, tag, or commit
- `<path>` — File path inside the repository

---

## 📦 Usage Examples

### 1️⃣ Without Versioning (Branch-based)

Use a branch (commonly `main`) when you want assets to update automatically as files change.

```

https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/img.svg

```

**Pros**
- Always serves the latest file
- No need to manage releases

**Cons**
- Aggressively cached
- Changes may take time to propagate globally

---

### 2️⃣ With Versioning (Recommended for Production)

Use a **Git tag or release** for stable and predictable assets.

```

https://cdn.jsdelivr.net/gh/webify-io/webify-assets@v1.0.0/branding/img.svg

```

**Pros**
- Immutable
- Extremely cache-friendly
- Ideal for production environments

**Cons**
- Requires a new tag when updating assets

---

### 3️⃣ Cache Busting (Refreshing Global CDN Cache)

jsDelivr caches files very aggressively.  
If a file changes but keeps the same name, append a **query string** to force a refresh.

```

https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/img-2.svg?v=20251228

````

Common cache-busting strategies:
- Date: `?v=20251228`
- Timestamp: `?v=1735400000`
- Version: `?v=1.0.1`
- Hash: `?v=abc123`

**Why this works**
- Browsers treat the URL as a new resource
- jsDelivr fetches the updated file
- No repo or tag changes required

---

## 🌐 HTML Usage

### Local Image (Relative Path)

```html
<img
  src="images/illustrations/workflow.png"
  alt="Workflow Diagram"
  width="400"
/>
```

### CDN Image via jsDelivr (Branch-based)

```html
<img
  src="https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/walmart.svg"
  alt="Logo"
  class="h-6 w-auto max-w-xs"
/>
```

### CDN Image via jsDelivr (Versioned)

```html
<img
  src="https://cdn.jsdelivr.net/gh/webify-io/webify-assets@v1.0.0/branding/walmart.svg"
  alt="Logo"
  class="h-6 w-auto max-w-xs"
/>
```

### CDN Image with Cache Busting

```html
<img
  src="https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/walmart.svg?v=20251228"
  alt="Logo"
  class="h-6 w-auto max-w-xs"
/>
```

## 🧠 JavaScript Example

```js
const logos = [
  'https://cdn.jsdelivr.net/gh/webify-io/webify-assets@v1.0.0/branding/img.svg',
  'https://cdn.jsdelivr.net/gh/webify-io/webify-assets@main/branding/img-2.svg?v=20251228',
];
````

---

## 🏆 Best Practices

* **Production assets** → Use versioned tags (`@v1.0.0`)
* **Rapid iteration** → Use `@main` with cache-busting query params
* **Never modify tagged releases**
* Prefer **new filenames** or **query strings** when assets change
* Keep asset paths stable and predictable

---

## 📁 Suggested Repository Structure

```
branding/
  ├── img.svg
  ├── img-2.svg
icons/
backgrounds/
```

---

## 🔗 Useful Links

* jsDelivr GitHub CDN Docs: [https://www.jsdelivr.com/github](https://www.jsdelivr.com/github)
* GitHub Releases: [https://docs.github.com/en/repositories/releasing-projects-on-github](https://docs.github.com/en/repositories/releasing-projects-on-github)

---

## ✨ Contribution Guidelines
- Place images in the appropriate folder (logos, screenshots, illustrations).
- Use descriptive filenames (e.g., homepage-dark-mode.png instead of img1.png).
- Optimize images for web (compressed PNG/JPEG, or SVG for vector graphics).
- Avoid including copyrighted material unless you have permission.

## 📜 License
All images in this repository are licensed under [Webify Licence Agreements] unless otherwise stated.
Please check individual folders or files for specific licensing notes.

## 🙌 Acknowledgements
Special thanks to contributors who provide and maintain these assets.
If you use these images, consider giving credit or linking back to this repository.

---

Happy shipping 🚢

