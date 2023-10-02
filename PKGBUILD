# Maintainer: nandub <nandub+arch@nandub.info>
# Contributor: Kim Walisch <kim.walisch@gmail.com>

pkgname=primesieve
pkgver=11.1
pkgrel=1
pkgdesc="A fast prime number generation program and C/C++ library"
url="https://github.com/kimwalisch/primesieve"
license=('BSD')
depends=('gcc-libs')
makedepends=('cmake')
source=("${pkgname}-${pkgver}.tar.gz::https://github.com/kimwalisch/primesieve/archive/v${pkgver}.tar.gz")
sha1sums=('0f8bafd657ba79f6809c0ff07f6513b875b46c99')
arch=('x86_64')

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DBUILD_STATIC_LIBS=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build

  install -Dm644 $pkgname-$pkgver/README.md -t "$pkgdir"/usr/share/doc/$pkgname/
  install -Dm644 $pkgname-$pkgver/COPYING -t "$pkgdir"/usr/share/licenses/$pkgname/
}
