---
icon: play
---

# Getting Started

## Install Flutter&#x20;

Install the latest Stable version of Flutter

**Recommended:** Use Flutter Version Manager to install Flutter ([https://github.com/leoafarias/fvm](https://github.com/leoafarias/fvm))



## Install dependencies

```
flutter pub get
```



## Run Codegen

```
flutter pub run build_runner build --delete-conflicting-outputs
```



## Config env

Copy `assets/configs/config.example.json` to `local.json`

Edit `restApiUrl` with `http://localhost:8080`

## Run the App

For Visual Studio Code, here's a `launch.json` file:

```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "dev (local)",
            "request": "launch",
            "type": "dart",
            "program": "lib/main_dev.dart",
            "toolArgs": [
                "--dart-define", "APP_ENV=local",
                "--dart-define", "REST_API_URL=http://localhost:8080/"
            ],
        },
    ]
}
```



Select a device using the Command Palette, then run the `dev (local)`  config

To launch Atomic Blend on Windows 11: 
1) Install Android Studio (for Frontend)
 2) Install Docker (for Backend)
2.1) Clone backend repo.
2.2) run backend with ```docker compose up -d```
 3) Download Flutter SDK and open up Android Studio's Settings.
 4) In the Settings go to Languages & Frameworks and select Flutter.
 5) Write the correct path for Flutter SDK
 6) Repeat the same thing for Dart SDK.
 7) Install Firebase. (Using standalone Windows application is not recommended, install and use node.js)
 8) Write ```firebase login``` to the terminal inside Android Studio.
 9) Login to your Google Account.
 10) Write ```dart pub global activate flutterfire_cli``` to the terminal inside Android Studio.
11) delete firebase.json file in the main dir.
12) Write ```flutterfire configure``` to the terminal inside Android Studio.
13) create dev.json file under assets/config folder with this config:
```
{
  "env": "beta",
  "debug": true,
  "debugShowCheckedModeBanner": true,
  "debugShowMaterialGrid": true,
  "debugApiClient": true,
  "restApiUrl": "http://localhost:8080/",
  "appleRevenueCatApiKey": "API_KEY",
  "googleRevenueCatApiKey": "API_KEY"
}
```
14) Run this command inside the terminal to launch the app: ```flutter run -t lib/main_dev.dart --dart-define APP_ENV=dev --dart-define REST_API_URL=http://localhost:8080/ --flavor dev``` 

