# Notes on installing ScarletDME

Adapted from https://nivethan.dev/devlog/notes-on-scarletdme.html

Start with Debian 11

Install:

```
apt install git
dpkg --add-architecture i386
apt update
apt install libc6-dev-i386 make libcrypt1-dev:i386
git clone https://github.com/geneb/ScarletDME.git
cd ScarletDME
groupadd qmusers
useradd -c "qmsys" -d /home/qmsys -s /bin/sh qmsys
usermod -a -G qmusers qmsys
usermod -a -G qmusers root
make
make install
make datafiles
cp scarlet.conf /etc/
```

Start ScarletDME:
```
/usr/qmsys/bin/qm -start
```

Start the TCL:
```
cd /usr/qmsys
export TERM=vt100
bin/qm
```