# Maintainer: Ionut Biru <ionut@archlinux.ro>

pkgname=openconnect
pkgver=2.11
pkgrel=1
pkgdesc="Open client for Cisco AnyConnect VPN"
arch=('i686' 'x86_64')
license=('GPL')
url="http://www.infradead.org/openconnect.html"
depends=('libxml2' 'openssl')
makedepends=('gconf' 'gtk2')
options=('!libtool')
source=(ftp://ftp.infradead.org/pub/${pkgname}/${pkgname}-${pkgver}.tar.gz)
sha256sums=('56471b06e9f4253cb5fc4e888442f52a1cba1aa4cea784c4094a98efa5fb81ab')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  sed -i "s|/usr/libexec|/usr/lib/openconnect|" Makefile || return 1
  make || return 1
  make DESTDIR="${pkgdir}" install || return 1

  install  -Dm0644 openconnect.8 "${pkgdir}"/usr/share/man/man8/openconnect.8 || return 1
}
