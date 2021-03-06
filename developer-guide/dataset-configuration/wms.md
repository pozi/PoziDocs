---
layout: default
title: WMS (Web Map Service)
parent: Dataset Configuration
grand_parent: Developer Guide
nav_order: 5
---

# WMS (Web Map Service)

## Services

### DELWP DataVic

* [GetCapabilities](https://services.land.vic.gov.au/catalogue/publicproxy/guest/dv_geoserver/wms?request=getCapabilities)

### data.gov.au

* [GeoServer Layer Preview](https://data.gov.au/geoserver/web/wicket/bookmarkable/org.geoserver.web.demo.MapPreviewPage?0)
* [GetCapabilities](https://data.gov.au/geoserver/wms?SERVICE=WMS&VERSION=1.3.0&REQUEST=GetCapabilities)

### Pozi Cloud Server

* [Example GetCapabilities](https://d2nozjvesbm579.cloudfront.net/iis/qgisserver?service=WMS&request=GetCapabilities&MAP=C:/Program%20Files%20(x86)/Pozi/server/data/local/sample/queenscliffe/vicmap.qgs)

## Styling

### External SLD

WMS GetMap requests can be made with an `sld` parameter that contains the URL of an SLD file.

*Note: as at 25 Feb 2022, the data.gov.au WMS service is not successfully responding to WMS requests that point to external SLDs. See 'Embedded SLD' below for an alternative styling configuration. Or better yet, consider using WFS if the dataset is small enough.*

### Embedded SLD

WMS GetMap requests can be made with an `sld_body` parameter that contains the SLD styling rules as a string of XML.

Switching from external SLD to embedded SLD:

1. download the existing external SLD and open in text editor (VSCode or NotePad++ recommended)
2. find and replace double spaces with blank
3. find and replace line returns with blank
4. find and replace double quotes with single quotes

The resulting text is a single line of XML.

In the dataset config, replace the existing `sld` parameter with a new `sld_body` parameter, using the line of XML as the value.

Examples

* [Glen Eira Street Trees](https://github.com/pozi/PoziAppConfig/commit/c2f9bf6b3eb9998b27d85df266ebf48fc4ff80c5#diff-5a45ada4e9f3d1ed3db20f652cabe746c1767390718cf94228bc25a7576c9f7dL776-R776)
* [Mitchell Contours](https://github.com/pozi/PoziAppConfig/commit/d95812fd4691e86e0fac3de91d0e3ad5fbb7683b#diff-216128510370c47687518818e49f4d63083c96ba0b3686031cea3cc7dc0d98feL3214-R3234)
