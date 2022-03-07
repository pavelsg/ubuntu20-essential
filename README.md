# Ubuntu Server 20.04 essentials

## Introduction

This repo is created to minimize packages installed on Ubuntu 20.04. This will cut your Ubuntu down to 217 packages out of 595 installed by default, reduce binaries size down by ~700Mb, and double the boot speed.
This repo defines packages which are critical to provide just following functions:
1. Boot properly
2. Run OpenSSH server
3. Working package manager (apt, dpkg)
4. Working filesystem (fdisk, LVM, ext4, xfs)
5. Basic text processing (sed, gawk, grep, vim-tiny)

Apart from the above, all other functionality will require installing additional packages using apt.

## Motivation
1. Reduce OS image size (which might be critical for saturated links)
2. Increase boot speed
3. Reduce attack surface
4. Reduce maintenance effort on OS packages/libraries updates
5. Reduce chance of compatibility issues

## How to use

1. Install Ubuntu 20.04 with just SSH Server pre-installed
2. Login via ssh
3. Sudo to root
4. Download https://raw.githubusercontent.com/pavelsg/ubuntu20-minimal/main/ubuntu-20.04-server-essentials
5. Run ```apt list --installed | sed 's/\/.*//' | sort > installed_packages```
6. Run ```comm ubuntu-20.04-server-essentials installed_packages -13 > packages_to_remove```
7. **Review and update packages_to_remove according to your needs**
8. Run **at your own risk** ```apt-get purge $(cat packages_to_remove)```
9. Done! Now you have no any other packages except for the ones essential to boot into barely usefull Ubuntu 20.04 distribution

## Warranty

This repo comes with no warranties at all. Use at your own risk. Not recommended to run on live systems (recommended only for new systems).

## Testing

Tested on VirtualBox VM

## TO DO:

1. Test on bare metal
2. Test on other hypervisors (VMware, Hyper-V, XEN)
4. Test on could providers (AWS, Azure, GCP)

