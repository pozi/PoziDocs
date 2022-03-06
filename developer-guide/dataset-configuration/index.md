---
layout: default
title: Dataset Configuration
parent: Developer Guide
has_children: true
nav_order: 1
---

# Dataset Configuration

## Dataset Types

```
GeoJSON
Image
ImageWMS
QGISGetProjectSettings
Search
TileWMS
TileWMSAuth
Mapbox
Mapbox-GL
Mapbox-OLSM
VectorTile
Vicmap
WFSGetCapabilities
WMSGetCapabilities
XYZ
```

See https://github.com/pozi/PoziApp/blob/master/app/src/ConfigManager/schemas/layer-schema.json

## Examples

### Basic GeoJSON

```json
{
  "title": "Maternal and Child Health Zones",
  "group": "Family Services",
  "type": "GeoJSON",
  "config": {
    "spatial": {
      "url": "https://d2nozjvesbm579.cloudfront.net/ogr2ogr?source=data.gov.au/bendigo/cogb-community-mach-zones.shz",
      "label": "Name",
      "id": "Name"
    }
  },
  "styleGeoStyler": {
    "type": "SLD",
    "url": "https://config.pozi.com/public/files/cogb_mach_zones.sld"
  },
  "opacity": 0.8,
  "queryable": true,
  "showInLayerControl": true
}
```

### Options

#### Metadata

```
  "about": {
    "organisation": "City of Greater Bendigo",
    "url": "https://data.gov.au/dataset/ds-dga-3df55d47-8fde-4f2d-97a6-ba51bdbad0cb"
  },
```
#### "What's Here" Datasets

Display the feature's attributes (which would normally be displayed in the Details panel of the child record) directly in What's Here, taking the place of the title.

`"promoteDetails": true`

Only be used when there is no requirement to view Location/Dimensions, Source or child records.
