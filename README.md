# Thoughtful Tutors

## Description

This document describes the design of [Thoughtful Tutors](https://thoughtfultutors.co.uk), the site and email service.

## Domain

The domain is registered with Cloudflare.
All controls are available through the [Cloudflare Dashboard](https://dash.cloudflare.com/).
Cloudflare will stay the authoritative DNS for the site, as they offer this service for free.


## Email

The email is provided by [iCloud Custom Email Domain](https://developers.cloudflare.com/registrar/account-options/icloud-domains/) as this is included with the iCloud+ subscription.
Currently the emails available are: [dev](mailto:dev@thoughtfultutors.co.uk), [info](mailto:info@thoughtfultutors.co.uk).
Settings for this are largely managed through iCloud directly, but shouldn't need changing.


## Hosting

The site is served by [Cloudflare Workers static assets](https://developers.cloudflare.com/workers/static-assets/), configured in `wrangler.jsonc`.
Requests for static assets are free and unlimited, and Cloudflare provides HTTPS for the domain.
It was hosted on Amazon S3 behind Amazon CloudFront until November 2026; those resources have been deleted.

## Page Content

The static parts of the site are in the `site` directory.
Each page carries its own styles inline and uses fonts already on the reader's device (Charter on Apple devices, Sitka or Cambria on Windows), so a visit is a single request of about 4 KB.
The typography follows [Practical Typography](https://practicaltypography.com/): body text first, 18–21 px type, 140% line spacing, about 65 characters per line, subtle headings, and colour only on links.

## Deployment

```sh
wrangler deploy
```

This uploads `site/` and serves it on `thoughtfultutors.co.uk` and `www.thoughtfultutors.co.uk`; Cloudflare manages both DNS records and the certificate.
`wrangler rollback` restores an earlier version.

## Testing

Open `site/index.html` in a browser, or run `wrangler dev` to serve it as Cloudflare would.
