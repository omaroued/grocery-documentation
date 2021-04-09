---
title: "Stripe"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 107
toc: true
---
In the user app, we used Stripe to receive payment from costomers. To add payment with credit cards, you need to follow these steps:

1. Create [Stripe Account](https://dashboard.stripe.com/register).

2. Add your business details to activate your account.

![image alt text](/images/stripe.jpg)

3. Get your `merchant ID` and go to `Developers → API` Keys and get your `publishable key` and your `secret key` and paste them in `project_configuration.dart` file.
