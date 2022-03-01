---
layout: default
title: ArcGIS
parent: Dataset Configuration
grand_parent: Developer Guide
nav_order: 1
---

# ArcGIS

[ArcGIS Online Health Dashboard](https://status.arcgis.com/)

## FeatureServer API GeoJSON

Obtaining GeoJSON endpoint:

1. Go to dataset's FeatureServer page [[example]](https://www.arcgis.com/home/item.html?id=203951d814374494af36437e19767cbf)
2. Copy URL link from bottom of page [[example]](https://services3.arcgis.com/TJxZpUnYIJOvcYwE/arcgis/rest/services/CILZones/FeatureServer)
3. go to URL, click desired layer from Layer list, and copy URL [[example]](https://services3.arcgis.com/TJxZpUnYIJOvcYwE/ArcGIS/rest/services/CILZones/FeatureServer/0)
4. append parameters (see reference below) [[example]](https://services3.arcgis.com/TJxZpUnYIJOvcYwE/arcgis/rest/services/CILZones/FeatureServer/0/query?f=geojson&outFields=*&where=1=1)

### Parameters

#### For Entire Dataset

`/query?f=geojson&outFields=*&where=1=1`

[[Example]](https://services3.arcgis.com/TJxZpUnYIJOvcYwE/arcgis/rest/services/CILZones/FeatureServer/0/query?f=geojson&outFields=*&where=1=1)


#### Spatial Intersection

`/query?f=geojson&outFields=*&returnGeometry=true&inSR=4326&spatialRel=esriSpatialRelIntersects&geometryType=[$esriGeometryType]&geometry=[$esriGeometry]`

[[Example]](https://services3.arcgis.com/TJxZpUnYIJOvcYwE/arcgis/rest/services/CILZones/FeatureServer/0/query?f=geojson&outFields=*&returnGeometry=true&inSR=4326&spatialRel=esriSpatialRelIntersects&geometryType=[$esriGeometryType]&geometry=[$esriGeometry])

#### Complete Reference

[Esri ArcGIS REST APIs Documentation](https://developers.arcgis.com/rest/services-reference/enterprise/query-feature-service-layer-.htm)

## Example Configuration

### Layer

```json
{
  "title": "Community Infrastructure Levy",
  "group": "Council Facilities and Services",
  "type": "GeoJSON",
  "config": {
    "spatial": {
      "url": "https://services3.arcgis.com/TJxZpUnYIJOvcYwE/arcgis/rest/services/CILZones/FeatureServer/0/query?f=geojson&outFields=*&where=1=1",
      "label": "DCP",
      "id": "$id"
    }
  },
  "opacity": 0.5,
}
```

### What's Here

```json
{
  "title": "Applicable Community Infrastructure Levy",
  "icon": "img/map-icons/dollar4.svg",
  "type": "GeoJSON",
  "parent": "Whats Here",
  "showInLayerControl": false,
  "config": {
    "spatial": {
      "url": "https://services3.arcgis.com/TJxZpUnYIJOvcYwE/arcgis/rest/services/CILZones/FeatureServer/0/query?f=geojson&outFields=*&returnGeometry=true&inSR=4326&spatialRel=esriSpatialRelIntersects&geometryType=[$esriGeometryType]&geometry=[$esriGeometry]",
      "label": "DCP",
      "id": "$id"
    }
  }
}
```
