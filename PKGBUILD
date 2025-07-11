# Maintainer: Levente Polyak <anthraxx[at]archlinux[dot]org>
# Contributor: Ionut Biru <ibiru@archlinux.org>
# Contributor: Felix Yan <felixonmars@archlinux.org>

pkgname=openconnect-git
conflicts=('openconnect')
pkgver=r4759.f17fe20
pkgrel=1
epoch=1
pkgdesc='Open client for Cisco AnyConnect VPN'
url='https://www.infradead.org/openconnect/'
arch=('x86_64')
license=('LGPL2.1')
depends=('libxml2' 'gnutls' 'libproxy' 'vpnc' 'krb5' 'lz4' 'pcsclite'
  'stoken' 'tpm2-tss' 'oath-toolkit' 'libproxy' 'libp11-kit'
  'xdg-utils'
  libstoken.so libtss2-esys.so libtss2-mu.so libtss2-tctildr.so
  libxml2.so libproxy.so libhogweed.so libp11-kit.so libpskc.so
  libgssapi_krb5.so libpcsclite.so)
makedepends=('intltool' 'python')
checkdepends=('python-flask')
optdepends=('python: tncc-wrapper')
provides=("openconnect=${pkgver}" 'libopenconnect.so')
options=('!emptydirs')
source=("$pkgname::git+https://gitlab.com/openconnect/openconnect.git#branch=master")
sha256sums=('SKIP')

pkgver() {
  cd "$pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

build() {
  pwd
  cd "$pkgname"
  ./autogen.sh
  PYTHON=/usr/bin/python \
    ./configure \
    --prefix=/usr \
    --sbindir=/usr/bin \
    --libexecdir=/usr/lib \
    --disable-static
  sed -i -e 's/ -shared / -Wl,-O1,--as-needed\0/g' libtool
  make
}

check() {
  cd ${pkgname}
  make check
}

package() {
  cd ${pkgname}
  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
