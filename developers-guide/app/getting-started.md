---
icon: play
---

# Getting Started

## 1. Install Flutter

Install the latest Stable version of Flutter

**Recommended:** Use Flutter Version Manager to install Flutter ([https://github.com/leoafarias/fvm](https://github.com/leoafarias/fvm))

## 2. Install the Android SDK

**Recommended** : Use Android Studio to configure the Android SDK and your virtual device

1. Install Android Studio
2. In the Settings go to Languages & Frameworks and select Flutter.
3. Select the correct path for Flutter SDK
4. Do the same for the Dart SDK

## 3. Run the backend

1. Install docker
2. Clone the [backend repo](https://github.com/atomic-blend/backend)
3. Run `docker compose up -d`

## 4. Configure firebase

1. Install the Firebase CLI
2. Run `firebase login` to log in Firebase on your PC
3. Log in your Google Account
4. Create a new firebase project
5. Install `flutterfire` with `dart pub global activate flutterfire_cli`
6. Delete the `firebase.json` file at the app root directory
7. Run this command to configure firebase for the dev flavor : 
```
flutterfire configure \
  --project=<FIREBASE_PROJECT_NAME> \ 
  --out=lib/firebase_options_dev.dart \ 
  --ios-bundle-id=fr.atomicblend.app-dev \
  --android-package-name=fr.atomicblend.appdev \
  --ios-out=ios/config/dev \ 
  --android-out=android/app/src/dev \ 
  --macos-out=macos/config/dev
```

## 5. Set up the config

1. Copy `assets/configs/config.example.json` to `dev.json`
2. Edit `env` to dev
4. Edit `restApiUrl` with `http://localhost:8080`
4. Change any other settings you might want to

## 6. Install dependencies

```
flutter pub get
```



## 7. Run Codegen

```
flutter pub run build_runner build --delete-conflicting-outputs
```


## 8. Select your device

Launch your virtual Android device or select your physical device in your IDE (using the command palette on Visual Studio Code or in the top menu bar on Android Studio / JetBrains IDE)


## 9. Run the App

To run the app in the dev flavor, ie with the dev configurations we set before : 
```bash
flutter run -t lib/main_dev.dart --dart-define APP_ENV=dev --dart-define REST_API_URL=http://localhost:8080/ --flavor dev
```