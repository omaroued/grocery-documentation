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


- In the downloaded file, you will find a folder named functions. Open index.js and you will find 4 functions:

1- sendNotificationFromAdmin

2- sendNotificationFromDeliveryBoy

3- createPayment

4- addOrder

- In `addOrder` and `createPayment` functions, you will find a variable named `stripeSecretKey`, assign your stripe secret key with it.

- After settings your variables, upload the functions to firebase.
- These videos show how to upload your functions to firebase:

{{< youtube 29BNaJiqWB4 >}}

{{< youtube gYF32BrHVlA >}}
