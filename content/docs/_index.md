+++
title = "Getting started"
date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
+++
## What is Sparrow ?
Sparrow is an unofficial build for armhf architecture of the awesome <a href="https://wazo-platform.org\" target="_blank" >Wazo Platform</a>.
It allows you to host complete Open Source, and programable telephone system on a <a href="https://www.raspberrypi.org/" target="_blank" >Raspberry Pi</a>

## Who is behind Sparrow
Currently sparrow is maintained and hosted by [Benoît Stahl](https://github.com/benasse).

## Why Sparrow / Wazo ?

* **It’s free and open source**. Students, Geeks for home use and Small businesses will definitely appreciate this! Wazo-platform is free and open-source.
* **Simple editing**. Wazo platform  provides a web interface to configure telephone functionality.
* **Based on Debian**.
* **An impressive number of telephony features**.
  * Phone provisioning
  * Centralized directory
  * Graphical IVR
  * Call Permissions
  * Schedules
  * ...

## Running Sparrow is the same as running Wazo?
Using sparrow is exactly the same as using wazo.
For now the only limitation is that the Opus codec is disabled.

## What packages are distributed and where can I find the sources ?
Sparrow is based on exactly the same source code as Wazo available on [Github](https://github.com/wazo-platform).

However, some packages have been modified to be able to be compiled on arm processor or to allow the use of specific repositories.
The list of modified packages is available here:

* asterisk: https://github.com/benasse/asterisk/releases
* wazo-dist: https://github.com/benasse/wazo-dist/releases
