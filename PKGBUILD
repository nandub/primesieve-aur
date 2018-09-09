# Maintainer: nandub <nandub+arch@nandub.info>
# Contributor: Kim Walisch <kim.walisch@gmail.com>

pkgname=primesieve
pkgver=7.1
pkgrel=1
pkgdesc="A fast prime number generation program and C/C++ library"
url="https://primesieve.org/"
license=('BSD')
depends=(gcc-libs)
provides=('libprimesieve.a' 'libprimesieve.so')
makedepends=('cmake' 'help2man')
source=(https://github.com/kimwalisch/primesieve/archive/v$pkgver.tar.gz)
sha1sums=('293db5261e443df7147e760a9ca0b919982381c1')
arch=('i686' 'x86_64')

build() {
  cd $pkgname-$pkgver
  cmake -DCMAKE_INSTALL_PREFIX=$pkgdir/usr -DCMAKE_BUILD_TYPE=Release .
  make
}

package() {
  cd $pkgname-$pkgver
  make install

  install -Dm644 "README.md" "$pkgdir/usr/share/doc/$pkgname/README.md"
  install -Dm644 "COPYING" "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
