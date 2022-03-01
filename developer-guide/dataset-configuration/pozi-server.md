---
layout: default
title: Pozi Server
parent: Dataset Configuration
grand_parent: Developer Guide
nav_order: 1
---

# Pozi Server

## API

### Examples

Local install: https://local.pozi.com/ogr2ogr?source=sample/queenscliffe/delwp/vmfeat/foi_point.shp
More: https://local.pozi.com/tests?

Pozi Cloud: https://d2nozjvesbm579.cloudfront.net/ogr2ogr?source=data.gov.au/bendigo/cogb-community-mach-zones.shz

### Parameters

https://gdal.org/programs/ogr2ogr.html
#### Default Parameters

Pozi Server applies the following parameters by default to all requests:

* `-f GeoJSON`
* `lco RFC7946=YES` ([more info](https://gdal.org/drivers/vector/geojson.html#rfc-7946-write-support))

#### Simplify

`-simplify 0.00001`
#### Spatial Intersection

#### Unified Search
