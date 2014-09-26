kernel-cleanup
==============

Safe old kernel removal for Ubuntu derivatives.

Copyright 2013, Rodrigo Balerdi.
Licensed under the [GNU General Public License (GPL) Version 3](http://www.gnu.org/licenses/gpl-3.0-standalone.html) or later.

Developed on Linux Mint, tested on Ubuntu and Kubuntu.

This script performs some sanity checks before making changes.

Features:

  * enumerates the installed kernel versions using dpkg
  * enumerates the installed kernel versions found in /boot
  * checks that kernel version lists match
  * checks that currently running kernel version is found in these lists
  * warns if the currently running kernel version is not the newest
  * only removes kernel versions older than the currently running kernel
  * dry-runs (no changes made) if executed without root privileges

Usage: kernel-cleanup [-hb] [-c COMMAND]
Identify and uninstall old kernels.
    -h          display this help and exit
    -b          batch mode (do not check for root user)
    -c COMMAND  command used to uninstall packages
                defaults to:
                    non-batch mode: apt-get purge %P
                    batch mode:     apt-get -y purge %P

