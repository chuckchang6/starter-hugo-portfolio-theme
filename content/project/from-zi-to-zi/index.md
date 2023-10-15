---
title: From zi to zi
subtitle: Using zi2zi model to assist font design
date: 2023-10-15T07:27:47.393Z
summary: Train my own zi2zi and try to use it in the font design process
draft: false
featured: false
tags:
  - AI
links:
  - icon_pack: fas
    icon: link
    url: https://kaonashi-tyc.github.io/2017/04/06/zi2zi.html
    name: Link
image:
  filename: featured.jpg
  focal_point: Smart
  preview_only: false
---
zi2zi(字到字, meaning from character to character) is an application and extension of the recent popular [pix2pix](https://github.com/phillipi/pix2pix) model to Chinese characters. It can tackling the same problem of style transfer between Chinese fonts.This is the first open source model I came across for style transfer between fonts. With the contribution of author Yuchen Tian, I tried to run it on my own machine and train it on my own dataset.

{{< figure src="project/zi2zi use-01.jpg" caption="Process" >}}

Combined with the Chinese font works I originally designed to run and test the model, in the actual use process, it was found that the sample size required by the model was still very large, and it required one-to-one paired data sets. Therefore, after the end of the project, I set my eyes on CycleGan, which did not need paired data sets.