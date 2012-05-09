# Maintainer: Ionut Biru <ibiru@archlinux.org>

pkgname=openconnect
pkgver=3.18
pkgrel=1
epoch=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl' 'libproxy' 'vpnc')
makedepends=('intltool')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.infradead.org/pub/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('5a440ad946cfec0f1ee7ee5519081cf1')

build() {
  cd "$pkgname-$pkgver"
  ./configure --prefix=/usr \
      --disable-static
  make
}

package() {
  cd "$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}
