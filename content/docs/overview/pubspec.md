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

## User App
```
name: grocery
description: A new Flutter project.
publish_to: 'none'
version: 1.4.0

environment:
  sdk: ">=2.7.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter

  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.2
  #Splash Screen
  flutter_native_splash: ^0.2.7
  # State Management and Streams manipulations
  provider: ^5.0.0
  rxdart: ^0.26.0
  # Local Storage: For dark mode, onBoarding Screen...
  shared_preferences: ^2.0.5
  #Firebase
  firebase_core: ^1.0.3
  #Firebase Login
  firebase_auth: ^1.0.2
  google_sign_in: ^5.0.1
  flutter_facebook_login: ^3.0.0
  # Show svg images
  flutter_svg: ^0.19.3
  #Firebase database
  cloud_firestore: ^1.0.4
  #Firebase messaging:  for notifications
  firebase_messaging: ^9.1.1
  #Numbers manipulation
  decimal: ^1.0.0+1
  #UIs
  circular_check_box: ^1.0.4
  fluttertoast: ^8.0.3
  flutter_country_picker: ^0.1.6
  font_awesome_flutter: ^9.0.0
  #Image picker
  file_picker: ^3.0.1
  #Firebase storage
  firebase_storage: ^8.0.2
  #Notification
  flutter_local_notifications: ^5.0.0+1
  #Http plugin for notifications and payment
  http: ^0.13.1
  #Stripe for credit card payment
  stripe_payment: ^1.0.11
  #Image resizer to reduce upload size
  flutter_native_image: ^0.0.6

dev_dependencies:
  flutter_test:
    sdk: flutter

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


## Admin App
```
name: grocery_admin
description: A new Flutter project.
publish_to: 'none'
version: 1.4.0

environment:
  sdk: ">=2.7.0 <3.0.0"
dependencies:
  flutter:
    sdk: flutter

  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.2
  #Font awesome icons
  font_awesome_flutter: ^9.0.0
  #Splash Screen
  flutter_native_splash: ^1.1.7+1
  #Flutter Slidable widget
  flutter_slidable: ^0.6.0
  #Firebase
  firebase_core: ^1.0.3
  #Firebase login
  firebase_auth: ^1.0.2
  #Firebase Database
  cloud_firestore: ^1.0.4
  #Firebase storage
  firebase_storage: ^8.0.2
  #Firebase messaging:  for notifications
  firebase_messaging: ^9.1.4
  #image picker
  file_picker: ^3.0.1
  # State Management and Streams manipulations
  provider: ^5.0.0
  rxdart: ^0.26.0
  # Local Storage: For dark mode
  shared_preferences: ^2.0.5
  #Show svg images
  flutter_svg: ^0.21.0+1
  #Notification
  flutter_local_notifications: ^5.0.0+1
  url_launcher: ^6.0.3
  #Flutter toast
  fluttertoast: ^8.0.3
  #Http plugin for notifications and payment
  http: ^0.13.1
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

flutter:
  uses-material-design: true
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

## Delivery Boy App

```
name: delivery
description: A new Flutter project.
publish_to: 'none'
version: 1.4.0

environment:
  sdk: ">=2.7.0 <3.0.0"
dependencies:
  flutter:
    sdk: flutter

  # The following adds the Cupertino Icons font to your application.
  # Use with the CupertinoIcons class for iOS style icons.
  cupertino_icons: ^1.0.2
  #Splash Screen
  flutter_native_splash: ^1.1.8+4
  #Firebase
  firebase_core: ^1.0.3
  #Firebase login
  firebase_auth: ^1.0.2
  #Firebase Database
  cloud_firestore: ^1.0.4
  #Firebase storage
  firebase_storage: ^8.0.2
  #Firebase messaging:  for notifications
  firebase_messaging: ^9.1.1
  # State Management and Streams manipulations
  provider: ^5.0.0
  rxdart: ^0.26.0
  # Local Storage: For dark mode
  shared_preferences: ^2.0.5
  #Show svg images
  flutter_svg: ^0.21.0+1
  #Notification
  flutter_local_notifications: ^5.0.0+1
  url_launcher: ^6.0.3
  #Flutter toast
  fluttertoast: ^8.0.3
  #image picker
  file_picker: ^3.0.1
  #Http plugin for notifications
  http: ^0.13.1
  #Image resizer to reduce upload size
  flutter_native_image: ^0.0.6
  #Geocoding plugin to get location from address
  geocoding: ^2.0.0
  #Map launcher plugin to show address in map
  map_launcher: ^2.0.0

dev_dependencies:
  flutter_test:
    sdk: flutter

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
