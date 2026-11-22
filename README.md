# ZOV LOCKER

A minimal native Android app-lock demo targeting Android 10–15 (API 29–35).

## Features
- First launch: create and confirm a 4–8 digit PIN.
- Later launches: enter the PIN to unlock the app screen.
- PIN is stored as a salted PBKDF2-HMAC-SHA256 hash (120,000 iterations).
- Secure-window flag prevents screenshots and screen recording of the app window.
- Immersive full-screen presentation and Back-button suppression while the app is foregrounded.
- No network permission and no external dependencies.

## Important limitations
This is an app-level PIN screen, not a device lock. It cannot prevent Android Home/Recents/system gestures, force-stop, uninstall, recovery, or emergency access. A user can leave the app through Android system controls. It does not replace the Android lock screen.

## Build
Open this folder in Android Studio (Giraffe or newer), allow Gradle sync, then select:
Build > Build Bundle(s) / APK(s) > Build APK(s)

Requirements: JDK 17, Android SDK Platform 35, Android Gradle Plugin 8.7.3.


## Build APK automatically with GitHub Actions (phone only)

1. Create a new repository on GitHub. A public repository is easiest for following these steps; do not upload passwords, signing keys, or private data.
2. Upload the **contents** of this project folder to the repository's `main` branch. The `.github/workflows/android.yml` file must be included.
3. Open the repository's **Actions** tab.
4. Select **Build ZOV LOCKER APK** and tap **Run workflow** (or wait for the first push build to finish).
5. Open the completed run, scroll to **Artifacts**, and download **ZOV-LOCKER-debug**.
6. Extract the downloaded ZIP on your phone. Install the included APK and allow installation from that source if Android asks.

This workflow creates a **debug APK** for testing. It is not a Play Store release build and is not signed with a private release key.
