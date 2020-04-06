+++
title = "Disable munin"

date = 2020-01-02
toc = true  # Show table of contents? true/false
type = "docs"  # Do not modify.
weight = 62

[menu.docs]
  parent = "tips"
  weight = 62

+++
Munin was used to provide graphics in the [XiVO](https://www.xivo.solutions) web interface. These Graphics are no longer available in the current Wazo interface.

On a device with limited resources it is appropriate to deactivate their generation.

This is done by commenting out all the lines in the file `/etc/cron.d/munin` and `/etc/cron.d/munin-node`
