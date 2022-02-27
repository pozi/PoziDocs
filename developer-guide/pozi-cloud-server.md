---
layout: default
title: Pozi Cloud Server
parent: Developer Guide
nav_order: 3
---

# Pozi Cloud Server

## EC2 Issues

* The server did not allow downloading files using IE. This page explains how to work around this: https://aws.amazon.com/premiumsupport/knowledge-center/ec2-windows-file-download-ie/
* SSL/Certificate issues between Cloudfront and the EC2 instance. Thanks to: https://bobcares.com/blog/cloudfront-wasnt-able-to-connect-to-the-origin-how-to-fix/. Solution: run PoziServer on `POZI_CONNECT_PORT=3001` with `HTTPS=false`
* The server expired the Administrator password after 45 days. Make sure to set `Password never expires` for every user, especially Administrator. You can do this via `Computer management`

## Cloudfront

* URL: https://d2nozjvesbm579.cloudfront.net/

## Example Requests

* https://d2nozjvesbm579.cloudfront.net/ogr2ogr?source=frankston/property-valuation-information.vrt&options=-where|propertynumber='214855'
* https://d2nozjvesbm579.cloudfront.net/ogr2ogr?source=data.gov.au/bendigo/cogb-recreation-drinking-fountains.shz
