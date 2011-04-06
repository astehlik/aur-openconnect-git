# Maintainer: Ionut Biru <ibiru@archlinux.org>

pkgname=openconnect
pkgver=2.26
pkgrel=1
epoch=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl')
makedepends=('gconf' 'gtk2')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.infradead.org/pub/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('e3c7605fed128efe39c2eb9400af6765')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i "s|/usr/libexec|/usr/lib/networkmanager|" Makefile
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install

  install  -Dm0644 openconnect.8 "${pkgdir}"/usr/share/man/man8/openconnect.8
}
