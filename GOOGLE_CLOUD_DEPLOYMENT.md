# VYTAL AIR — Google Cloud and Google Sites Deployment

## Target infrastructure

- Google Cloud / Firebase project: `vytal-house`
- GitHub repository: `ACoolNerd/VYTALAir`
- Firebase Hosting configuration: `firebase.json`
- Firebase project mapping: `.firebaserc`
- Automated deployment: `.github/workflows/firebase-hosting.yml`

## Current external blocker

The latest available Google Cloud billing notice stated that the billing account connected to project `vytal-house` was past due or did not have valid payment information. Resolve billing before depending on Firebase Hosting for a public production launch.

## One-time Google Cloud setup

1. Open Google Cloud Console and select project `vytal-house`.
2. Confirm the billing account is active and valid.
3. Open Firebase Console and select or add the existing Google Cloud project `vytal-house`.
4. Enable Firebase Hosting.
5. In Firebase project settings, open **Service accounts**.
6. Generate a new private key for a deployment-only service account with the minimum Firebase Hosting permissions required.
7. Do not commit the JSON key to this repository.

## GitHub secret

In the GitHub repository, open:

**Settings → Secrets and variables → Actions → New repository secret**

Create:

`FIREBASE_SERVICE_ACCOUNT_VYTAL_HOUSE`

Paste the full service-account JSON into the secret value.

After the secret is present, every push to `main` triggers the Firebase Hosting deployment workflow.

## Expected Firebase URLs

The default Firebase Hosting domains normally follow these patterns after Hosting is initialized:

- `https://vytal-house.web.app`
- `https://vytal-house.firebaseapp.com`

Confirm the actual assigned site ID in Firebase Console because an existing project can use a different Hosting site name.

## Local deployment option

Install Node.js and Firebase CLI, then run:

```bash
npm install -g firebase-tools
firebase login
firebase use vytal-house
firebase deploy --only hosting
```

## Google Sites implementation

Google Sites does not import this custom HTML/CSS/JavaScript website as a native Google Sites theme. Use Google Sites as the institutional wrapper and embed the deployed Firebase or GitHub Pages website.

1. Create or open the VYTAL AIR Google Site.
2. Choose **Insert → Embed → By URL**.
3. Paste the Firebase Hosting URL.
4. Use a full-width embed and increase the height so the interactive site is visible.
5. Add native Google Sites navigation only when needed:
   - Home
   - Product System
   - Science
   - Physician Review
   - Development Pathway
   - Media
   - Partnerships

## Claims and privacy controls

- Keep development-stage, FDA, patent-status, and physician-review disclaimers visible.
- Do not use Google Forms or a public form to collect protected health information.
- Do not commit service-account keys, API keys with excessive privileges, patient information, confidential invention disclosures, or regulatory records to this public repository.
- Public inquiry forms should collect only ordinary business-contact information and should warn users not to submit confidential technical information.
