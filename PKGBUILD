pkgname=paper-icon-theme-git
pkgver=0.r2.aca8802
pkgrel=1
pkgdesc="Paper is an icon theme for GTK based desktops and fits perfectly the paper-gtk-theme"
arch=('i686' 'x86_64')
url="https://github.com/snwh/paper-icon-theme"
license=('CC BY-SA 4.0')
depends=('librsvg')
makedepends=('git')
provides=('paper-icon-theme')
source=("$pkgname"::'git+https://github.com/snwh/paper-icon-theme.git')
# Because the sources are not static, skip Git checksum:
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  # Use the tag of the last commit
  printf "0.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$srcdir/$pkgname/Paper"
  install -d -m 755 "$pkgdir"/usr/share/icons/Paper
  rm -rf {.git,.gitignore,CONTRIBUTORS,COPYING,CREDITS,LICENSE.txt,README.md}
  cp -r . "$pkgdir"/usr/share/icons/Paper/
}
