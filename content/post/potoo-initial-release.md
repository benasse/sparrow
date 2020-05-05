---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "First release of potoo"
subtitle: ""
summary: ""
authors: []
tags: [sparrow, wazo, release, news, potoo]
categories: [release]
date: 2020-05-05T12:12:31+01:00
lastmod: 2020-05-05T13:15:22+01:00
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
The first public release of potoo is available under AGPL-3.0 License.
Its Source code is available on [github](https://github.com/benasse/potoo).

Potoo is software that communicates with VoIP ecosystem and particularly well with Wazo engines.
It is coded in python, and allows from a http call to launch python script or ansible playbook.

The main objective of this project is to quickly (and perhaps badly) provide solutions to missing functionalities in a given ecosystem.

## Features
Currently potoo allows you to do 3 things:
1. Originate a call to a specified number

For compatibility with a maximum of system using asterisk (FreePBX, XiVO, vanilla asterisk, ... ), this function launches a `channel originate` via the cli asterisk.

In version 2 we will use the wazo APIs to make the call.
```
http://myhost:8001/originate/v1?dest_exten=1234&dest_context=my-dest-context&src_exten=777&src_context=my-src-context
http://myhost:8001/originate/v1?dest_exten=1234
```

2. Display the output of the `queue show` in the asterisk cli.

This simply allows supervisors to view the status of their queues.

Like the first functionality, it uses the asterisk cli and is therefore compatible with any asterisk-based system.
```
http://myhost:8001/queue?queue=myqueue
http://myhost:8001/queue_pretty?queue=myqueue
http://myhost:8001/queue
```

3. Change the system information of a Wazo engine

Currently modify the system information of a wazo engine is a pain.

To enhance this I wanted to create a web page that allows you to do it.

The web page displays a form and updates your system via a playbook that contains information.
```
http://myhost:8001/update_system_info
```
![update_system_info](/img/potoo-initial-release/update_system_info.png)

## Security Disclaimer
{{% alert warning %}}
The features provided by potoo focus on the result, however, they are not necessarily secure.

Use the software at your own risk.
{{% /alert %}}

## Contribute
New functionalities ideas are welcome, the contributions to the code are too.

Potoo is my first real project, don't hesitate to give feedback regarding code quality, or whatever.

## Installation on a Wazo engine
As root on your wazo engine:
1. `apt install -y wazo-plugind-cli`
2. `wazo-plugind-cli -c 'install git https://github.com/benasse/potoo'`
