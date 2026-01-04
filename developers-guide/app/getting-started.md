---
icon: play
---

# Getting Started

## 1. Install Flutter
### On windows using vs code (skip 2)
  Install the latest **Stable** version of Flutter by following the official **Flutter + VS Code** setup guide:

  👉 https://docs.flutter.dev/get-started/install/windows

### Using Android SDK
Install the latest Stable version of Flutter

**Recommended:** Use Flutter Version Manager to install Flutter ([https://github.com/leoafarias/fvm](https://github.com/leoafarias/fvm))

## 2. Install the Android SDK

**Recommended** : Use Android Studio to configure the Android SDK and your virtual 
device

1. Install Android Studio
2. In the Settings go to Languages & Frameworks and select Flutter.
3. Select the correct path for Flutter SDK
4. Do the same for the Dart SDK

## 3. Windows Desktop (Required)

Install **Visual Studio Community** (required for Windows builds and Firebase C++ SDK):

👉 https://visualstudio.microsoft.com/downloads/

### During installation, select:

- Desktop development with C++
- MSVC v143 build tools
- Windows 10/11 SDK
- C++ CMake tools for Windows

Restart your PC after installation.

### Verify installation

```bash
cmake --version
where cmake
```

## 4. Run the backend

1. Install docker
2. Clone the [backend repo](https://github.com/atomic-blend/backend)
3. Run `docker compose up -d`

## 5. Configure firebase

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
## 6. Install Rust + Cargo 
Install Rust using [rustup](https://rustup.rs) &#x20;
Verify:&#x20;
```bash
rustup --version
cargo --version
```

## 7. Install flutter_rust_bridge Codegen
Install the Flutter Rust Bridge code generator:
```bash
cargo install flutter_rust_bridge_codegen
```
Verify
```bash
flutter_rust_bridge_codegen --version
```
## 8. Setup Rust for WebAssembly (Flutter Web)
```bash
rustup toolchain install nightly
rustup component add rust-src --toolchain nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
```
Verify: 
```bash
rustup toolchain list
```
## 9. Fork & clone [flutter_age](https://github.com/atomic-blend/flutter_age) and Build WASM

The Flutter Web app depends on Rust code compiled to WebAssembly (WASM).

### navigate to flutter_age repo

```bash
cd flutter_age
```

Build WASM output into the Flutter app

```bash
flutter_rust_bridge_codegen build-web --release \
  -o /ABSOLUTE/PATH/TO/your_app
```
Replace the output path with the absolute path to your local app directory
## 10. Set up the config

1. Copy `assets/configs/config.example.json` to `dev.json`
2. Edit `env` to dev
4. Edit `restApiUrl` with `http://localhost:8080`
4. Change any other settings you might want to

## 11. Install dependencies

```
flutter pub get
```



## 12. Run Codegen

```
flutter pub run build_runner build --delete-conflicting-outputs
```


## 13. Select your device

Launch your virtual Android device or select your physical device in your IDE (using the command palette on Visual Studio Code or in the top menu bar on Android Studio / JetBrains IDE)


## 14. Run the App

To run the app in the dev flavor, ie with the dev configurations we set before : 
```bash
flutter run -d edge \
  -t lib/main_dev.dart \
  --dart-define APP_ENV=dev \
  --dart-define REST_API_URL=http://localhost:8080/ \
   --flavor dev \
  --wasm \
  --web-header=Cross-Origin-Opener-Policy=same-origin \
  --web-header=Cross-Origin-Embedder-Policy=require-corp \
  --web-port 53631
```