

Install the ports tree:
```
pkg install portsnap
portsnap fetch extract
```

Clone this port overlay:
```
cd /usr/local
git clone git@github.com:Dark3clipse/freebsd-ports.git
cd freebsd-ports/sysutils/reflink_dedupe
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
```

Install the package
```
make install clean
```
