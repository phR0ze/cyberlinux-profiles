#MIT License
#Copyright (c) 2017-2021 phR0ze
#
#Permission is hereby granted, free of charge, to any person obtaining a copy
#of this software and associated documentation files (the "Software"), to deal
#in the Software without restriction, including without limitation the rights
#to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
#copies of the Software, and to permit persons to whom the Software is
#furnished to do so, subject to the following conditions:
#
#The above copyright notice and this permission notice shall be included in all
#copies or substantial portions of the Software.
#
#THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
#IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
#FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
#AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
#LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
#OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
#SOFTWARE.

#-------------------------------------------------------------------------------
# Maintainer: phR0ze
#-------------------------------------------------------------------------------
pkgname=(
    'cyberlinux-core-profile'      # core
    'cyberlinux-shell-profile'     # shell
#    'cyberlinux-lite-profile'      # lite
#    'cyberlinux-server-profile'    # server
#    'cyberlinux-netbook-profile'   # netbook
#    'cyberlinux-theater-profile'   # theater
#    'cyberlinux-desktop-profile'   # shell
#    'cyberlinux-laptop-profile'    # laptop
)
pkgver=0.0.11
pkgrel=1
pkgdesc='Configuration for various cyberlinux profiles'
arch=('any')
url="https://github.com/phR0ze/cyberlinux/aur/cyberlinux-profiles"
license=('MIT')

pkg() {
  local name=$1
#  shopt -s dotglob
#  shopt -s extglob
#
#  cd $srcdir/../profiles/$name
#
#  # Install profile files
#  while IFS='' read -r -d '' x; do
#    msg2 "Installing $x"
#    mkdir -p "$pkgdir/$(dirname $x)"
#    cp -dr "$x" "$pkgdir/$x"
#  done < <(find . -type f -print0 -o -type l -print0)
}

package_cyberlinux-core-profile()
{
  pkgdesc="Smallest set of packages possible for a functioning container with bash"
  depends=(
    'bash'                    # GNU Bourne Again shell, depends_on: [readline, glibc, ncurses], size: 7321.00 KiB
    'bash-completion'         # Bash tab completion, size: 799.00 KiB
    'ca-certificates'         # CAcert.org root certificates, size: 7.05 KiB
    'ca-certificates-mozilla' # Mozilla's set of CA certificates, size: 923 KiB
    'ca-certificates-utils'   # Common CA certificates, size: 7 KiB
    'coreutils'               # Utils ls/cp/mv, depends_on: [glibc, acl, attr, gmp, libcap, openssl], size: 13.79 MiB
    'gcc-libs'                # GCC runtime libraries, depends_on: [glibc], size: 105.27 MiB
    'glibc'                   # GNU C Library, depends_on: [linux-api-headers, tzdata, filesystem], size: 41.40 MiB
    'gzip'                    # GNU compression utility, depof: locale-gen, group: [build-devel]
    'filesystem'              # Base Arch Linux files, depends_on: [iana-etc], size: 9.00 KiB
    'iana-etc'                # /etc/protocols and /etc/services provided by IANA, size: 3941.00 KiB
    'linux-api-headers'       # Kernel headers sanitized for use in userspace, size: 4168.00 KiB
    'lsb-release'             # LSB version query program, size: 17.00 Kib
    'ncurses'                 # System V curses emulation library, depends_on: [glibc, gcc-libs], size: 3645.00 KiB
    'readline'                # GNU readline library, depends_on: [glibc, ncurses], size: 731.00 KiB
    'sed'                     # GNU stream editor, depof: locale-gen, group: [build-devel], size: 1MB
    'tzdata'                  # Sources for time zone and daylight savings time data, size: 1861.00 KiB
  )
  pkg core
}

