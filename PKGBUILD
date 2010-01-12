# Maintainer: Ionut Biru <ionut@archlinux.ro>

pkgname=openconnect
pkgver=2.21
pkgrel=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl')
makedepends=('gconf' 'gtk2')
options=('!libtool')
source=(ftp://ftp.infradead.org/pub/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha256sums=('31485be950d9801ab4d103d3f346df7fd091475eef06f695c8078964e6571e78')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i "s|/usr/libexec|/usr/lib/networkmanager|" Makefile || return 1
  make || return 1
  make DESTDIR="${pkgdir}" install || return 1

  install  -Dm0644 openconnect.8 "${pkgdir}"/usr/share/man/man8/openconnect.8 || return 1
}
