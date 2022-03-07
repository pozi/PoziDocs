---
layout: default
title: QGIS Project Configuration
parent: Pozi Server
grand_parent: Administrator Guide
---

## *Under Construction*

*This page is a work in progress. Please refer to our existing Help Guide for information about this topic.*

[Existing Help Guide](https://help.pozi.com/){: .btn .btn-outline }

---

# QGIS Project Configuration

## Introduction

You can use QGIS projects to publish internal map layers to your organisation's internal users.

Each project represents a layer group within Pozi.

The example below uses a QGIS project called `property.qgs`.

## Create Project

1. open QGIS
2. add layers from internal data sources
3. configure styling for layers
4. Project > Save >
   * example: `C:\Program Files (x86)\Pozi\userdata\local\property.qgs`

## Enable Project as WMS Service

1. Project > Properties > QGIS Server
2. update these settings
   * `Add geometry to feature response`: tick on
   * `Advertised URL`: enter WMS GetCapabilities address
     * example: `https://local.pozi.com/iis/qgisserver?service=WMS&request=GetCapabilities&MAP=C:/Program%20Files%20(x86)/Pozi/userdata/local/property.qgs`
   * `Published layers`: tick Project box
3. OK
4. Project > Save



<img src="../img/qgis-project-properties-wms-configuration.png" alt="Screenshot of QGIS Project Properties WMS Configuration" style="zoom:60%;" />



## Enable Layers in WFS Service

WFS (Web Feature Service) provides users with the ability to directly interact with map features.

Advantages:

* cursor changes when hovering over object
* select individual features and display results in Info Panel without displaying results of features on other layers at the same location
* enable filter, report and table view

Disadvantages:

* the browser can be easily overwhelmed when dealing with thousands of features
* labelling for WFS features is not well supported, especially for line features such as roads

It is recommend to only enable WFS for layers with fewer than 10K features.

1. Project > Properties > QGIS Server
2. update the following settings:
   * `WFS capabilities > Published`: tick on for each layer to be published
   * `Advertised URL`: enter WFS GetCapabilities
     * example: `https://local.pozi.com/iis/qgisserver?service=WFS&version=1.1.0&request=GetCapabilities&MAP=C:/Program%20Files%20(x86)/Pozi/server/data/local/property.qgs`
3. OK
4. Project > Save



<img src="../img/qgis-project-properties-wfs-configuration.png" alt="Screenshot of QGIS Project Properties WfS Configuration" style="zoom:60%;" />
