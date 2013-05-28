# Maintainer: Ionut Biru <ibiru@archlinux.org>

pkgname=openconnect
pkgver=5.00
pkgrel=1
epoch=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'gnutls' 'libproxy' 'vpnc')
makedepends=('intltool' 'python2')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.infradead.org/pub/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('b3677a4b15f8c530615f4c42dadce275')

build() {
  cd $pkgname-$pkgver
  PYTHON=/usr/bin/python2 ./configure --prefix=/usr \
      --sbindir=/usr/bin \
      --disable-static
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
