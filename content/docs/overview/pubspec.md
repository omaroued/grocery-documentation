---
title: "Pubspec.yaml"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Project Overview"
weight: 102
toc: true
---

### User App
```
name: grocery
description: A new Flutter project.
publish_to: 'none' # Remove this line if you wish to publish to pub.dev
version: 1.6.0

environment:
  sdk: ">=2.12.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter
  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.2
  # State Management and Streams manipulations
  provider: ^6.0.1
  rxdart: ^0.27.2
  # Local Storage: For dark mode, onBoarding Screen...
  get_storage: ^2.0.3
  #Firebase
  firebase_core: ^1.7.0
  #Firebase Login
  firebase_auth: ^3.1.2
  google_sign_in: ^5.1.1
  flutter_facebook_auth: ^3.4.1
  # Show svg images
  flutter_svg: ^0.22.0
  #Firebase database
  cloud_firestore: ^2.5.3
  #Firebase messaging:  for notifications
  firebase_messaging: ^10.0.8
  #Firebase cloud Functions
  cloud_functions: ^3.0.4
  #Numbers manipulation
  decimal: ^1.3.0
  fluttertoast: ^8.0.8
  country_code_picker : ^2.0.2
  font_awesome_flutter: ^9.1.0
  #Image picker
  file_picker: ^4.1.3
  #Firebase storage
  firebase_storage: ^10.0.4
  #Http plugin for notifications and payment
  http: ^0.13.3
  #Stripe for credit card payment
  flutter_stripe: ^1.3.0
  #Image resizer to reduce upload size
  flutter_native_image: ^0.0.6+1

dev_dependencies:
  flutter_test:
    sdk: flutter
  #Splash Screen
  flutter_native_splash: ^1.2.0
  #Icons
  flutter_launcher_icons: ^0.9.1

flutter_native_splash:
  image: images/logo_splash.png
  color: "#ffffff"
  color_dark: "#404E5A"
  android_disable_fullscreen: true

flutter_icons:
  android: true
  ios: true
  image_path: "images/logo.png"

# The following section is specific to Flutter.
flutter:
  fonts:
    - family: Roboto
      fonts:
        - asset: fonts/RobotoRegular.ttf
        - asset: fonts/RobotoLight.ttf
          weight: 300
        - asset: fonts/RobotoMedium.ttf
          weight: 500
        - asset: fonts/RobotoBold.ttf
          weight: 700
  uses-material-design: true
  assets:
    - images/logo.png
    - images/logo_splash.png
    - images/sign_in/facebook.svg
    - images/sign_in/google.svg
    - images/sign_in/twitter.svg
    - images/state_images/empty_cart.svg
    - images/state_images/error.svg
    - images/state_images/nothing_found.svg
    - images/settings/profile.png
    - images/reminder.svg
    - images/success.svg
    - images/categories/vegetables.png
    - images/on_boarding/1.svg
    - images/on_boarding/2.svg
    - images/on_boarding/3.svg
```


### Admin App
```
name: grocery_admin
description: A new Flutter project.
publish_to: 'none' # Remove this line if you wish to publish to pub.dev
version: 1.6.0

environment:
  sdk: ">=2.12.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter
  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.3
  #Font awesome icons
  font_awesome_flutter: ^9.1.0
  #Flutter Slidable widget
  flutter_slidable: ^0.6.0
  #Firebase
  firebase_core: ^1.3.0
  #Firebase login
  firebase_auth: ^1.4.1
  #Firebase Database
  cloud_firestore: ^2.2.2
  #Firebase storage
  firebase_storage: ^8.1.3
  #Firebase messaging:  for notifications
  firebase_messaging: ^10.0.2
  #Firebase cloud Functions
  cloud_functions: ^3.0.4
  #image picker
  file_picker: ^3.0.2+2
  # State Management and Streams manipulations
  provider: ^5.0.0
  rxdart: ^0.27.1
  # Local Storage: For dark mode
  get_storage: ^2.0.3
  #Show svg images
  flutter_svg: ^0.22.0
  url_launcher: ^6.0.6
  #Flutter toast
  fluttertoast: ^8.0.7
  #Http plugin for notifications and payment
  http: ^0.13.3
  #UIs
  numberpicker: ^2.1.1
  #Image resizer to reduce upload size
  flutter_native_image: ^0.0.6
  #Geocoding plugin to get location from address
  geocoding: ^2.0.0
  #Map launcher plugin to show address in map
  map_launcher: ^2.0.0

dev_dependencies:
  flutter_test:
    sdk: flutter
  #Splash Screen
  flutter_native_splash: ^1.2.0
  #Icons
  flutter_launcher_icons: ^0.9.1

flutter_native_splash:
  image: images/logo_splash.png
  color: "#ffffff"
  color_dark: "#404E5A"
  android_disable_fullscreen: true

flutter_icons:
  android: true
  ios: true
  image_path: "images/logo.png"

flutter:
  assets:
    - images/empty_cart.svg
    - images/error.svg
    - images/nothing_found.svg
    - images/reminder.svg
    - images/success.svg
    - images/category.svg
    - images/delivery_boy.svg
    - images/no_delivery_found.svg
    - images/map.svg
    - images/logo.png
    - images/logo_splash.png
    - images/upload_image.png
    - images/stripe.png
    - images/profile.png
```

### Delivery Boy App

```
name: delivery
description: A new Flutter project.
publish_to: 'none' # Remove this line if you wish to publish to pub.dev
version: 1.6.0

environment:
  sdk: ">=2.12.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter
  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.3
  #Firebase
  firebase_core: ^1.3.0
  #Firebase login
  firebase_auth: ^1.4.1
  #Firebase Database
  cloud_firestore: ^2.2.2
  #Firebase storage
  firebase_storage: ^8.1.3
  #Firebase messaging:  for notifications
  firebase_messaging: ^10.0.2
  #Firebase cloud Functions
  cloud_functions: ^3.0.4
  # State Management and Streams manipulations
  provider: ^5.0.0
  rxdart: ^0.27.1
  # Local Storage: For dark mode
  get_storage: ^2.0.3
  #Show svg images
  flutter_svg: ^0.22.0
  url_launcher: ^6.0.6
  #Flutter toast
  fluttertoast: ^8.0.7
  #image picker
  file_picker: ^3.0.2+2
  #Http plugin for notifications
  http: ^0.13.3
  #Image resizer to reduce upload size
  flutter_native_image: ^0.0.6
  #Geocoding plugin to get location from address
  geocoding: ^2.0.0
  #Map launcher plugin to show address in map
  map_launcher: ^2.0.0

dev_dependencies:
  flutter_test:
    sdk: flutter
  #Splash Screen
  flutter_native_splash: ^1.2.0
  #Icons
  flutter_launcher_icons: ^0.9.1

flutter_native_splash:
  image: images/logo_splash.png
  color: "#ffffff"
  color_dark: "#404E5A"
  android_disable_fullscreen: true

flutter_icons:
  android: true
  ios: true
  image_path: "images/logo.png"

flutter:
  uses-material-design: true
  assets:
    - images/empty_cart.svg
    - images/error.svg
    - images/nothing_found.svg
    - images/reminder.svg
    - images/success.svg
    - images/map.svg
    - images/logo.png
    - images/logo_splash.png
    - images/upload_image.png
    - images/profile.png
```
