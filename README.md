# Focus Garden: website + Android APK built by GitHub

Everything in this folder goes into ONE GitHub repository. GitHub then hosts the website
(GitHub Pages) and builds the Android APK for you (GitHub Actions). No Android tools needed.

## Before uploading
1. Do the Firebase setup (see firestore.rules and the earlier instructions) and paste your
   Firebase config into the FB block near the top of index.html.

## Upload
1. On a computer, go to github.com > New repository.
2. Name it YOUR-USERNAME.github.io (lowercase, exactly). Public. Create.
3. Click "uploading an existing file". Drag in EVERYTHING from this folder, including the
   hidden items: .github, .well-known, .nojekyll.
   (Mac: press Cmd+Shift+. in Finder to show hidden files. Windows: they show normally.)
   If a hidden item won't upload, add it with Add file > Create new file: type the path
   (for example .github/workflows/build-apk.yml), paste the contents, and commit.
4. Commit changes.

## Turn on the website
Settings > Pages > Deploy from a branch > main, / (root) > Save.
Then Firebase > Authentication > Settings > Authorized domains > add YOUR-USERNAME.github.io

## Get the APK
1. Open the Actions tab. If asked, click "I understand my workflows, go ahead and enable them".
2. The "Build Android APK" workflow starts by itself after your upload (about 5 to 10 minutes).
   You can also run it by hand: Actions > Build Android APK > Run workflow.
3. When it turns green, open the Releases section on the repo home page.
4. Download link for everyone:
   https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io/releases/latest/download/focus-garden.apk

## Install on Android
Open the link, tap the downloaded file, allow "Install unknown apps" if asked, tap Install.

## Updates
Edit any file on GitHub and commit. The APK rebuilds automatically with a higher version number,
and installs over the old one. The app shows your live website, so most changes need no reinstall.

## Notes
- The signing key (android/app/release.keystore) is included so updates install over old versions.
  Because the repo is public, do not use this key for the Play Store.
- If the build fails, open the failed run in Actions and send the red error text to Claude.
- If the app shows a thin address bar, wait a few minutes after the first Pages deploy, then reinstall.
  The file .well-known/assetlinks.json removes it.
