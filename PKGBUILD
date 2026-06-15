# Maintainer: callmetango
# Contributor: Felix Yan <felixonmars@archlinux.org>
# Contributor: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=sonic-frameworks-doctools
pkgver=6.27.0
pkgrel=1
pkgdesc='Documentation generation from docbook'
arch=(x86_64)
url='https://github.com/Sonic-DE/sonic-frameworks-doctools'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(docbook-xsl
         glibc
         karchive
         libstdc++
         libxml2
         libxslt
         qt6-base)
makedepends=(doxygen
             ki18n
             perl-uri
             qt6-tools
             sonic-frameworks-cmake-modules)
provides=(kdoctools)
conflicts=(kdoctools)
groups=(sonicde-frameworks)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/${pkgver}.tar.gz")
sha256sums=('e11c8f24e389787429b819645b763f35c8f8533ea48dc7318699070fae08866b')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF \
    -DDocBookXSL_DIR=/usr/share/xml/docbook/xsl-stylesheets-nons
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
