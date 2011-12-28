# Maintainer: Ionut Biru <ibiru@archlinux.org>

pkgname=openconnect
pkgver=3.15
pkgrel=1
epoch=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl' 'libproxy')
makedepends=('intltool')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.infradead.org/pub/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('94245f4bac42a288100becab0b4ca29a')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr \
      --disable-static
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}
