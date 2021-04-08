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
publish_to: 'none' # Remove this line if you wish to
version: 1.0.1
environment:
 sdk: ">=2.7.0 <3.0.0"
dependencies:
 flutter:
 sdk: flutter
 cupertino_icons: ^0.1.3
 # State Management and Streams manipulations
 provider: ^4.3.2+2
 rxdart: ^0.25.0
 # Local Storage: For dark mode, onBoarding Screen...
 shared_preferences: ^0.5.12+4 #Firebase
 firebase_core: ^0.5.0
 #Firebase Login
 firebase_auth: ^0.18.0+1
 google_sign_in: ^4.5.4
 flutter_facebook_login: ^3.0.0
 # Show svg images
 flutter_svg: ^0.19.0
 #Firebase database
 cloud_firestore: ^0.14.1+2
 #Firebase messaging: for notifications
 firebase_messaging: ^7.0.3
 #Numbers manipulation
 decimal: ^0.3.5
 #UIs
 circular_check_box: ^1.0.4
 fluttertoast: ^7.1.6
 flutter_country_picker: ^0.1.6
 font_awesome_flutter: ^8.11.0
 #Image picker
 file_picker: ^2.1.1
 #Firebase storage
 firebase_storage: ^5.2.0
 #Notification
 flutter_local_notifications: ^4.0.0
 #Http plugin for notifications and payment
 http: ^0.12.2
 #Stripe for credit card payment
 stripe_payment: ^1.0.10
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
 - images/sign_in/facebook.svg - images/sign_in/google.svg
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
# The following line prevents the package from being
accidentally published to
# pub.dev using `pub publish`. This is preferred for
private packages.
publish_to: 'none' # Remove this line if you wish to
publish to pub.dev
# The following defines the version and build number
for your application.
# A version number is three numbers separated by dots,
like 1.2.43
# followed by an optional build number separated by a
+.
# Both the version and the builder number may be
overridden in flutter
# build by specifying --build-name and --build-number,
respectively.
# In Android, build-name is used as versionName while
build-number used as versionCode.
# Read more about Android versioning at
https://developer.android.com/studio/publish/versioning
# In iOS, build-name is used as
CFBundleShortVersionString while build-number used as
CFBundleVersion.
# Read more about iOS versioning at
#
https://developer.apple.com/library/archive/documentati
on/General/Reference/InfoPlistKeyReference/Articles/Cor
eFoundationKeys.htmlversion: 1.0.0
environment:
 sdk: ">=2.7.0 <3.0.0"
dependencies:
 flutter:
 sdk: flutter
 cupertino_icons: ^1.0.0
 #Firebase
 firebase_core: ^0.5.0
 #Firebase login
 firebase_auth: ^0.18.0+1
 #Firebase Database
 cloud_firestore: ^0.14.1+2
 #Firebase storage
 firebase_storage: ^5.2.0
 #Firebase messaging: for notifications
 firebase_messaging: ^7.0.3
 #image picker
 file_picker: ^2.1.1
 # State Management and Streams manipulations
 provider: ^4.3.2+3
 rxdart: ^0.25.0
 # Local Storage: For dark mode
 shared_preferences: ^0.5.12+4
 #Show svg images
 flutter_svg: ^0.19.0
 #Notification
 flutter_local_notifications: ^4.0.0
 #Dio plugin for sending notifications
 dio: ^3.0.10
 url_launcher: ^5.7.10
 #Flutter toast
 fluttertoast: ^7.1.8
dev_dependencies:
 flutter_test:
 sdk: flutter
 uses-material-design: true
 assets:
 - images/empty_cart.svg
 - images/error.svg
 - images/nothing_found.svg
 - images/reminder.svg
 - images/success.svg
 - images/logo.png
 - images/upload_image.png
 - images/stripe.png
```
