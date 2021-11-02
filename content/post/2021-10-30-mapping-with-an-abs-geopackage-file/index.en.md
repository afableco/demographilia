---
title: Mapping with an ABS GeoPackage file
author: Afableco
date: '2021-10-30'
draft: true
slug: mapping-with-an-abs-geopackage-file
categories: []
tags:
  - Spatial-demography
subtitle: ''
summary: ''
authors: []
lastmod: '2021-10-30T11:18:11+11:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

I want to improve my mapping skills in R. The [Australian Bureou of Statistics (ABS)](http://abs.gov.au) are now preparing spatial data in an open format called [GeoPackage](https://www.geopackage.org/), so I thought I would write a  post on how I used an ABS dataset to prepare a map. Just a quick work of warning: I plodded through this, so I will try and point out some of the traps I had to work through, but this  is not a  master class and my terminology is not going  to necessarily  align  with people that know what they are talking about.

In this post  I will cover off  on:

- where I sourced the data;
- which R packages I used;
- how I worked in my own data;
- things I learned along the way;
- problems that I needed to overcome.

xxxxxxxxxx    ``
