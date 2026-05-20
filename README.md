# DeHydration — GitHub Pages

Premium marketing and legal pages for **DeHydration** (App Store, support, and compliance URLs).

## Files

| File | App Store / purpose |
|------|---------------------|
| `index.html` | **Marketing URL** — product landing page |
| `privacy.html` | **Privacy Policy URL** |
| `terms.html` | **Terms of Use (EULA) URL** |
| `T&C.html` | Redirect to `terms.html` (legacy link compatibility) |
| `support.html` | **Support URL** |
| `css/site.css` | Shared styles |

## Deploy to GitHub Pages

### Option A — Use this `docs/` folder (recommended)

1. Create a GitHub repository (e.g. `dehydration-app-legal`).
2. Copy the entire `docs/` folder contents into the repo root **or** keep the `docs/` folder at the repo root.
3. On GitHub: **Settings → Pages → Build and deployment**
   - **Source:** Deploy from a branch
   - **Branch:** `main` → **`/docs`** (if you kept the folder name `docs`)
   - Or use **`/ (root)`** if you copied files to the repository root.
4. Save. Your site will be live at:

   `https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/`

### Option B — Root of repo

Copy all files from `docs/` (including `css/`) into the repository root and set Pages to **`/ (root)`**.

## App Store Connect URLs

After publishing, use these in App Store Connect (replace placeholders):

| Field | URL |
|-------|-----|
| **Privacy Policy** | `https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/privacy.html` |
| **Terms of Use (EULA)** | `https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/terms.html` |
| **Marketing URL** | `https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/` |
| **Support URL** | `https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/support.html` |

## Update the iOS app links

In `IAP/FreeTrialView.swift`, point Terms and Privacy to your GitHub Pages URLs:

```swift
private let termsURL = "https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/terms.html"
private let privacyURL = "https://<GITHUB_USERNAME>.github.io/<REPO_NAME>/privacy.html"
```

## Customize before publishing

1. **App Store link** — In `index.html`, replace `https://apps.apple.com/app/id0000000000` with your real App Store URL.
2. **Email addresses** — Search for `@terafort.com` and set your real support/privacy emails.
3. **Company name** — Update "Terafort" in footers and legal text if needed.
4. **Governing law** — In `terms.html`, specify your country/state if required.

## Local preview

```bash
cd docs
python3 -m http.server 8080
```

Open `http://localhost:8080`
