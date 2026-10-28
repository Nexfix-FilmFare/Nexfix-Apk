# Nexfix APK

Official release repository for the **Nexfix** streaming app (Android).

---

## App Details

| Field | Value |
|---|---|
| App Name | Nexfix |
| Package / Serial | `com.example.nexfix` |
| Version | **1.0.1** (versionCode 101) |
| Platform | Android (iOS planned) |
| Min SDK | 25 (Android 7.1) |
| Target SDK | 35 (Android 15) |
| Build | Flutter / Dart |
| APK Size | ~194 MB (universal release) |
| Architecture | arm64-v8a + armeabi-v7a (universal) |
| License | Proprietary — unauthorized distribution not permitted |

---

## Download

Latest signed release: **[Nexfix v1.0.1 — app-release.apk](https://github.com/Nexfix-FilmFare/Nexfix-Apk/releases/download/v1.0.1/app-release.apk)**

All releases: **[Releases](https://github.com/Nexfix-FilmFare/Nexfix-Apk/releases/latest)** page.

- Download `app-release.apk`
- Install on your device (enable *Install unknown apps* for your browser/file manager if prompted)
- Launch **Nexfix**

---

## Version Detail

### v1.0.1 (versionCode 101) — latest

- Stability: global crash guards — uncaught player/stream errors no longer kill the app
- Playback: fixed movie server list staying empty (stream API failure now falls back to the legacy route)
- Playback: mpv byte-level stream cache enabled — smoother playback, no mid-scene stutters
- Failsafe: automatic server failover on expired/broken links

### v1.0.0 (versionCode 100)

- Initial public release

---

## Publishing a Release

### Android (APK)

```bash
flutter clean
flutter pub get
flutter build apk --release
```

The output lands at `build/app/outputs/flutter-apk/app-release.apk`. Publish it with GitHub CLI:

```bash
gh release create v<VERSION> \
  --title "Nexfix v<VERSION>" \
  --notes "Release notes here" \
  build/app/outputs/flutter-apk/app-release.apk
```

### iOS (IPA)

iOS builds require macOS with Xcode 15+:

```bash
flutter build ipa --release
```

Upload the exported `.ipa` to **App Store Connect** via Xcode or `xcrun altool`, then distribute through **TestFlight / App Store**. GitHub Releases can also carry the `.ipa` the same way as the APK.

---

## Requirements

- Android 7.1 or newer
- Stable internet connection
- ~300 MB free storage (install + cache)
