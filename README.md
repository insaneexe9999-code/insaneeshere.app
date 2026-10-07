# INSANE SHARE — GitHub APK Build

This project is ready to build an Android APK with **GitHub Actions**.

## Build the APK on GitHub

1. Create a new GitHub repository.
2. Upload **all files and folders inside this ZIP** to the repository root.
   - Do **not** upload only the ZIP file.
   - Make sure `.github/workflows/build-apk.yml` is uploaded.
3. Commit the files to the `main` branch.
4. Open the repository's **Actions** tab.
5. Select **Build INSANE SHARE APK**.
6. Click **Run workflow** (or push to `main` to trigger it automatically).
7. Wait for the build to finish.
8. Open the completed workflow run.
9. Under **Artifacts**, download **INSANE-SHARE-debug-apk**.
10. Extract the downloaded artifact and install `app-debug.apk` on your Android phone.

## What was fixed

- GitHub Actions now explicitly installs and uses **Gradle 8.11.1**, so the workflow does not depend on a missing Gradle wrapper.
- The workflow builds `assembleDebug` and fails clearly if the APK is not produced.
- Android SDK 35 and JDK 17 are configured for the project.

## Important

The current Android app is a WebView wrapper around the HTML file in:

`app/src/main/assets/index.html`

If you want the APK to contain your actual INSANE SHARE website/interface, replace that HTML with your real web app files (including its JavaScript/CSS/assets), or change `MainActivity.kt` to load your hosted HTTPS website.

An internet connection is required for any online/peer-discovery functionality.
