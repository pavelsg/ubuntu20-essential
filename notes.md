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




at
bcache-tools
btrfs-progs
byobu
fonts-ubuntu-console
git
htop
iptables
libsodium23
lshw
manpages
mdadm
motd-news-config
multipath-tools
open-iscsi
open-vm-tools
overlayroot
pollinate
powermgmt-base
screen
snapd
software-properties-common
sosreport
update-manager-core
whiptail
libfl2



apparmor
curl
ethtool
git-man
kpartx
liberror-perl
libfl2
libip6tc2
libisns0
libmspack0
libnetfilter-conntrack3
libnftnl11
liburcu6
libxmlsec1-openssl
lxd-agent-loader
pastebinit
patch
pciutils
python3-newt
python3-pexpect
python3-requests-unixsocket
python3-setuptools
python3-software-properties
run-one
sg3-utils-udev
squashfs-tools
tmux
ubuntu-advantage-tools
ubuntu-release-upgrader-core
usbutils
zerofree




plymouth


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
dash
cloud-guest-utils
cloud-initramfs-copymods
init
isc-dhcp-client
cloud-initramfs-dyn-netconf
lvm2
systemd-timesyncd
dash
gawk
less
xfsprogs
gpgv
base-files
bsdutils
logsave
ncurses-base
xxd
vim-common
vim-tiny

^apt-.*
^busybox-initramfs$
^bzip2$
^cpio$
^debconf$
^groub-.*
^initramfs-.*
^login$
^lz4$
^networkd-dispatcher$
^openssh-.*server
^openssl$
^procps$
^tar$
^tzdata$
^ubuntu-keyring$
^udev$
^xz-utils$
^apt$
^iproute2$
^linux-firmware$
^sed$

1 deps:
----
alsa-topology-conf
alsa-ucm-conf
bolt
bsdmainutils
bsdutils
crda
debconf-i18n
dirmngr
distro-info-data
dmidecode
dosfstools
eject
file
fwupd-signed
fwupd
gpgsm
isc-dhcp-common
iucode-tool
iw
krb5-locales
logrotate
ncurses-term
ntfs-3g
os-prober
parted
perl
psmisc
publicsuffix
sound-theme-freedesktop
thermald
tpm-udev
upower
usbmuxd
uuid-runtime
vim-runtime
wget
wireless-regdb
xdg-user-dirs


----

cron
fuse
gdisk
liblocale-gettext-perl
policykit-1
**1 deps**:
ca-certificates
shared-mime-info
**2 deps:**
xauth

---
bash-completion
install-info






```

for pkgname in `apt list --installed | sed 's/\/.*//'`; do echo ${pkgname}; apt-cache rdepends --no-suggests --no-conflicts --no-breaks --no-replaces --no-enhances --installed ${pkgname} | sort | uniq > ${pkgname}.rdeps; done
 
 grep -c -e "^  " *.rdeps | grep ":0" | sed 's/\..*//' | grep -v -f ../exceptions.grep | xargs -n 1 apt-cache show | grep -e "^Package\|^Description-en\|^\ "|less
 
 for pkgname in `cat layer3`; do apt purge ${pkgname}; done
```




