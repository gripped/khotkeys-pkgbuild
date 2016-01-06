# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Antonio Rojas

pkgname=khotkeys
pkgver=5.5.3
pkgrel=1
pkgdesc='KHotKeys'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/kde/workspace/khotkeys'
license=('LGPL')
depends=('plasma-workspace')
makedepends=('extra-cmake-modules' 'kdoctools' 'python')
conflicts=('kdebase-workspace')
source=("http://download.kde.org/stable/plasma/${pkgver}/$pkgname-$pkgver.tar.xz")
md5sums=('f35d58f740037f393470ec2390642af1')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
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