package_cyberlinux-shell-profile()
{
  pkgdesc="Full bootable shell environment"
  depends=(
    'cyberlinux-core-profile' # Smallest set of packages possible for a functioning container with bash

    # core-boot               # Minimal bootable base for any machine
    'sudo'                    # Elevate user commands on demand to root
    'systemd'                 # System and service manager
    'systemd-sysvcompat'      # Sysinit compat for systemd
    'gnutls'                  # required by systemd-resolved to work
    'gettext'                 # required by grub
    'intel-ucode'             # required for Intel Microcode update files to boot
    'cyberlinux-grub'         # required for Grub Booloader to boot

    # kernel-full
    'linux'                   # Linux kernel and supporting modules
    'linux-headers'           # Linux kernel headers

    # core-tools              # Basic linux shell tools e.g. ls, cp, mv, hostname, gzip, tar and vim
    'openssl'                 # Secure sockets layer and TLS, depends_on: [perl], size: 6.36 MiB
    'perl'                    # Perl language, depends_on: [gdbm, db, glibc], size: 52.00 MiB
    'inetutils'               # hostname, ftp, telnet
    'iproute2'                # ifcfg/ip other networking tools
    'net-tools'               # arp/ifconfig/iptunnel/netstat
    'procps-ng'               # pidof/pkill/ps/top/uptime etc..., size: 1MB
    'tar'                     # File store backup and transport utility, depof: k8s cp
    'vim'                     # Improved version of vi text editor, size: 28MB

    # mkinitcpio
    'mkinitcpio'              # Tools required for building initramfs for early boot environment
    'cracklib'                # Cryptography suite, depof: [shadow]
    'e2fsprogs'               # Ext2/3/4 filesystem utilities, depof: [shadow]
    'gawk'                    # GNU version of awk, depof: [mkinitcpio], group: [base-devel]
    'grep'                    # search text util, depof: [mkinitcpio], group: [build-devel]
    'findutils'               # find/xargs, depof: [mkinicpio, curl], group: [base-devel]
    'mkinitcpio-vt-colors'    # vt console colors
    'shadow'                  # Account mgmt e.g. passwd/useradd/usermod/groupadd, depof: [util-linux]
    'util-linux'              # blkid/fdisk/rename/cp etc..., depof: [mkinicpio, php-gd], group: [build-devel]

    # shell                   # Full shell environment
    'cronie'                  # Daemon for scheduling programs to run
    'openssh'                 # Open source SSH server/client
    'virtualbox-guest-utils-nox' # VirtualBox guest drivers/utilities w/out X support
    'virtualbox-guest-modules-arch' # VirtualBox guest kernel modules
    'ddrescue'                # GNU data recovery tool
    'testdisk'                # Checks and undeletes partitions + photorec

    # net                     # Smallest set of packages for networking debug
    'archlinux-keyring'       # Arch linux keyring for installing packages
    'htop'                    # Interactive process viewer, alt: top
    'iftop'                   # Display bandwidth usage on an interface
    'pacman'                  # Package manager with dependency support, group: [build-devel]
    'pacman-contrib'          # Pacman support configuration, depof: rankmirrors
    'pkgfile'                 # A pacman files and metadata explorer
    'which'                   # Show the full path of commnds, depof: .bashrc, group: [build-devel]
    'tar'                     # File store backup and transport utility
    'bindip'                  # Bind a service to a specifc IP Address, repo: CYBERLINUX
    'curl'                    # Adding curl command to pull in packer scripts
    'dnsutils'                # Network utilities dig/host/nslookup
    'gnu-netcat'              # Network piping application
    'iputils'                 # Network utils e.g. ping/tftpd
    'nfs-utils'               # Support programs for Network File Systems
    'nmap'                    # Network discovery and security auditing
    'rsync'                   # Remote file transfer sync utility
    'tcpdump'                 # Network monitoring and data acquisition
    'wget'                    # Retrieve files from the Web

    # system
    'dmidecode'               # Desktop Managment Interface table related utilities
    'efibootmgr'              # Tool to modify UEFI Firmware Boot Manager Variables, depof: installer
    'gcc'                     # GNU Compiler Collection, multilib: false, group: [base-devel]
    'gcc-multilib'            # GNU Compiler Collection, multilib: true, group: [base-devel]
    'gptfdisk'                # Text-mode paritioning tools e.g. sgdisk
    'haveged'                 # Entropy harvesting, depof: pacman-key --init
    'logrotate'               # Rotates system logs automatically
    'cyberlinux-screenfetch'  # CLI bash script to show system theme for screenshots, repo: CYBERLINUX

    # compression:
    'p7zip'                   # Comman-line file archiver for 7zip format, depof: thunar
    'unrar'                   # The RAR uncompression program
    'unzip'                   # Extract and view files in .zip archives
    'zip'                     # Zip file compression utilities

    # filesystem:
    'cdrkit'                  # CD/DVD burnig/extration and ISO creation
    'dosfstools'              # DOS filesystem utilities e.g. mkfs.fat, depof: installer
    'inxi'                    # System info display tool for CPUs/RAM/Kernel etc...
    'libisoburn'              # Libburn/libisofs/xorriso
    'lsof'                    # Lists open files for running processes
    'man-db'                  # A utility for reading man pages
    'man-pages'               # Linux man pages
    'moreutils'               # Linux utils e.g. parallel-moreutils
    'reptyr'                  # Attach running program to a new terminal
    'smartmontools'           # Control/monitor S.M.A.R.T. Drives
    'squashfs-tools'          # Tooling for squashfs like mksquashfs
    'tmux'                    # Terminal multiplexer built off screen
    'udisks2'                 # Enumerate and operate on storage devices
    'usbutils'                # USB device utilities including lsusb

    # develop:
    'arch-install-scripts'    # arch-chroot/genfstab/pacstrap
    'autoconf'                # Automatically configure source code, group: [base-devel]
    'automake'                # Automatically create Makefiles, group: [base-devel]
    'binutils'                # Manipulate binary and object files, group: [base-devel]
    'bison'                   # General purpose parser generator, group: [base-devel]
    'clang'                   # C language family frontend for LLVM, depof: chromium
    'delve'                   # A debugger for the Go Programming Language
    'devtools'                # Misc development tools including makepkg conf, depof: reduce 
    'diffutils'               # Patch file utility programs
    'dos2unix'                # Text file format converter
    'fakeroot'                # Tool for simulating supersuer privileges, group: [base-devel]
    'file'                    # File type identification utility, group: [base-devel]
    'flex'                    # Generate text-scanning programs, group: [base-devel]
    'gdb'                     # The GNU debugger
    'git'                     # Fast distributed version control system
    'go'                      # Compiler and tools for the Go programming lang
    'go-bindata'              # Embed any file as Go code }
    'go-tools'                # Developer tools for the Go programming lang
    'groff'                   # GNU trof text-formatting system, group: [base-devel]
    'jq'                      # Command line JSON processor, depof: kubectl
    'libtool'                 # Generic library support script, group: [base-devel]
    'lld'                     # Linker from the LLVM project, depof: chromium
    'llvm'                    # Low Level compiler infrastructure, depof: chromium
    'ltrace'                  # Tracks runtime library calls in dynamically linked programs
    'm4'                      # GNU macro processor, group: [base-devel]
    'make'                    # GNU utility to build programs, group: [base-devel]
    'patch'                   # Utility to apply patches to files, group: [base-devel]
    'pkg-config'              # System for managing library flags, group: [base-devel]
    'psmisc'                  # fuser/killall/pstree 
    'python-pip'              # The PyPA recommended tool for installing Python packages
    'ruby'                    # Ruby lang quick and easy programming
    'strace'                  # A diagnostic, debugging and instructional userspace tracer
    'texinfo'                 # Documentation for online information, group: [base-devel]
    'yq'                      # Command-line YAML processor - jq wrapper for YAML documents
  )
  pkg shell
}

