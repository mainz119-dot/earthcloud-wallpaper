# 천리안 2A 구름 라이브 배경화면

Android Studio starter project. This revision adds an image-import screen and a real satellite-image live wallpaper renderer.

## Current functionality
- Select one or multiple GK2A CLD PNG files from Android's file picker.
- Copy selected images into the app's private `cloud_frames` folder.
- Play imported images in filename order as a looping satellite animation (1.2 seconds per frame).
- Set the wallpaper from the app.
- Images are center-cropped to fill the wallpaper; originals remain in app-private storage.

## Use on the phone
1. Build and install the APK.
2. Open **천리안 구름 배경화면**.
3. Tap **CLD 위성영상 PNG 가져오기** and select multiple downloaded `gk2a_ami_le2_cld_...png` files. Select a sequence of timestamps for smooth motion.
4. Tap **라이브 배경화면 설정** and apply to the home screen.

## Important limitations in this revision
- This version plays CLD PNG files that the user imports. It does not yet fetch new frames automatically from KMA API Hub.
- The KMA API key must not be embedded in a public APK. Automatic refresh should be added through a secure proxy/backend or a carefully protected private configuration.
- The wallpaper uses a simple image sequence; it does not yet display Dongtan temperature/air-quality data.

## Build
Open the project folder in Android Studio, sync Gradle, then Build > Build APK(s).

## GitHub Actions로 APK 빌드
`main`에 push하거나 Actions 탭에서 **Build APK → Run workflow**를 실행하면, 완료 후 Artifacts의 `EarthCloudWallpaper-debug-apk`에서 APK를 받을 수 있습니다. (debug 서명 APK라 바로 설치 가능)
