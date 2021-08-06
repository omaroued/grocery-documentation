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

1. Go to Firebase → Authentication, enable email and password authentication, add a user (it will be your admin user) and copy his uid.

2. Go to Firebase → Cloud Firestore → Rules and paste these rules:

**Important**: Replace ADMIN_UID with your admin UID.

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {

    //TODO: Put your admin UID
    function adminUid(){ return "ADMIN_UID"}

    // Collection to check if the user is the admin or not
    match /permission_check/{check}{
    allow read : if  request.auth.uid== adminUid();
    }

    // Products collection
    // Allow read only to normal users, read and write to admin
    match /products/{product}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }

    // Admin collection
    // Allow read only to normal users (to get notifications token), read and write to admin
    match /admin/{document}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }

    // Categories collection
    // Allow read only to normal users, read and write to admin
    match /categories/{category}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }

    // Coupons collection
    // Allow read only to normal users, read and write to admin
    match /coupons/{coupon}/{collection=**}{
    allow get: if request.auth != null;
    allow list: if request.auth != null && request.auth.uid== adminUid() ;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }

    // Shipping methods collection
    // Allow read only to normal users, read and write to admin
    match /shipping/{ship}/{collection=**}{
    allow read: if request.auth != null;
    allow write: if request.auth != null && request.auth.uid== adminUid() ;
    }


    // Users collection (with nested cllections)
    // Allow read and write to normal users in his document, read and write to admin in all documents
    match /users/{userId}/{collection=**}{
    allow read,write: if request.auth != null &&
    (request.auth.uid == userId ||
    request.auth.uid== adminUid());
    }

    // Users collection (without nested cllections)
    // Allow read only to delivery boys (to get notifications token)
    match /users/{userId}{
    allow read: if request.auth != null &&
    exists(/databases/$(database)/documents/delivery_boys/$(request.auth.token.email));
    }


    // Delivery boys collection 
    // Allow read and write to delivery boys in his document, read and write to admin in all documents
    match /delivery_boys/{email}{
    allow read,write: if request.auth.uid== adminUid();
    allow read,update: if request.auth != null &&
    (request.auth.token.email == email)
    && exists(/databases/$(database)/documents/delivery_boys/$(email));
    }
    


    // Delivery boys history collection
    // Allow read and write to delivery boys in his document, read and write to admin in all documents
    match /delivery_boys/{email}/history/{collection=**}{
    allow read,write: if request.auth.uid== adminUid();
    allow read,write: if
         request.auth != null &&
         (request.auth.token.email == email) &&
         exists(/databases/$(database)/documents/delivery_boys/$(email));
    }


    // Orders collection group
    // Allow read and update to delivery boys, read and write to admin
    match /{path=**}/orders/{order} {
    allow read,write: if request.auth != null && request.auth.uid== adminUid();
    allow read,update: if request.auth != null
           && resource.data.status== "Processing"
           && resource.data.delivery_boy.email== request.auth.token.email;
    }

  }
}
```


2. Add orders indexes: Go to indexes → Add index.

![image alt text](/images/firestore-rules.jpg)


**Note:** in the video we made only 3 Firestore indexes. You have to add the fourth index (products) as you see in the picture.
#### Video:

{{< youtube 8CxLF1-g2tA >}}