#package_cyberlinux-lite-profile()
#{
#  depends=('cyberlinux-shell-profile')
#  pkg lite
#}
#
#package_cyberlinux-server-profile()
#{
#  depends=('cyberlinux-lite-profile')
#  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-laptop-profile' 'cyberlinux-netbook-profile' 'cyberlinux-theater-profile')
#  pkg server
#}
#
#package_cyberlinux-theater-profile()
#{
#  depends=('cyberlinux-lite-profile')
#  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-laptop-profile' 'cyberlinux-netbook-profile' 'cyberlinux-server-profile')
#  pkg theater
#}
#
#package_cyberlinux-netbook-profile()
#{
#  depends=('cyberlinux-lite-profile')
#  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-laptop-profile' 'cyberlinux-server-profile' 'cyberlinux-theater-profile')
#  pkg netbook
#}
#
#package_cyberlinux-desktop-profile()
#{
#  depends=('cyberlinux-lite-profile')
#  conflicts=('cyberlinux-server-profile' 'cyberlinux-laptop-profile' 'cyberlinux-netbook-profile' 'cyberlinux-theater-profile')
#  install=desktop.install
#  pkg desktop
#}
#
#package_cyberlinux-laptop-profile()
#{
#  depends=('cyberlinux-lite-profile')
#  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-server-profile' 'cyberlinux-netbook-profile' 'cyberlinux-theater-profile')
#  pkg laptop
#}
