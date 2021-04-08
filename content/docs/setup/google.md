---
title: "Google"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 103
toc: true
---

**Note**: you have to implement these instructions in the user app only.

For Google authentication, we need to add a little iOS configuration.

You have to go `Info.plist` and search for:
`<string>com.googleusercontent.apps.279585014161-lnc442tn9o8m76nfo3vr2tnn14l844oi</string>` and replace the URL with the one that you will find in `GoogleService-Info.plist` under: `<key>REVERSED_CLIENT_ID</key>`
