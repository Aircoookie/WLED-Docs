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
1D expansion: maps a 1D effect to a 2D pattern

### Segment to Logical
Maps segments to a matrix where (0,0) is always topleft and (width, height) always bottom right.
Non serpentine

### Ledmaps
Shuffles leds
Both for 1 and 2D

Code: uses customMappingTable

### Logical to Physical
Takes into account Panel setup and Led panel layout as defined in 2D Configuration (e.g. 1st panel, 1st led, serpentine)

Code: uses customMappingTable

### Physical to Busses
One or multiple GPIO ports

## Fork specific info

### WLED SR
* No JSON mapping as expand1D not implemented 

### WLED AC

* No JSON mapping yet although it's based on an idea from AirCoookie 
* Ledmaps only for 1D, 2D not implemented (PR pending)
