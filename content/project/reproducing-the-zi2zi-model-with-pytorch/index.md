---
slides: ""
url_pdf: ""
summary: The 19th Asian Games Hangzhou 2022, let's play together!
url_video: ""
date: 2023-10-15T06:05:45.626Z
external_link: ""
url_slides: ""
title: Using zi2zi model to assist Chinese font design
tags:
  - Poster
links:
  - icon: link
    icon_pack: fas
    name: Link
    url: https://kaonashi-tyc.github.io/2017/04/06/zi2zi.html
image:
  caption: ""
  focal_point: Smart
  filename: network-1-.png
url_code: ""
---
zi2zi(字到字, meaning from character to character) is an application and extension of the recent popular [pix2pix](https://github.com/phillipi/pix2pix) model to Chinese characters. It can tackling the same problem of style transfer between Chinese fonts.This is the first open source model I came across for style transfer between fonts. With the contribution of author Yuchen Tian, I tried to run it on my own machine and train it on my own dataset.

{{< figure src="project/zi2zi use-01.jpg" caption="Process >}}

Combined with the Chinese font works I originally designed to run and test the model, in the actual use process, it was found that the sample size required by the model was still very large, and it required one-to-one paired data sets. Therefore, after the end of the project, I set my eyes on CycleGan, which did not need paired data sets.