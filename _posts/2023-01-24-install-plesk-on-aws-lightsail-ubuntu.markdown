---
title: Install Plesk on AWS Lightsail Ubuntu
author: mdomocos
date: 2023-01-24 16:15:00 +0200
categories: [Blogging]
tags: [aws, ubuntu, linux, lightsail, plesk]
math: true
mermaid: true
---

Since AWS is not providing us with and updated Ubuntu image (currently Ubuntu 22.04.1),
we need to create a new Ubuntu 20.04 instance and then upgrade it.


To upgrade the new instance to Ubuntu 22.04.1 (or newer) run:

```shell
apt update
apt upgrade
do-release-upgrade
```

Follow the steps and after a reboot you will be running Ubuntu 22.04.1.

To install Plesk, use the
[One Click installer](https://docs.plesk.com/en-US/obsidian/deployment-guide/plesk-installation-and-upgrade-on-single-server/1click-plesk-installation/installing-plesk-for-linux-in-one-click.76444/)
by running the following command:


```shell
sh <(curl https://autoinstall.plesk.com/one-click-installer || wget -O - https://autoinstall.plesk.com/one-click-installer)
```

Login to Plesk UI without password by running as root:

```shell
plesk login
```
