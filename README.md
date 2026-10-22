# XAUUSD S/R Assistant (Android source project)

## What it does
- Android app shell with an offline local interface.
- XAUUSD M5 workflow only.
- User enters current price, nearest support/resistance, optional next lower support/next higher resistance, entry buffer and zone allowance.
- Suggests Buy Stop above resistance and Sell Stop below support.
- Stop-loss is beyond the breakout zone; take-profit is the next entered S/R zone.
- Manual approval only; no broker connection, live feed, automatic chart reading, or automatic order placement.

## Important limitation
With no integrated price source, the app cannot automatically detect live support/resistance. The user must read levels from the broker chart and type them into the app. The current price is also manually entered. This first build is a calculator/workflow tool, not a live scanner.

## Build an APK without owning a PC
This project includes a GitHub Actions workflow that builds a debug APK in the cloud.

1. On your Android tablet, sign in to GitHub or create an account.
2. Create a new **private** repository, for example `xauusd-sr-assistant`.
3. Upload the contents of this ZIP to the repository, keeping the folder structure and hidden `.github` folder. Easiest route: extract the ZIP in a file manager, then upload files/folders in GitHub's web interface. If GitHub's mobile interface makes folder uploads difficult, use GitHub's web interface in your browser with **Desktop site** enabled.
4. Ensure the default branch is named `main`.
5. Open the repository's **Actions** tab. If prompted, enable workflows.
6. Run **Build Android APK** using **Run workflow**, or push a commit to `main`.
7. Open the completed workflow run, find **Artifacts**, and download `XAUUSD-SR-Assistant-debug-apk`.
8. Extract the downloaded artifact ZIP to get `app-debug.apk`.
9. Tap the APK on your Xiaomi tablet. If Android blocks it, allow installation from that specific browser/file-manager app in Settings, install, then turn that permission off again if you prefer.
10. Install only APKs you built from source you trust. This is an unsigned debug APK intended for personal testing, not Play Store release.

## Build requirements
- Android Gradle Plugin 8.7.3
- Gradle 8.9
- JDK 17
- Android SDK platform 35, installed by the cloud build runner as required by the build environment

## Trading cautions
- Levels are user-entered and can be wrong or stale.
- A pending order may trigger during a false breakout or spread widening.
- Confirm candle close and broker stop-distance rules yourself.
- This tool does not calculate position size or guarantee a profitable setup.
