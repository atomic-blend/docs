---
icon: play
---

# Getting Started

## 1. Install Flutter

### Using VS Code on Windows

If you use VS Code on Windows, this setup already includes the Android SDK.
You can skip section 2.

Install the latest **stable** version of Flutter by following the official **Flutter + VS Code** setup guide:

👉 https://docs.flutter.dev/get-started/install/windows


### Using Android SDK

Install the latest stable version of Flutter

**Recommended:** Use Flutter Version Manager to install Flutter ([https://github.com/leoafarias/fvm](https://github.com/leoafarias/fvm))

## 2. Install the Android SDK

**Recommended** : Use Android Studio to configure the Android SDK and your virtual device

1. Install Android Studio
2. In the Settings go to Languages & Frameworks and select Flutter.
3. Select the correct path for Flutter SDK
4. Do the same for the Dart SDK

## 3. Platform Specific configuration

### 3.1. Windows

Install **Visual Studio Community** (required for Windows builds and Firebase C++ SDK):

👉 https://visualstudio.microsoft.com/downloads/

During installation, select:

- Desktop development with C++
- MSVC v143 build tools
- Windows 10/11 SDK
- C++ CMake tools for Windows

Restart your PC after installation.

Verify installation:
```bash
cmake --version
where cmake
```

### 3.2. Web

#### 3.2.1. Install Rust + Cargo 

Install Rust using [rustup](https://rustup.rs)
Verify:
```bash
rustup --version
cargo --version
```

#### 3.2.2. Install flutter_rust_bridge Codegen

Install the Flutter Rust Bridge code generator:
```bash
cargo install flutter_rust_bridge_codegen
```

Verify:
```bash
flutter_rust_bridge_codegen --version
```

#### 3.2.3. Setup Rust for WebAssembly (Flutter Web)

```bash
rustup toolchain install nightly
rustup component add rust-src --toolchain nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
```
Verify: 
```bash
rustup toolchain list
```

#### 3.2.4. Fork & clone [flutter_age](https://github.com/atomic-blend/flutter_age), then build WASM

Fork the repository to your GitHub account, then clone it locally:
```bash
git clone https://github.com/<your-github-username>/flutter_age.git
cd flutter_age
```

Build WASM output into the Flutter app
```bash
flutter_rust_bridge_codegen build-web --release \
  -o /ABSOLUTE/PATH/TO/your_app
```
Replace the output path with the absolute path to your local app directory

## 4. Run the backend

Before running the frontend, make sure the backend is up and running.

👉 Follow the backend setup instructions here:  
[Backend setup guide](https://atomic-blend.gitbook.io/docs/developers/backend/getting-started)

## 5. Configure Firebase

1. Install the Firebase CLI
2. Run `firebase login` to log in Firebase on your PC
3. Log in your Google Account
4. Create a new firebase project
5. Install `flutterfire` with `dart pub global activate flutterfire_cli`
6. Delete the `firebase.json` file at the app root directory
7. Run this command to configure Firebase for the dev flavor : 
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

## 6. Set up the config

1. Copy `assets/configs/config.example.json` to `dev.json`
2. Edit `env` to dev
3. Edit `restApiUrl` with `http://localhost:8080`
4. Change any other settings you might want to

## 7. Install dependencies

```
flutter pub get
```



## 8. Run Codegen

```
flutter pub run build_runner build --delete-conflicting-outputs
```


## 9. Select your device

Launch your virtual Android device or select your physical device in your IDE (using the command palette on Visual Studio Code or in the top menu bar on Android Studio / JetBrains IDE)


## 10. Run the App

To run the app in the dev flavor, ie with the dev configurations we set before : 
```bash
flutter run
  -t lib/main_dev.dart \
  --dart-define APP_ENV=dev \
  --dart-define REST_API_URL=http://localhost:8080/ \
   --flavor dev \
  --wasm \
  --web-header=Cross-Origin-Opener-Policy=same-origin \
  --web-header=Cross-Origin-Embedder-Policy=require-corp \
  --web-port 53631
```