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

3. Get your `merchant ID` and go to `Developers → API` Keys and get your `publishable key` and paste them in `project_configuration.dart` file.

4. Go [Cloudflare workers](https://workers.cloudflare.com/) and add this script and replace `YOUR_STRIPE_SECRET_KEY` with your Stripe secret key:
```
addEventListener('fetch', function(event) {
  const { request } = event
  const response = handleRequest(request).catch(handleError)
  event.respondWith(response)
})

async function handleRequest(request) {
  const { method, url } = request
  const { host, pathname } = new URL(url)

  const stripeSecretKey='YOUR_STRIPE_SECRET_KEY';
  if(request.body!=null){

    const stripeRequest=await fetch('https://api.stripe.com/v1/payment_intents',
      {method : "POST",
      body:request.body,
      headers: {
      'Authorization': "Bearer "+stripeSecretKey,
      'Content-Type': 'application/x-www-form-urlencoded'
    },  
      }
    );
   return stripeRequest;
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

4. Copy the link and paste it helpers/project_configuration.dart (variable name: paymentApi).

*Note:* We choose CloudFlare workers over Firebase functions because he provide 100K free request per day (30M free in a period of 30 days) and Firebase functions offer 2M free request per month only.

#### Video:

{{< youtube ef2DuomFiaA >}}
