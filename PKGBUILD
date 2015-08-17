# $Id: PKGBUILD 206455 2014-02-26 20:00:34Z andrea $
# Maintainer: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Balló György <ballogyor+arch at gmail dot com>

pkgname=signon-qt5
pkgver=8.57
pkgrel=2
arch=('i686' 'x86_64')
pkgdesc=("Framework to provide credential storage and authentication service")
url="http://code.google.com/p/accounts-sso/"
license=('LGPL')
depends=('qt5-base' 'signon')
makedepends=('doxygen' 'graphviz')
options=('!emptydirs')
source=("http://signond.accounts-sso.googlecode.com/archive/8.57.tar.gz")
sha1sums=('SKIP')

build() {
  cd signond.accounts-sso-$pkgver
  qmake-qt5 PREFIX=/usr LIBDIR=/usr/lib
  make
}

package() {
  cd signond.accounts-sso-$pkgver
  make INSTALL_ROOT="$pkgdir" install

# Remove libraries and binaries provided by signon
  rm -r "$pkgdir"/{etc,usr/{bin,share,include/{signond,signon-{plugins,extension}},lib/{signon,pkgconfig/{s,S}*,libsignon-{plugins,extension}*}}}
}

