---
layout: default
title: Layer Styling
parent: Administrator Guide
---

## *Under Construction*

*This page is a work in progress. Please refer to our existing Help Guide for information about this topic.*

[Existing Help Guide](https://help.pozi.com/search?query=layer+styling){: .btn .btn-outline }

---

# Layer Styling

## Styled Layer Descriptor (SLD)

### Generating SLDs

1. open your source dataset in QGIS
2. style the layer using the QGIS styling controls
3. export the style to an SLD file
4. place SLD file in public sync folder, along with the corresponding GeoJSON file

<img src="../img/creating-sld-in-qgis.gif" alt="" style="zoom:65%;" />

### Styling Options

Supported:

* simple points, lines, polygons symbolisers
* rule-based styles
* basic labels
* customisable legend text

Not currently supported:

* fill hatching
* label offsets
* rules based on a field name that contains spaces

Tips

* opacity must be defined in the colour - the layer's global opacity slider has no effect

## Bubble Symbols

In addition to standard map styles, Pozi supports user-friendly "bubble" symbols.

Pick your symbol and colour, and email support@pozi.com to organise the setup on the style. The symbol can be referenced by URL or name, and the colour must be provided as a colour hex code (eg `#CD5C5C`) from one of the options below.
### Symbols

Symbols can be chosen from any of the following:

* https://thenounproject.com/
* http://map-icons.com/

Obtain the URL or icon name for the desired icon.
### Colours

Bubble symbols can be styled with the following colours.
#### Reds

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:indianred" /></svg> | IndianRed | `#CD5C5C` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightcoral" /></svg> | LightCoral | `#F08080` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:salmon" /></svg> | Salmon  | `#FA8072` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darksalmon" /></svg> | DarkSalmon | `#E9967A` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightsalmon" /></svg> | LightSalmon | `#FFA07A` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:crimson" /></svg> | Crimson  | `#DC143C` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:red" /></svg> | Red  | `#FF0000` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:fireBrick" /></svg> | FireBrick | `#B22222` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkred" /></svg> | DarkRed  | `#8B0000` |

#### Pinks

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:pink" /></svg> | Pink  | `#FFC0CB` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightpink" /></svg> | LightPink | `#FFB6C1` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:hotpink" /></svg> | HotPink  | `#FF69B4` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:deeppink" /></svg> | DeepPink  | `#FF1493` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumvioletred" /></svg> | MediumVioletRed | `#C71585` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:palevioletred" /></svg> | PaleVioletRed  | `#DB7093` |

#### Oranges

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightsalmon" /></svg> | LightSalmon  | `#FFA07A` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:coral" /></svg> | Coral  | `#FF7F50` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:tomato" /></svg> | Tomato  | `#FF6347` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:orangered" /></svg> | OrangeRed | `#FF4500` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkorange" /></svg> | DarkOrange | `#FF8C00` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:orange" /></svg> | Orange  | `#FFA500` |

#### Yellows

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:gold" /></svg> | Gold  | `#FFD700` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:yellow" /></svg> | Yellow  | `#FFFF00` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightyellow" /></svg> | LightYellow | `#FFFFE0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lemonchiffon" /></svg> | LemonChiffon  | `#FFFACD` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightgoldenrodyellow" /></svg> | LightGoldenrodYellow | `#FAFAD2` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:papayawhip" /></svg> | PapayaWhip | `#FFEFD5` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:moccasin" /></svg> | Moccasin  | `#FFE4B5` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:peachpuff" /></svg> | PeachPuff | `#FFDAB9` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:palegoldenrod" /></svg> | PaleGoldenrod  | `#EEE8AA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:khaki" /></svg> | Khaki  | `#F0E68C` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkkhaki" /></svg> | DarkKhaki | `#BDB76B` |

#### Purples

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lavender" /></svg> | Lavender  | `#E6E6FA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:thistle" /></svg> | Thistle  | `#D8BFD8` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:plum" /></svg> | Plum  | `#DDA0DD` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:violet" /></svg> | Violet  | `#EE82EE` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:orchid" /></svg> | Orchid  | `#DA70D6` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:fuchsia" /></svg> | Fuchsia  | `#FF00FF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:magenta" /></svg> | Magenta  | `#FF00FF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumorchid" /></svg> | MediumOrchid  | `#BA55D3` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumpurple" /></svg> | MediumPurple  | `#9370DB` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:#9966CC" /></svg> | Amethyst  | `#9966CC` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:blueviolet" /></svg> | BlueViolet | `#8A2BE2` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkviolet" /></svg> | DarkViolet | `#9400D3` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkorchid" /></svg> | DarkOrchid | `#9932CC` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkmagenta" /></svg> | DarkMagenta | `#8B008B` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:purple" /></svg> | Purple  | `#800080` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:indigo" /></svg> | Indigo  | `#4B0082` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:slateblue" /></svg> | SlateBlue | `#6A5ACD` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkslateblue" /></svg> | DarkSlateBlue  | `#483D8B` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumslateblue" /></svg> | MediumSlateBlue | `#7B68EE` |

#### Greens

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:greenyellow" /></svg> | GreenYellow | `#ADFF2F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:chartreuse" /></svg> | Chartreuse | `#7FFF00` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lawngreen" /></svg> | LawnGreen | `#7CFC00` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lime" /></svg> | Lime  | `#00FF00` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:limegreen" /></svg> | LimeGreen | `#32CD32` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:palegreen" /></svg> | PaleGreen | `#98FB98` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightgreen" /></svg> | LightGreen | `#90EE90` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumspringgreen" /></svg> | MediumSpringGreen | `#00FA9A` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:springgreen" /></svg> | SpringGreen | `#00FF7F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumseagreen" /></svg> | MediumSeaGreen  | `#3CB371` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:seagreen" /></svg> | SeaGreen  | `#2E8B57` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:forestgreen" /></svg> | ForestGreen | `#228B22` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:green" /></svg> | Green  | `#008000` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkgreen" /></svg> | DarkGreen | `#006400` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:yellowgreen" /></svg> | YellowGreen | `#9ACD32` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:olivedrab" /></svg> | OliveDrab | `#6B8E23` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:olive" /></svg> | Olive  | `#808000` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkolivegreen" /></svg> | DarkOliveGreen  | `#556B2F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumaquamarine" /></svg> | MediumAquamarine | `#66CDAA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkseagreen" /></svg> | DarkSeaGreen  | `#8FBC8F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightseagreen" /></svg> | LightSeaGreen  | `#20B2AA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkcyan" /></svg> | DarkCyan  | `#008B8B` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:teal" /></svg> | Teal  | `#008080` |

#### Blues

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:aqua" /></svg> | Aqua  | `#00FFFF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:cyan" /></svg> | Cyan  | `#00FFFF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightcyan" /></svg> | LightCyan | `#E0FFFF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:paleturquoise" /></svg> | PaleTurquoise  | `#AFEEEE` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:aquamarine" /></svg> | Aquamarine | `#7FFFD4` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:turquoise" /></svg> | Turquoise | `#40E0D0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumturquoise" /></svg> | MediumTurquoise | `#48D1CC` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkturquoise" /></svg> | DarkTurquoise  | `#00CED1` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:cadetblue" /></svg> | CadetBlue | `#5F9EA0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:steelblue" /></svg> | SteelBlue | `#4682B4` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightsteelblue" /></svg> | LightSteelBlue  | `#B0C4DE` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:powderblue" /></svg> | PowderBlue | `#B0E0E6` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightblue" /></svg> | LightBlue | `#ADD8E6` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:skyblue" /></svg> | SkyBlue  | `#87CEEB` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightskyblue" /></svg> | LightSkyBlue  | `#87CEFA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:deepskyblue" /></svg> | DeepSkyBlue | `#00BFFF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:dodgerblue" /></svg> | DodgerBlue | `#1E90FF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:cornflowerblue" /></svg> | CornflowerBlue  | `#6495ED` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumslateblue" /></svg> | MediumSlateBlue | `#7B68EE` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:royalblue" /></svg> | RoyalBlue | `#4169E1` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:blue" /></svg> | Blue  | `#0000FF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mediumblue" /></svg> | MediumBlue | `#0000CD` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkblue" /></svg> | DarkBlue  | `#00008B` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:navy" /></svg> | Navy  | `#000080` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:midnightblue" /></svg> | MidnightBlue  | `#191970` |

#### Browns

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:cornsilk" /></svg> | Cornsilk  | `#FFF8DC` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:blanchedalmond" /></svg> | BlanchedAlmond  | `#FFEBCD` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:bisque" /></svg> | Bisque  | `#FFE4C4` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:navajowhite" /></svg> | NavajoWhite | `#FFDEAD` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:wheat" /></svg> | Wheat  | `#F5DEB3` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:burlywood" /></svg> | BurlyWood | `#DEB887` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:tan" /></svg> | Tan  | `#D2B48C` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:rosybrown" /></svg> | RosyBrown | `#BC8F8F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:sandybrown" /></svg> | SandyBrown | `#F4A460` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:goldenrod" /></svg> | Goldenrod | `#DAA520` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkgoldenrod" /></svg> | DarkGoldenrod  | `#B8860B` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:Peru" /></svg> | Peru  | `#CD853F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:chocolate" /></svg> | Chocolate | `#D2691E` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:saddlebrown" /></svg> | SaddleBrown | `#8B4513` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:sienna" /></svg> | Sienna  | `#A0522D` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:brown" /></svg> | Brown  | `#A52A2A` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:maroon" /></svg> | Maroon  | `#800000` |

#### Whites

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:white" /></svg> | White  | `#FFFFFF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:snow" /></svg> | Snow  | `#FFFAFA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:honeydew" /></svg> | Honeydew  | `#F0FFF0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mintcream" /></svg> | MintCream | `#F5FFFA` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:azure" /></svg> | Azure  | `#F0FFFF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:aliceblue" /></svg> | AliceBlue | `#F0F8FF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:ghostwhite" /></svg> | GhostWhite | `#F8F8FF` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:whitesmoke" /></svg> | WhiteSmoke | `#F5F5F5` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:seashell" /></svg> | Seashell  | `#FFF5EE` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:beige" /></svg> | Beige  | `#F5F5DC` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:oldlace" /></svg> | OldLace  | `#FDF5E6` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:floralwhite" /></svg> | FloralWhite | `#FFFAF0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:ivory" /></svg> | Ivory  | `#FFFFF0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:antiquewhite" /></svg> | AntiqueWhite  | `#FAEBD7` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:linen" /></svg> | Linen  | `#FAF0E6` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lavenderblush" /></svg> | LavenderBlush  | `#FFF0F5` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:mistyrose" /></svg> | MistyRose | `#FFE4E1` |

#### Greys

| Colour         | Colour Name          | Colour Value             |
|:---------------|:---------------------|:-------------------------|
| <svg width="50" height="20"><rect width="50" height="20" style="fill:gainsboro" /></svg> | Gainsboro | `#DCDCDC` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightgrey" /></svg> | LightGrey | `#D3D3D3` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:silver" /></svg> | Silver  | `#C0C0C0` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkgray" /></svg> | DarkGray  | `#A9A9A9` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:gray" /></svg> | Gray  | `#808080` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:dimgray" /></svg> | DimGray  | `#696969` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:lightslategray" /></svg> | LightSlateGray  | `#778899` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:slategray" /></svg> | SlateGray | `#708090` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:darkslategray" /></svg> | DarkSlateGray  | `#2F4F4F` |
| <svg width="50" height="20"><rect width="50" height="20" style="fill:black" /></svg> | Black  | `#000000` |
