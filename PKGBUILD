# Maintainer: Ionut Biru <ibiru@archlinux.org>

pkgname=openconnect
pkgver=3.01
pkgrel=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.infradead.org/pub/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('4d41c96f95a2bc5b355e89b845bc5bb7')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install

  install  -Dm0644 openconnect.8 "${pkgdir}"/usr/share/man/man8/openconnect.8
}
