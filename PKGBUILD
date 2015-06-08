# Author: Julien MISCHKOWITZ <wain@archlinux.fr>
# Author: tuxce <tuxce.net@gmail.com>

pkgname=yaourt
pkgver=1.5
pkgrel=1
pkgdesc="A pacman wrapper with extended features and AUR support"
arch=('any')
url="https://github.com/archlinuxfr/yaourt"
license=(GPL)
depends=('diffutils' 'pacman>=4.1' 'package-query>=1.4' 'gettext')
optdepends=('aurvote: vote for favorite packages from AUR'
      'customizepkg: automatically modify PKGBUILD during install/upgrade'
      'rsync: retrieve PKGBUILD from official repositories')
backup=('etc/yaourtrc')
source=(http://mir.archlinux.fr/~tuxce/releases/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('4e1ee5533a567868facf035851e531f6')

build() { 
  cd "$srcdir/$pkgname-$pkgver/"
  make PREFIX=/usr sysconfdir=/etc localstatedir=/var 
}

package() {
  cd "$srcdir/$pkgname-$pkgver/"
  make PREFIX=/usr sysconfdir=/etc localstatedir=/var DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
