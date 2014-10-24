# Maintainer: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Antonio Rojas

pkgname=khotkeys
pkgver=5.1.0.1
pkgrel=2
pkgdesc='KHotKeys'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/workspace/khotkeys'
license=('LGPL')
depends=('plasma-workspace')
makedepends=('extra-cmake-modules' 'kdoctools' 'python')
conflicts=('kdebase-workspace')
source=("http://download.kde.org/stable/plasma/5.1.0/$pkgname-$pkgver.tar.xz"
        'fix-shortcuts.patch')
md5sums=('50123581b85df285bd2ea5d7f722e7d0'
         'db701291f62d72780ec0cfd6c18635c6')

prepare() {
  mkdir -p build

  cd $pkgname-5.1.0
  patch -p1 -i "${srcdir}"/fix-shortcuts.patch
}

build() {
  cd build
  cmake ../$pkgname-5.1.0 \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib \
    -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
