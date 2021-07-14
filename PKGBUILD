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
    'cyberlinux-lite-profile'      # lite
    'cyberlinux-server-profile'    # server
    'cyberlinux-netbook-profile'   # netbook
    'cyberlinux-theater-profile'   # theater
    'cyberlinux-desktop-profile'   # shell
    'cyberlinux-laptop-profile'    # laptop
)
pkgver=0.0.10
pkgrel=1
pkgdesc='Configuration files for cyberlinux'
arch=('any')
url="https://github.com/phR0ze/cyberlinux/aur/cyberlinux-profile"
license=('MIT')

pkg() {
  local name=$1
  shopt -s dotglob
  shopt -s extglob
  pkgdesc="Configuration for the cyberlinux ${name} deployment"

  cd $srcdir/../profiles/$name

  # Install profile files
  while IFS='' read -r -d '' x; do
    msg2 "Installing $x"
    mkdir -p "$pkgdir/$(dirname $x)"
    cp -dr "$x" "$pkgdir/$x"
  done < <(find . -type f -print0 -o -type l -print0)
}

package_cyberlinux-profile()
{
  pkg core
}

package_cyberlinux-shell-profile()
{
  depends=('cyberlinux-profile')
  pkg shell
}

package_cyberlinux-lite-profile()
{
  depends=('cyberlinux-shell-profile')
  pkg lite
}

package_cyberlinux-server-profile()
{
  depends=('cyberlinux-lite-profile')
  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-laptop-profile' 'cyberlinux-netbook-profile' 'cyberlinux-theater-profile')
  pkg lite
}

package_cyberlinux-theater-profile()
{
  depends=('cyberlinux-lite-profile')
  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-laptop-profile' 'cyberlinux-netbook-profile' 'cyberlinux-server-profile')
  pkg theater
}

package_cyberlinux-netbook-profile()
{
  depends=('cyberlinux-lite-profile')
  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-laptop-profile' 'cyberlinux-server-profile' 'cyberlinux-theater-profile')
  pkg netbook
}

package_cyberlinux-desktop-profile()
{
  depends=('cyberlinux-lite-profile')
  conflicts=('cyberlinux-server-profile' 'cyberlinux-laptop-profile' 'cyberlinux-netbook-profile' 'cyberlinux-theater-profile')
  install=desktop.install
  pkg desktop
}

package_cyberlinux-laptop-profile()
{
  depends=('cyberlinux-lite-profile')
  conflicts=('cyberlinux-desktop-profile' 'cyberlinux-server-profile' 'cyberlinux-netbook-profile' 'cyberlinux-theater-profile')
  pkg laptop
}
