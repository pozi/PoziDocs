---
layout: default
title: Widgets
parent: Administrator Guide
---

## *Under Construction*

*This page is a work in progress. Please refer to our existing Help Guide for information about this topic.*

[Existing Help Guide](https://help.pozi.com/search?query=widgets){: .btn .btn-outline }

---

# Widgets

## Example

*Type '3 Queen Street' to try it out.*

<iframe style="border:none; height: 300px; width: 100%; overflow: hidden;" src="https://southerngrampians.pozi.com/widget.html#card=Waste Collection&fieldnames=Next Rubbish Pickup,Next Recycling Pickup,Next Organics Pickup&fontsize=20"></iframe>

## Configuration

### Standard

### CKAN

### Options

`&fieldnames=...`

`&fieldnameshide=true`

`&fontsize=16`

## Configuration Examples

```
https://widget.pozi.com/#site=swanhill&ckan=ckan_7cf7d8a9_387f_4e3f_8ef0_6ebe2d22ec84&widget=true&fieldnames=location,requiremen,criterion_,criterio00,criterio01&fieldnameshide=true&fontsize=16
```

## Embedding

The HTML for embedding the widget in your website:

```
<iframe style="border:none; height: 300px; width: 100%; overflow: hidden;" src="https://southerngrampians.pozi.com/widget.html#card=Waste Collection&fieldnames=Next Rubbish Pickup,Next Recycling Pickup,Next Organics Pickup&fontsize=20"></iframe>
```

## Showcase

Map Widgets:

* [Cardinia "My Council Services"](https://www.cardinia.vic.gov.au/)

Data Widgets:

* [Cardinia Bin Collection Days](https://www.cardinia.vic.gov.au/binday#section-3-check-your-bin-collection-days-online)
* [Swan Hill Open Air Burning](https://www.swanhill.vic.gov.au/environment-and-waste/fires/open-air-burning/)

## Troubleshooting

### Some fields are not showing in the results

If the widget URL specifies field names to display via `&fieldnames=...`, these fields must existin the source data.

If expected attributes are not showing, check that the field names in the source data have not changed. If they have changed, update the widget URL accordingly.
