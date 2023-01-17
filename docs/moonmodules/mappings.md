---
title: Mappings
hide:
  # - navigation
  # - toc
---

## Introduction

## Mappings
Below is in processing order

### JSON mapping
AKA jmap
1D expansion: maps a 1D effect to a 2D pattern

From excel/vba <img width="181" alt="image" src="https://user-images.githubusercontent.com/1737159/188688306-b5a5e7d8-3172-43b8-9f53-778ff9a2df3b.png"> via /edit and <img width="98" alt="image" src="https://user-images.githubusercontent.com/1737159/188688993-34c73f35-b642-4120-b31d-c87ea58ea10e.png">
 to matrix <img width="160" alt="image" src="https://user-images.githubusercontent.com/1737159/188688601-73a9e7f8-34d9-463f-9ec3-1cacaea13d6b.png">

Files are here: [JSONMappings](https://github.com/MoonModules/WLED-Effects/tree/master/JSONMappings)

### Segment to Logical
Maps segments to a matrix where (0,0) is always topleft and (width, height) always bottom right.
Non serpentine

### Ledmaps
Shuffles leds
Both for 1 and 2D

Code: uses customMappingTable

See also [Advanced/Mappings](https://mm.kno.wled.ge/advanced/mapping/)

### Logical to Physical
Takes into account Panel setup and Led panel layout as defined in 2D Configuration (e.g. 1st panel, 1st led, serpentine)

Code: uses customMappingTable

### Physical to Busses
One or multiple GPIO ports

## Fork specific info

| Feature | [WLED SR 0.13](https://github.com/atuline/WLED/tree/dev) | [MoonModules WLED 0.14](https://github.com/MoonModules/WLED/tree/mdev) | [Upstream WLED 0.14](https://github.com/Aircoookie/WLED) |
|---|---|---|---|
JSON Mapping|No|Yes|No JSON mapping yet although it's based on an idea from AirCoookie 
Segment to Logical|Yes|Yes|Yes
Ledmaps|Yes|Yes|Ledmaps only for 1D, 2D not implemented (PR pending)
Logical to Physical|Yes|Yes|Yes
Physical to Busses|Yes|Yes|Yes

