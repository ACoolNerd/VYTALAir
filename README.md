# VYTAL AIR

Official public development website and 16:9 social-media asset system for **VYTAL AIR**, a proposed VYTAL House capsule-based dry-powder inhalation development platform.

## Status

- Development-stage planning program
- Not FDA approved or cleared
- Patent status must be independently confirmed
- No clinical benefit, safety, bioavailability, or commercialization claim is made

## Brand

- Master brand: VYTAL House
- Product: VYTAL AIR
- Positioning line: **Renew • Restore • Recharge**
- Operating principle: **Rights • Disclosure • Proof**

## Website stack

```text
.
├── index.html
├── styles.css
├── script.js
├── assets.js
├── GOOGLE_SITES.md
├── .nojekyll
└── .github/workflows/pages.yml
```

The production repository uses a static HTML/CSS/JavaScript stack with no build dependency.

## Open locally

```bash
python3 -m http.server 8080
```

Open `http://localhost:8080`.

## GitHub Pages

The included workflow deploys the static website through GitHub Pages. In repository settings, select:

**Pages → Build and deployment → GitHub Actions**

Expected URL after successful deployment:

`https://acoolnerd.github.io/VYTALAir/`

## Google Sites

Google Sites does not import a complete custom HTML/CSS/JavaScript website as a native theme. Use the GitHub Pages site as the interactive source, then embed it in Google Sites using:

**Insert → Embed → By URL**

See `GOOGLE_SITES.md` for the complete integration approach.

## Controlled communication rule

Do not publish language stating that VYTAL AIR is patented, patent pending, FDA approved, FDA cleared, clinically proven, bioavailable, safe, effective, or commercially available unless the statement is supported by current documentary evidence and approved for public use.