remaining packages
```
adduser/focal,now 3.118ubuntu2 all [installed]
apt-utils/focal-updates,now 2.0.6 amd64 [installed]
apt/focal-updates,now 2.0.6 amd64 [installed]
base-files/focal-updates,now 11ubuntu5.5 amd64 [installed]
base-passwd/focal,now 3.5.47 amd64 [installed]
bash/focal-updates,now 5.0-6ubuntu1.1 amd64 [installed]
bsdutils/focal-updates,focal-security,now 1:2.34-0.1ubuntu9.3 amd64 [installed,automatic]
busybox-initramfs/focal-updates,focal-security,now 1:1.30.1-4ubuntu6.4 amd64 [installed,automatic]
bzip2/focal,now 1.0.8-2 amd64 [installed]
cloud-guest-utils/focal,now 0.31-7-gd99b2d76-0ubuntu1 all [installed]
cloud-initramfs-copymods/focal-updates,now 0.45ubuntu2 all [installed]
cloud-initramfs-dyn-netconf/focal-updates,now 0.45ubuntu2 all [installed]
coreutils/focal,now 8.30-3ubuntu2 amd64 [installed,automatic]
cpio/focal-updates,focal-security,now 2.13+dfsg-2ubuntu0.3 amd64 [installed]
dash/focal,now 0.5.10.2-6 amd64 [installed]
dbus-user-session/focal-updates,focal-security,now 1.12.16-2ubuntu2.1 amd64 [installed,automatic]
dbus/focal-updates,focal-security,now 1.12.16-2ubuntu2.1 amd64 [installed,automatic]
debconf/focal,now 1.5.73 all [installed]
debianutils/focal,now 4.9.1 amd64 [installed,automatic]
diffutils/focal,now 1:3.7-3 amd64 [installed]
dmeventd/focal,now 2:1.02.167-1ubuntu1 amd64 [installed,automatic]
dmsetup/focal,now 2:1.02.167-1ubuntu1 amd64 [installed,automatic]
dpkg/focal,now 1.19.7ubuntu3 amd64 [installed,automatic]
e2fsprogs/focal,now 1.45.5-2ubuntu1 amd64 [installed]
fdisk/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
findutils/focal,now 4.7.0-1ubuntu1 amd64 [installed]
gawk/focal,now 1:5.0.1+dfsg-1 amd64 [installed,automatic]
gcc-10-base/focal-updates,focal-security,now 10.3.0-1ubuntu1~20.04 amd64 [installed,automatic]
gettext-base/focal,now 0.19.8.1-10build1 amd64 [installed,automatic]
gir1.2-glib-2.0/focal-updates,now 1.64.1-1~ubuntu20.04.1 amd64 [installed,automatic]
gpgv/focal-updates,now 2.2.19-3ubuntu2.1 amd64 [installed,automatic]
grep/focal,now 3.4-1 amd64 [installed]
grub-common/focal-updates,now 2.04-1ubuntu26.13 amd64 [installed,automatic]
grub-gfxpayload-lists/focal,now 0.7 amd64 [installed,automatic]
grub-pc-bin/focal-updates,now 2.04-1ubuntu26.13 amd64 [installed,automatic]
grub-pc/focal-updates,now 2.04-1ubuntu26.13 amd64 [installed,automatic]
grub2-common/focal-updates,now 2.04-1ubuntu26.13 amd64 [installed,automatic]
gzip/focal,now 1.10-0ubuntu4 amd64 [installed]
hostname/focal,now 3.23 amd64 [installed]
init-system-helpers/focal,now 1.57 all [installed,automatic]
init/focal,now 1.57 amd64 [installed]
initramfs-tools-bin/focal-updates,now 0.136ubuntu6.7 amd64 [installed,automatic]
initramfs-tools-core/focal-updates,now 0.136ubuntu6.7 all [installed,automatic]
initramfs-tools/focal-updates,now 0.136ubuntu6.7 all [installed,automatic]
iproute2/focal,now 5.5.0-1ubuntu1 amd64 [installed]
irqbalance/focal,now 1.6.0-3ubuntu1 amd64 [installed]
isc-dhcp-client/focal-updates,focal-security,now 4.4.1-2.1ubuntu5.20.04.2 amd64 [installed]
klibc-utils/focal,now 2.0.7-1ubuntu5 amd64 [installed,automatic]
kmod/focal,now 27-1ubuntu2 amd64 [installed]
less/focal-updates,now 551-1ubuntu0.1 amd64 [installed]
libacl1/focal,now 2.2.53-6 amd64 [installed,automatic]
libaio1/focal,now 0.3.112-5 amd64 [installed,automatic]
libapparmor1/focal-updates,now 2.13.3-7ubuntu5.1 amd64 [installed,automatic]
libapt-pkg6.0/focal-updates,now 2.0.6 amd64 [installed,automatic]
libargon2-1/focal,now 0~20171227-0.2 amd64 [installed,automatic]
libatm1/focal,now 1:2.5.1-4 amd64 [installed,automatic]
libattr1/focal,now 1:2.4.48-5 amd64 [installed,automatic]
libaudit-common/focal,now 1:2.8.5-2ubuntu6 all [installed,automatic]
libaudit1/focal,now 1:2.8.5-2ubuntu6 amd64 [installed,automatic]
libblkid1/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
libbsd0/focal,now 0.10.0-1 amd64 [installed,automatic]
libbz2-1.0/focal,now 1.0.8-2 amd64 [installed,automatic]
libc-bin/focal-updates,focal-security,now 2.31-0ubuntu9.7 amd64 [installed,automatic]
libc6/focal-updates,focal-security,now 2.31-0ubuntu9.7 amd64 [installed,automatic]
libcap-ng0/focal,now 0.7.9-2.1build1 amd64 [installed,automatic]
libcap2-bin/focal,now 1:2.32-1 amd64 [installed,automatic]
libcap2/focal,now 1:2.32-1 amd64 [installed,automatic]
libcbor0.6/focal,now 0.6.0-0ubuntu1 amd64 [installed,automatic]
libcom-err2/focal,now 1.45.5-2ubuntu1 amd64 [installed,automatic]
libcrypt1/focal,now 1:4.4.10-10ubuntu4 amd64 [installed,automatic]
libcryptsetup12/focal-updates,focal-security,now 2:2.2.2-3ubuntu2.4 amd64 [installed,automatic]
libdb5.3/focal,now 5.3.28+dfsg1-0.6ubuntu2 amd64 [installed,automatic]
libdbus-1-3/focal-updates,focal-security,now 1.12.16-2ubuntu2.1 amd64 [installed,automatic]
libdebconfclient0/focal,now 0.251ubuntu1 amd64 [installed]
libdevmapper-event1.02.1/focal,now 2:1.02.167-1ubuntu1 amd64 [installed,automatic]
libdevmapper1.02.1/focal,now 2:1.02.167-1ubuntu1 amd64 [installed,automatic]
libdns-export1109/focal-updates,now 1:9.11.16+dfsg-3~ubuntu1 amd64 [installed,automatic]
libedit2/focal,now 3.1-20191231-1 amd64 [installed,automatic]
libefiboot1/focal-updates,now 37-2ubuntu2.2 amd64 [installed,automatic]
libefivar1/focal-updates,now 37-2ubuntu2.2 amd64 [installed,automatic]
libelf1/focal,now 0.176-1.1build1 amd64 [installed,automatic]
libestr0/focal,now 0.1.10-2.1 amd64 [installed,automatic]
libexpat1/focal-updates,focal-security,now 2.2.9-1ubuntu0.2 amd64 [installed,automatic]
libext2fs2/focal,now 1.45.5-2ubuntu1 amd64 [installed,automatic]
libfastjson4/focal,now 0.99.8-2 amd64 [installed,automatic]
libfdisk1/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
libffi7/focal,now 3.3-4 amd64 [installed,automatic]
libfido2-1/focal,now 1.3.1-1ubuntu2 amd64 [installed,automatic]
libfreetype6/focal-updates,focal-security,now 2.10.1-2ubuntu0.1 amd64 [installed,automatic]
libfuse2/focal,now 2.9.9-3 amd64 [installed,automatic]
libgcc-s1/focal-updates,focal-security,now 10.3.0-1ubuntu1~20.04 amd64 [installed,automatic]
libgcrypt20/focal-updates,focal-security,now 1.8.5-5ubuntu1.1 amd64 [installed,automatic]
libgirepository-1.0-1/focal-updates,now 1.64.1-1~ubuntu20.04.1 amd64 [installed,automatic]
libglib2.0-0/focal-updates,now 2.64.6-1~ubuntu20.04.4 amd64 [installed,automatic]
libglib2.0-data/focal-updates,now 2.64.6-1~ubuntu20.04.4 all [installed,automatic]
libgmp10/focal,now 2:6.2.0+dfsg-4 amd64 [installed,automatic]
libgnutls30/focal-updates,focal-security,now 3.6.13-2ubuntu1.6 amd64 [installed,automatic]
libgpg-error0/focal,now 1.37-1 amd64 [installed,automatic]
libgpm2/focal,now 1.20.7-5 amd64 [installed,automatic]
libgssapi-krb5-2/focal-updates,focal-security,now 1.17-6ubuntu4.1 amd64 [installed,automatic]
libhogweed5/focal-updates,focal-security,now 3.5.1+really3.5.1-2ubuntu0.2 amd64 [installed,automatic]
libicu66/focal-updates,focal-security,now 66.1-2ubuntu2.1 amd64 [installed,automatic]
libidn2-0/focal,now 2.2.0-2 amd64 [installed,automatic]
libip4tc2/focal,now 1.8.4-3ubuntu2 amd64 [installed,automatic]
libisc-export1105/focal-updates,now 1:9.11.16+dfsg-3~ubuntu1 amd64 [installed,automatic]
libjson-c4/focal-updates,focal-security,now 0.13.1+dfsg-7ubuntu0.3 amd64 [installed,automatic]
libk5crypto3/focal-updates,focal-security,now 1.17-6ubuntu4.1 amd64 [installed,automatic]
libkeyutils1/focal,now 1.6-6ubuntu1 amd64 [installed,automatic]
libklibc/focal,now 2.0.7-1ubuntu5 amd64 [installed,automatic]
libkmod2/focal,now 27-1ubuntu2 amd64 [installed,automatic]
libkrb5-3/focal-updates,focal-security,now 1.17-6ubuntu4.1 amd64 [installed,automatic]
libkrb5support0/focal-updates,focal-security,now 1.17-6ubuntu4.1 amd64 [installed,automatic]
liblvm2cmd2.03/focal,now 2.03.07-1ubuntu1 amd64 [installed,automatic]
liblz4-1/focal-updates,focal-security,now 1.9.2-2ubuntu0.20.04.1 amd64 [installed,automatic]
liblzma5/focal-updates,now 5.2.4-1ubuntu1 amd64 [installed,automatic]
libmnl0/focal,now 1.0.4-2 amd64 [installed,automatic]
libmount1/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
libmpdec2/focal,now 2.4.2-3 amd64 [installed,automatic]
libmpfr6/focal,now 4.0.2-1 amd64 [installed,automatic]
libncurses6/focal,now 6.2-0ubuntu2 amd64 [installed,automatic]
libncursesw6/focal,now 6.2-0ubuntu2 amd64 [installed,automatic]
libnetplan0/focal-updates,now 0.103-0ubuntu5~20.04.5 amd64 [installed,automatic]
libnettle7/focal-updates,focal-security,now 3.5.1+really3.5.1-2ubuntu0.2 amd64 [installed,automatic]
libnss-systemd/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed,automatic]
libnuma1/focal,now 2.0.12-1 amd64 [installed,automatic]
libp11-kit0/focal-updates,focal-security,now 0.23.20-1ubuntu0.1 amd64 [installed,automatic]
libpam-cap/focal,now 1:2.32-1 amd64 [installed,automatic]
libpam-modules-bin/focal-updates,now 1.3.1-5ubuntu4.3 amd64 [installed,automatic]
libpam-modules/focal-updates,now 1.3.1-5ubuntu4.3 amd64 [installed,automatic]
libpam-runtime/focal-updates,now 1.3.1-5ubuntu4.3 all [installed,automatic]
libpam-systemd/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed]
libpam0g/focal-updates,now 1.3.1-5ubuntu4.3 amd64 [installed,automatic]
libpcre2-8-0/focal,now 10.34-7 amd64 [installed,automatic]
libpcre3/focal,now 2:8.39-12build1 amd64 [installed,automatic]
libpng16-16/focal,now 1.6.37-2 amd64 [installed,automatic]
libprocps8/focal-updates,now 2:3.3.16-1ubuntu2.3 amd64 [installed,automatic]
libpython3-stdlib/focal,now 3.8.2-0ubuntu2 amd64 [installed,automatic]
libpython3.8-minimal/focal-updates,focal-security,now 3.8.10-0ubuntu1~20.04.2 amd64 [installed,automatic]
libpython3.8-stdlib/focal-updates,focal-security,now 3.8.10-0ubuntu1~20.04.2 amd64 [installed,automatic]
libreadline5/focal,now 5.2+dfsg-3build3 amd64 [installed,automatic]
libreadline8/focal,now 8.0-4 amd64 [installed,automatic]
libseccomp2/focal-updates,focal-security,now 2.5.1-1ubuntu1~20.04.2 amd64 [installed,automatic]
libselinux1/focal,now 3.0-1build2 amd64 [installed,automatic]
libsemanage-common/focal,now 3.0-1build2 all [installed,automatic]
libsemanage1/focal,now 3.0-1build2 amd64 [installed,automatic]
libsepol1/focal,now 3.0-1 amd64 [installed,automatic]
libsigsegv2/focal,now 2.12-2 amd64 [installed,automatic]
libsmartcols1/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
libsqlite3-0/focal-updates,focal-security,now 3.31.1-4ubuntu0.2 amd64 [installed,automatic]
libss2/focal,now 1.45.5-2ubuntu1 amd64 [installed,automatic]
libssl1.1/focal-updates,now 1.1.1f-1ubuntu2.10 amd64 [installed,automatic]
libstdc++6/focal-updates,focal-security,now 10.3.0-1ubuntu1~20.04 amd64 [installed,automatic]
libsystemd0/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed,automatic]
libtasn1-6/focal,now 4.16.0-2 amd64 [installed,automatic]
libtinfo6/focal,now 6.2-0ubuntu2 amd64 [installed,automatic]
libudev1/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed,automatic]
libunistring2/focal,now 0.9.10-2 amd64 [installed,automatic]
libuuid1/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
libwrap0/focal,now 7.6.q-30 amd64 [installed,automatic]
libxtables12/focal,now 1.8.4-3ubuntu2 amd64 [installed,automatic]
libyaml-0-2/focal,now 0.2.2-1 amd64 [installed,automatic]
libzstd1/focal-updates,focal-security,now 1.4.4+dfsg-3ubuntu0.1 amd64 [installed,automatic]
linux-base/focal-updates,now 4.5ubuntu3.7 all [installed,automatic]
linux-firmware/now 1.187.26 all [installed,upgradable to: 1.187.27]
linux-headers-5.4.0-100-generic/focal-updates,focal-security,now 5.4.0-100.113 amd64 [installed,automatic]
linux-headers-5.4.0-100/focal-updates,focal-security,now 5.4.0-100.113 all [installed,automatic]
linux-image-5.4.0-100-generic/focal-updates,focal-security,now 5.4.0-100.113 amd64 [installed,automatic]
linux-modules-5.4.0-100-generic/focal-updates,focal-security,now 5.4.0-100.113 amd64 [installed,automatic]
locales/focal-updates,focal-security,now 2.31-0ubuntu9.7 all [installed]
login/focal-updates,now 1:4.8.1-1ubuntu5.20.04.1 amd64 [installed,automatic]
logsave/focal,now 1.45.5-2ubuntu1 amd64 [installed,automatic]
lsb-base/focal,now 11.1.0ubuntu2 all [installed,automatic]
lvm2/focal,now 2.03.07-1ubuntu1 amd64 [installed]
lz4/focal-updates,focal-security,now 1.9.2-2ubuntu0.20.04.1 amd64 [installed,automatic]
mime-support/focal,now 3.64ubuntu1 all [installed]
mount/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed]
ncurses-base/focal,now 6.2-0ubuntu2 all [installed]
ncurses-bin/focal,now 6.2-0ubuntu2 amd64 [installed]
netbase/focal,now 6.1 all [installed]
netplan.io/focal-updates,now 0.103-0ubuntu5~20.04.5 amd64 [installed]
networkd-dispatcher/focal-updates,now 2.1-2~ubuntu20.04.1 all [installed,automatic]
openssh-client/focal-updates,now 1:8.2p1-4ubuntu0.4 amd64 [installed]
openssh-server/focal-updates,now 1:8.2p1-4ubuntu0.4 amd64 [installed]
openssh-sftp-server/focal-updates,now 1:8.2p1-4ubuntu0.4 amd64 [installed,automatic]
passwd/focal-updates,now 1:4.8.1-1ubuntu5.20.04.1 amd64 [installed]
perl-base/focal-updates,focal-security,now 5.30.0-9ubuntu0.2 amd64 [installed,automatic]
procps/focal-updates,now 2:3.3.16-1ubuntu2.3 amd64 [installed]
python3-dbus/focal,now 1.2.16-1build1 amd64 [installed,automatic]
python3-gi/focal,now 3.36.0-1 amd64 [installed,automatic]
python3-minimal/focal,now 3.8.2-0ubuntu2 amd64 [installed,automatic]
python3-netifaces/focal,now 0.10.4-1ubuntu4 amd64 [installed,automatic]
python3-yaml/focal-updates,focal-security,now 5.3.1-1ubuntu0.1 amd64 [installed,automatic]
python3.8-minimal/focal-updates,focal-security,now 3.8.10-0ubuntu1~20.04.2 amd64 [installed,automatic]
python3.8/focal-updates,focal-security,now 3.8.10-0ubuntu1~20.04.2 amd64 [installed,automatic]
python3/focal,now 3.8.2-0ubuntu2 amd64 [installed]
readline-common/focal,now 8.0-4 all [installed,automatic]
rsyslog/focal-updates,now 8.2001.0-1ubuntu1.1 amd64 [installed]
sed/focal,now 4.7-1 amd64 [installed,automatic]
sensible-utils/focal,now 0.0.12+nmu1 all [installed]
sudo/focal-updates,focal-security,now 1.8.31-1ubuntu1.2 amd64 [installed]
systemd-sysv/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed,automatic]
systemd-timesyncd/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed,automatic]
systemd/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed,automatic]
sysvinit-utils/focal,now 2.96-2.1ubuntu1 amd64 [installed]
tar/focal-updates,focal-security,now 1.30+dfsg-7ubuntu0.20.04.1 amd64 [installed,automatic]
thin-provisioning-tools/focal,now 0.8.5-4build1 amd64 [installed,automatic]
tzdata/focal-updates,focal-security,now 2021e-0ubuntu0.20.04 all [installed]
ubuntu-keyring/focal-updates,now 2020.02.11.4 all [installed]
ucf/focal,now 3.0038+nmu1 all [installed,automatic]
udev/focal-updates,focal-security,now 245.4-4ubuntu3.15 amd64 [installed]
util-linux/focal-updates,focal-security,now 2.34-0.1ubuntu9.3 amd64 [installed,automatic]
vim-common/focal-updates,focal-security,now 2:8.1.2269-1ubuntu5.7 all [installed,automatic]
vim-tiny/focal-updates,focal-security,now 2:8.1.2269-1ubuntu5.7 amd64 [installed]
xfsprogs/focal,now 5.3.0-1ubuntu2 amd64 [installed]
xxd/focal-updates,focal-security,now 2:8.1.2269-1ubuntu5.7 amd64 [installed,automatic]
xz-utils/focal-updates,now 5.2.4-1ubuntu1 amd64 [installed,automatic]
zlib1g/focal-updates,now 1:1.2.11.dfsg-2ubuntu1.2 amd64 [installed,automatic]
```
