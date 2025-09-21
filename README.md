# Thoughtful Tutors

## Description

This document describes the design of [Thoughtful Tutors](www.thoughtfultutors.co.uk), the site and email hosting service.

## Domain

The domain is registered with Cloudflare.
All controls are available through the [Cloudflare Dashboard](https://dash.cloudflare.com/).
Cloudflare will stay the authoritative DNS for the site, as they offer this service for free.


## Email

The email is provided by [iCloud Custom Email Domain](https://developers.cloudflare.com/registrar/account-options/icloud-domains/) as this is included with the iCloud+ subscription.
Currently the emails available are: [dev](mailto:dev@thoughtfultutors.co.uk), [info](mailto:info@thoughtfultutors.co.uk).
Settings for this are largely managed through iCloud directly, but shouldn't need changing.


## Hosting

The hosting is backed by Amazon S3 and sped up with Amazon Cloudfront, which also provides SSL.
The `opentofu` directory contains the infrastructure in code form.

## Page Content

The static parts of the site are available in `site` directory.

## Deployment

## Testing
