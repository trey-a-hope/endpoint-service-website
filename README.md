# Endpoint Service Website

A one-page Angular site that documents the PHP API endpoints hosted at `es.tr3umphant-designs.com`. Those endpoints wrap the Stripe API and a mail script so Trey's apps from 2018 (such as the tr3Designs store) could call them over HTTP. The site itself only lists the endpoints and their parameters. The PHP code isn't in this repo.

## What it documents

The home page (`src/app/views/home/home.component.html`) lists each endpoint under `http://es.tr3umphant-designs.com/assets/` with its POST parameters:

| Group | Endpoints |
| --- | --- |
| Stripe tokens | create token |
| Stripe cards | create, retrieve, update, list all, delete |
| Stripe charges | create, capture, retrieve, update, list all |
| Stripe customers | create, retrieve, update, delete, list all |
| Stripe orders | create, pay, retrieve, list all |
| Stripe payouts | create, cancel, retrieve, update, list all |
| Stripe products and SKUs | list all products, retrieve product, retrieve SKU |
| Stripe transfers | create transfer |
| Email | send email (`to`, `from`, `subject`, `message`) |

Every Stripe endpoint takes an `apiKey` parameter, meaning the caller sends the Stripe secret key with each request. The About page says the site exists only to keep track of these endpoints.

## Tech stack

- Angular 5 with the Angular CLI (`.angular-cli.json`)
- Material Design for Bootstrap (`angular-bootstrap-md`)

## Getting started

Requires a Node.js version that Angular CLI 1.x supports (Node 8 or 10).

```sh
npm install
npm start          # ng serve on http://localhost:4200
npm run build      # ng build --prod, output in dist/
```

## Note

Sending a Stripe secret key from client apps to these endpoints exposes it to anyone using the app. If the endpoints are still live, they should keep the key on the server instead.
