---
layout: default
title: Widgets
parent: Administrator Guide
---

# Widgets

*Available for Pozi Pro, Enterprise and Enterprise Cloud customers*

Pozi Widgets are embeddable address search tools that can be embedded into any website.

* data widget: search any address to display specific details about the location (eg, waste collection details)
* map widget: search any address to launch an instance of the Pozi web application focussed on the address location

Widgets can configured by clients without the need for any changes by Pozi staff. However you can request help from Pozi staff to construct the necessary embed code to suit your requirements.

## Data Widget

### Example

*Type '3 Queen Street' to try it out.*

<iframe style="border:none; height: 300px; width: 100%; overflow: hidden;" src="https://southerngrampians.pozi.com/widget.html#card=Waste Collection&fieldnames=Next Rubbish Pickup,Next Recycling Pickup,Next Organics Pickup&fontsize=20"></iframe>

### Configuration

Any result that appears in the *What's Here* section in the Info Panel of your site can be exposed in a data widget using the standard option described below. Other datasets can be exposed in the widget if the dataset is published as a WFS on data.gov.au, and can be configured using the CKAN option below.

#### Option 1. Standard

Any result that appears in the *What's Here* section in the Info Panel of your site can be exposed in a Pozi data widget. All that is needed is the name of the dataset (as displayed in the relevant tab heading).

`https://` + `site` + `/#card=` + `dataset` + `&widget=true`

Example:

* site: `strathbogie.pozi.com`
* dataset: `rubbishcollection` (derived from the "Rubbish Collection" tab heading in the *What's Here* results, with any spaces or underscores removed)

The basic widget URL is constructed as follows:

`https://` + `strathbogie.pozi.com` + `/#card=` + `rubbishcollection` + `&widget=true`

Widget URL: https://strathbogie.pozi.com/#card=rubbishcollection&widget=true

The resulting widget displays a table view of the results for the address specified by the user. See the Options section below for customising the results.

#### Option 2. CKAN

Datasets that don't appear in What's Here can still be configured as widgets if the dataset is accessible from data.gov.au's WFS service.

`https://` + `site` + `/#ckan=` + `ckan id` + `&widget=true`

*To do: update this section with working examples*

See https://help.pozi.com/article/53-obtaining-ckan-data-identifier for instructions on how to obtain the CKAN id.

The results from the data.gov.au API will not have any data transformers applied. If you require any data manipulation (such as waste collection calculations), you can specify them here in the widget URL. See Data Transformer details below.

### Options

#### Display Specific Fields

`&fieldnames=...`

#### Hide Field Names

`&fieldnameshide=true`

#### Data Transformer

If using the standard configration option, any transformers are already applied within the Pozi app, so there is typically no need to configure any transformer in the widget URL.

However, if using the CKAN option, the results will not have any transformers applied, and so you can specify them here in the widget URL.

`&transformer=garbage`

#### Specify Font Size

`&fontsize=16`

## Configuration Examples

Swan Hill Open Air Burning

```
https://widget.pozi.com/#site=swanhill&ckan=ckan_7cf7d8a9_387f_4e3f_8ef0_6ebe2d22ec84&widget=true&fieldnames=location,requiremen,criterion_,criterio00,criterio01&fieldnameshide=true&fontsize=16
```

## Map Widget

### Options

#### Redirect

If this parameter is added, the current page will be redirected to the Pozi map zoomed to the address.

`&reditect=true`

#### New Tab

If this parameter is added, the Pozi map will be loaded in a new tab zoomed to the address. Note this option can have issues with browser security such as the built in popup blockers, in particular in IE and Firefox. Whilst the user can change the settings in their browser to allow popups, depending on the expected customer, it may be more appropriate to avoid using the Newtab parameter and live with the downside of having the Pozi map load in the same tab as the address search was performed.

`&newtab=true`

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
