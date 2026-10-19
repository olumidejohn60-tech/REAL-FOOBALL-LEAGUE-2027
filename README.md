# Pitch Kings - Android build

I could not build the APK for you: the environment I work in cannot reach the Android SDK, Gradle or npm servers.
This folder is a complete project that builds the APK for you, for free, in the cloud.

## Get your APK (about 5 minutes, no coding)
1. Create a free account at github.com and make a new repository (any name).
2. Upload the CONTENTS of this folder to it (drag all files in, including the hidden `.github` folder).
   Easiest: install GitHub Desktop, or use the web "Upload files" page and also create `.github/workflows/build-apk.yml` by pasting its text.
3. Open the repository, go to the **Actions** tab, choose **Build Android APK**, press **Run workflow**.
4. When it finishes (green tick), open the run and download **PitchKings-apk**. Unzip it to get `app-debug.apk`.
5. Copy it to your phone and open it. Android will ask you to allow installs from this source. Accept, then install.

## Build on your own computer instead
Needs Node 18+, Java 17 and Android Studio (for the SDK).
```
npm install
node scripts/prepare.js
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug
```
The APK is in `android/app/build/outputs/apk/debug/`.

## No-install option (works as an app too)
Upload the `www` folder to any static HTTPS host (GitHub Pages, Netlify). Open the link in Chrome on Android,
then menu > **Install app**. It runs fullscreen, offline, with its own icon.

## Notes
- The APK is a debug build (installable, not Play Store ready). A Play Store release needs your own signing key.
- Commentary uses the phone's built-in text-to-speech voices. If you hear nothing, install a speech engine in Android settings.
- All sounds are generated in the game, no audio files are needed.
