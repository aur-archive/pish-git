# Maintainer: Thomas Dwyer <devel@tomd.tel>

pkgname=pish-git
pkgver=v1.1
pkgrel=2
pkgdesc="An easy to use pinentry wrapper written in mksh"
arch=('any')
url="https://github.com/tdwyer/pish"
license=('MirOS')
depends=('mksh' 'pinentry')
makedepends=('git')
conflicts=('pish')
provides=('pish')
source=("$pkgname"::'git://github.com/tdwyer/pish.git')
sha256sums=('SKIP')

#
# Pish now is useing ksh for OpenBSD support
# However ksh is in AUR and mksh is community
# so frezzing Archlinux at version 1.1
#
#pkgver() {
#  cd "$srcdir/$pkgname"
#  # Use the tag of the last commit
#  git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
#}

package() {
  cd "$srcdir/$pkgname"
  git checkout tags/${pkgver}
  mkdir -p "$pkgdir/usr/bin"
  mkdir -p "$pkgdir/usr/share/man/man1"
  mkdir -p "$pkgdir/usr/share/licenses/pish"
  install -T -m 0755 pish "$pkgdir/usr/bin/pish"
  install -T -m 0644 pish.1.gz "$pkgdir/usr/share/man/man1/pish.1.gz"
  install -T -m 0644 LICENSE "$pkgdir/usr/share/licenses/pish/LICENSE"
}

# vim: ft=sh syn=sh et
