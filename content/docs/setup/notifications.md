---
title: "Notifications"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 106
toc: true
---



## Setup
- **Note:** add this part if you want to work in the free plan (Without cloud functions).



1. For notifications between users, admin and delivery boys, we will use firebase messaging. So, we need the server key. To get it, you have to go to Project settings → Cloud messaging and copy the server key.

2. Open `Without cloud functions/send-notification.js` and search for variable named `firebaseSecretKey` and put your secret key.

3. Go [Cloudflare workers](https://workers.cloudflare.com/) and add the script.

4. Copy the link and paste it helpers/project_configuration.dart (variable name: notificationsApi).

#### Video:

{{< youtube 2DLmbsCi8kM >}}


## Android
To change notification icon, go to `android/app/src/main/res/drawable` and replace `notification_logo.png` with yours (keep same file name).

## IOS
1. Generate the certificates required by Apple for receiving push notifications following this [guide](https://firebase.google.com/docs/cloud-messaging/ios/certs) in the Firebase docs. You can skip the section titled `Create the Provisioning Profile`.
2. In Xcode, select Runner in the Project Navigator. In the `Capabilities` Tab turn on `Push Notifications` and `Background Mode`s, and enable `Background fetch` and `Remote notifications` under `Background Modes`.
