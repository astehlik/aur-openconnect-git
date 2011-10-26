# Maintainer: Ionut Biru <ibiru@archlinux.org>

pkgname=openconnect
pkgver=3.13
pkgrel=1
epoch=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl' 'libproxy')
makedepends=('intltool')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.infradead.org/pub/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('4364a779bfce66de243f39eeb7a39c1f')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr \
      --disable-static
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
