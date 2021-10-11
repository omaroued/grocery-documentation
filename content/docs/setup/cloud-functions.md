---
title: "Cloud Functions"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 105
toc: true
---
**Note:** Do these steps if you want to activate billing and work with cloud functions.


## Setup

In the downloaded file, you will find a folder named functions. Open index.js and you will find 4 functions:

1. sendNotificationFromAdmin

2. sendNotificationFromDeliveryBoy

3. createPayment

4. addOrder

- In `addOrder` and `createPayment` functions, you will find a variable named `stripeSecretKey`, assign your stripe secret key with it.

- In `sendNotificationFromAdmin` function, you will find a variable named `adminUid`, assign youradmin UID with it.


## Working with Firebase emulators
You still can work with cloud functions without activate billing with fFirebase emulators (Only to check if your functions are working). You have to follow these steps:

1. Install [Firebase CLI](https://firebase.google.com/docs/cli).
2. Run CMD and to `firebase` folder and type:
```
firebase init
```

3. Run this command:
```
firebase emulators:start
```

4. Go to `lib/services/cloud_functions` and uncomment this line:
```
_functions.useFunctionsEmulator('localhost', 5001);
```

## Upload your functions to Firebase

These videos show how to upload your functions to firebase:

{{< youtube 29BNaJiqWB4 >}}

{{< youtube gYF32BrHVlA >}}
