# Contributor: Antonio Rojas <arojas@archlinux.org>

pkgname=pcmanfm-qt
pkgver=0.8.0
pkgrel=2
pkgdesc="LXQt file manager and desktop manager"
arch=('i686' 'x86_64')
url='http://lxqt.org/'
license=('LGPL')
groups=('lxqt')
depends=('libfm' 'qt5-x11extras' 'desktop-file-utils')
makedepends=('cmake' 'qt5-tools')
source=("http://lxqt.org/downloads/lxqt/$pkgver/$pkgname-$pkgver.tar.xz")
md5sums=('5d86e2ec63463e615c21b812397785ae')
install=$pkgname.install

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../$pkgname-$pkgver \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DCMAKE_INSTALL_LIBDIR=lib \
    -DUSE_QT5=ON
  make
}

package() {
  cd build
  make DESTDIR="$pkgdir" install
}
