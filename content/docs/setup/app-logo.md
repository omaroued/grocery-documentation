---
title: "App logo"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 101
toc: true
---


Go to images folder and replace `logo.png` with your logo (keep the same
name).
### Android
Go to `android/app/src/main/minmap` and replace
`ic_launcher.png` with your logo (keep same image name)
### iOS
Go to `ios/Runner/Assets.xcassets/AppIcon.appiconset`
and replace the images with yours.
Important: Don’t forget to run flutter clean after these steps.


### Splash Screen
1. Go to images folder and replace `logo_splash.png` with your logo (keep the same
name and the **recommended** image resolution is 300px*300px).

2. Go to `flutter_native_splash.yaml` and replace the background colors (default and dark mode) with yours:

![image alt text](/images/splash_screen.jpg)

3. For every logo or background change you have to run the following command:
```
flutter pub run flutter_native_splash:create
```
