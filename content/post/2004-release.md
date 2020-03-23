---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Sparrow 20.04 Released"
subtitle: ""
summary: ""
authors: []
tags: [sparrow, wazo, release, news]
categories: [release]
date: 2020-03-23T15:08:47+01:00
lastmod: 2020-03-23T15:08:47+01:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
I am proud to announce the release of sparrow version 20.04.

## Changelog

The software release notes are the same as Wazo platform and available here: [20.02](https://wazo-platform.org/blog/release-review-2002), [20.03](https://wazo-platform.org/blog/release-review-2003) and [20.04](https://wazo-platform.org/blog/release-review-2004).

## News

There will be no build of version 20.02 and 20.03, I've been very busy lately.

In the future I don't think I will build exactly all the releases of wazo, but maybe only 1 out of 2.

To prepare this release I worked on scripts to manage the addition of packages to the repository.
The next releases will require less manual configuration and will be done identically.

I've made some changes to the way I manage git repositories that require modifications to the wazo's ones.
For more traceability, each release is now tagged in git : see [asterisk fork](https://github.com/benasse/asterisk/releases) and [wazo-dist fork](https://github.com/benasse/wazo-dist/releases)

## Upgrade

The update procedure is identical to Wazo.
You just have to launch `wazo-upgrade`

## Bug fixes

A [bug](https://github.com/benasse/sparrow/issues/7) preventing installation via ansible was found and fixed.

Do not hesitate to open issues on github.
