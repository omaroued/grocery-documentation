---
title: "Cloud Firestore"
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
Every database needs rules to give limited permissions to users and full
control to the admin. So, we will add rules to Firestore.

1. Go to Firebase → Cloud Firestore → Rules and paste these rules:

**Important**: Replace ADMIN_UID with your admin UID.

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
  function adminUid(){ return "ADMIN_UID"}

    match /permission_check/{check}{
    allow read : if  request.auth.uid== adminUid();
    }
    match /products/{product}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }
    match /admin/{document}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }
    match /categories/{category}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }  
    match /coupons/{coupon}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }
    match /shipping/{ship}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }
    match /users/{userId}/{collection=**}{
    allow read,write: if request.auth != null && (request.auth.uid == userId || request.auth.uid== adminUid());
    }
    match /{path=**}/orders/{order} {
       allow read,write: if request.auth != null && request.auth.uid== adminUid();
      }
  }
}
```

2. Go to Data and create a new collection named permission_check and put inside it any document name: This collection verifies if the user is the admin if he can read it.

![image alt text](/images/permission-check.jpg)

3. Add orders indexes: Go to indexes → Add index.

![image alt text](/images/firestore-rules.jpg)
