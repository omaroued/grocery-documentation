---
title: "Facebook"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 104
toc: true
---

**Note**: you have to implement these instructions in the user app only.

## Android
1. Create a Facebook app and choose **Build Connected Experiences** and choose a name and email.

2. Enter to your app and go to Settings/Basic and click to Add Platform and choose Android.

3. Add app package and class and Key Hashes and save changes.

**Note**: to get get Key haches open CMD and type:

```
keytool -exportcert -alias androiddebugkey -keystore "C:\Documents and Settings\Administrator.android\debug.keystore" | "C:\OpenSSL\bin\openssl" sha1 -binary |"C:\OpenSSL\bin\openssl" base64
```

and replace C:\OpenSSL with your OpenSSL path.

4. Go to Firebase → Authentication → Sign-in method: Activate Facebook and enter app id and secret (you find them in Settings/basic in Facebook) and copy OAuth redirect URI.

5. Go to your Facebook app dashboard and click on Facebook Login Set Up → Android and click next in all steps.

6. Go to Facebook Login → Settings and paste the OAuth redirect URI in Client OAuth Settings and save changes.

7. Go to `android/app/src/main/res/values/strings.xml` and replace old Facebook values with yours.
## IOS

1. Go to Facebook login → QuickStart and choose iOS.

2. Add your bundle Identifier.

3. Go to Info.plist replace old Facebook values with yours.

![image alt text](/images/fb.jpg)
