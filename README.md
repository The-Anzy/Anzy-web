# theanzy.com

The Anzy's company website: home page, product pages (`/logistrip`, `/swift-rental`, `/app`) and the Anzy app's link files (`.well-known/`).

Plain HTML and CSS, no build step. Edit the files and deploy.

## Hosting

Firebase Hosting in the Google Cloud project **Anzy** (`project-b61cbd93-2976-452c-970`), organization The Anzy.

Deploy (signed in to Firebase as a member of The Anzy):

```bash
npx firebase-tools deploy --only hosting
```

## Files

- `index.html`, `logistrip/`, `swift-rental/`, `app/`: the pages. Header and footer are repeated in each page.
- `assets/style.css`: one stylesheet for all pages (light and dark follow the visitor's device).
- `.well-known/apple-app-site-association`, `.well-known/assetlinks.json`: universal links for the Anzy app (`com.anzy.mobileapp`). Replace `TEAM_ID` with the Apple Team ID before iPhone links can work. `/` is deliberately not listed, so the home page stays a web page.
- `open.html`: shown for app paths (`/post/…`, `/profile`, …) when the app is not installed; one button opens `anzy://…`.
- `firebase.json`: clean URLs, app-path rewrites, the JSON content type for the Apple file, security headers.
