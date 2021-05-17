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

1. For notifications between users, admin and delivery boys, we will use firebase messaging. So, we need the server key. To get it, you have to go to Project settings → Cloud messaging and copy the server key.


2. Go [Cloudflare workers](https://workers.cloudflare.com/) and add this script and replace `YOUR_MESSAGING_KEY` with your Stripe secret key:
```
addEventListener('fetch', function(event) {
  const { request } = event
  const response = handleRequest(request).catch(handleError)
  event.respondWith(response)
})

async function handleRequest(request) {
  const { method, url } = request
  const { host, pathname } = new URL(url)

  const firebaseSecretKey='YOUR_MESSAGING_KEY';
  if(request.body!=null){

    const firebaseRequest=await fetch('https://fcm.googleapis.com/fcm/send',
      {method : "POST",
      body:request.body,
      headers: {
        'content-type': 'application/json',
        'Authorization': 'key='+ firebaseSecretKey,
      },  
      }
    );
   return firebaseRequest;

  }else{
    new Response('Bad Request', { status: 400 })
  }

  // Workers on these hostnames have no origin server,
  // therefore there is nothing else to be found
  if (host.endsWith('.workers.dev')
      || host.endsWith('.cloudflareworkers.com')) {
    return new Response('Not Found', { status: 404 })
  }

  // Makes a fetch request to the origin server
  return fetch(request)
}

/**
 * Responds with an uncaught error.
 * @param {Error} error
 * @returns {Response}
 */
function handleError(error) {
  console.error('Uncaught error:', error)

  const { stack } = error
  return new Response(stack || error, {
    status: 500,
    headers: {
      'Content-Type': 'text/plain;charset=UTF-8'
    }
  })
}
```

3. Copy the link and paste it helpers/project_configuration.dart (variable name: notificationsApi).

#### Video:

{{< youtube 2DLmbsCi8kM >}}


## Android
To change notification icon, go to `android/app/src/main/res/drawable` and replace `notification_logo.png` with yours (keep same file name).

## IOS
1. Generate the certificates required by Apple for receiving push notifications following this [guide](https://firebase.google.com/docs/cloud-messaging/ios/certs) in the Firebase docs. You can skip the section titled `Create the Provisioning Profile`.
2. In Xcode, select Runner in the Project Navigator. In the `Capabilities` Tab turn on `Push Notifications` and `Background Mode`s, and enable `Background fetch` and `Remote notifications` under `Background Modes`.
