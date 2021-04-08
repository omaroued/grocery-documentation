---
title: "App name"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 100
toc: true
---


### Android
Go to `android/app/src/main/AndroidManifest.xml` and
search for `android:label` and change the old name with yours.
### iOS
Go to `ios/Runner/Info.plist` and search for
`<key>CFBundleName</key>`
and you will find the old name just under it. Replace him with yours.
