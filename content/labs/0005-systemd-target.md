---
layout: lab
title: Systemd Targets Overview
permalink: /lab/systemd/targetsoverview
module: Systemd
---

A systemd target is a set of systemd units that should be started to reach a desire state.

View the dependencies of the multi-user target.

```
systemctl list-dependencies multi-user.target | grep target
```

Get an overview of all available targets.

```
systemctl list-units --type=target --all
```

Get an overview of all targets installed on disk

```
systemctl list-unit-files --type=target --all
```

When the system starts and control is passed over to systemd from the initramfs, systemd will try to activate the default.target. default.target is a sym link from `/etc/systemd/system/default.target` to `multi-user.target.`

Check the current default target using `systemctl`.

```
systemctl get-default
```

You can set the the default target by using the `set-default` command.