# Face Quest – build instructions

## Android APK (no Android Studio needed)
1. Create a free GitHub account and a new empty repository.
2. Upload everything in this folder (keep the .github folder).
3. Open the repo > Actions > "Build Android APK" > Run workflow.
4. After ~5 minutes download the artifact "face-quest-apk" and unzip it.
5. Copy app-debug.apk to the phone/tablet, open it, allow "Install unknown apps".

## Android (on your own computer)
npm install
npx cap add android
(add <uses-permission android:name="android.permission.CAMERA"/> to android/app/src/main/AndroidManifest.xml)
npx cap sync android
npx cap open android      # Android Studio > Build > Build APK(s)

## iPhone / iPad (needs a Mac with Xcode)
npm install
npx cap add ios
In ios/App/App/Info.plist add:
  NSCameraUsageDescription = "Take a photo for your hero"
  NSPhotoLibraryUsageDescription = "Choose a photo for your hero"
npx cap sync ios
npx cap open ios          # Xcode > select your team > Run on device
A free Apple ID installs for 7 days; TestFlight / App Store needs the $99/year Apple Developer account.
