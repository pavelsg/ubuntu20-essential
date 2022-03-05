1. Install Ubuntu 20.04 LTS with just SSHD service pre-installed
2. Disable UFW service


---

apt-rdepends
console-setup-linux
bind9-host
fdisk

pinentry-curses
python3-cffi-backend
python3-debconf
python3-pymacaroons
systemd-timesyncd

ubuntu-minimal
ubuntu-server
ubuntu-standard


busybox-static
bind9-libs
command-not-found
ed
friendly-recovery
ftp
hdparm
info
iputils-ping
iputils-tracepath
keyboard-configuration
language-selector-common
libapt-pkg-perl
locales
lsof
ltrace
man-db
mawk
mtr-tiny
nano
netcat-openbsd
pinentry-curses
plymouth-theme-ubuntu-text
popularity-contest
python3-cffi-backend
python3-pymacaroons
rsync
strace
*systemd-timesyncd
tcpdump
telnet
time
ubuntu-server
ufw
xkb-data

autoremove:
accountsservice apport-symptoms bc eatmydata gnupg-l10n gnupg-utils libaccountsservice0 libeatmydata1 libmaxminddb0 libnspr4 libnss3 libpcap0.8
  libpipeline1 libunwind8 libuv1 python3-attr python3-automat python3-blinker python3-click python3-colorama python3-commandnotfound python3-configobj
  python3-constantly python3-debian python3-entrypoints python3-gdbm python3-hamcrest python3-httplib2 python3-hyperlink python3-importlib-metadata
  python3-incremental python3-jinja2 python3-json-pointer python3-jsonpatch python3-jsonschema python3-jwt python3-lazr.uri python3-markupsafe
  python3-more-itertools python3-problem-report python3-pyasn1 python3-pyasn1-modules python3-pyrsistent python3-serial python3-simplejson python3-systemd
  python3-twisted-bin python3-wadllib python3-zipp python3-zope.interface

-- exceptions
locales
ncurses-bin
hostname
bind9-dnsutils
diffutils
sudo
rsyslog
linux-generic
findutils
base-passwd
bash
Cloud-init
dbus-user-session
fdisk
grep
gzip
irqbalance
sysvinit-utils
