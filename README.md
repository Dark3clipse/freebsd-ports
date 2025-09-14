# FreeBSD Ports Repository

This repository contains FreeBSD ports for the following utilities:

## 1. `docopts` (devel/docopts)

`docopts` is a command-line argument parser with an MIT license.  
This port provides a FreeBSD package for `docopts`, including the latest binary release.  

### Source Code

The source code for `docopts` is available at:  
[https://github.com/docopt/docopts](https://github.com/docopt/docopts)

### License

`docopts` is licensed under the **MIT License (MIT)**.

## 2. `reflink_dedupe` (sysutils/reflink_dedupe)

`reflink_dedupe` is a FreeBSD utility to deduplicate a filesystem using reflinks.  
It supports optional features such as:

- `FSWATCH` — File system monitoring using [`fswatch`](https://github.com/emcrisostomo/fswatch)  
- `ZPOOL` — Integration with ZFS pools

### Source Code

The source code for `reflink_dedupe` is available at:  
[https://github.com/Dark3clipse/reflink_dedupe](https://github.com/Dark3clipse/reflink_dedupe)

### License

`reflink_dedupe` is licensed under the **BSD 2-Clause License (BSD2CLAUSE)**.

---

## Installing the Ports

Clone this repository to your FreeBSD host and use the standard port commands:

Ensure the ports tree is available:
```
pkg install portsnap
portsnap fetch extract
```

Clone this port overlay:
```
git clone git@github.com:Dark3clipse/freebsd-ports.git /usr/local/freebsd-ports
```

Enable port overlay:
```
echo "OVERLAYS+= /usr/local/freebsd-ports" >> /etc/make.conf

mkdir -p /usr/ports/local/sysutils
ln -s /usr/local/freebsd-ports/sysutils/reflink_dedupe /usr/ports/local/sysutils/reflink_dedupe

mkdir -p /usr/ports/local/devel
ln -s /usr/local/freebsd-ports/devel/docopts /usr/ports/local/devel/docopts
```

Build the package
```
cd /usr/ports/local/sysutils/reflink_dedupe
make makesum
make fetch
```

Install the package
```
make install clean WITH_WATCHER=yes WITH_ZFS=yes
```

Configure the utility
```
sudo cp /usr/local/etc/reflink_dedupe.conf.sample /usr/local/etc/reflink_dedupe.conf
<edit the config>
```
