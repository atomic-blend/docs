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
