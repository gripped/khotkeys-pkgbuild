# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Antonio Rojas

pkgname=khotkeys
pkgver=5.6.5
pkgrel=1
pkgdesc='KHotKeys'
arch=('i686' 'x86_64')
url='https://www.kde.org/workspaces/plasmadesktop/'
license=('LGPL')
depends=('plasma-workspace')
makedepends=('extra-cmake-modules' 'kdoctools' 'python' 'kdesignerplugin')
conflicts=('kdebase-workspace')
source=("http://download.kde.org/stable/plasma/${pkgver}/$pkgname-$pkgver.tar.xz"{,.sig})
sha256sums=('8adebc7dacf0c74d23eddd66a6ea8f16697d59020d09f9b6a9f68abd62bb4dff'
            'SKIP')
validpgpkeys=('13C16D03EDE728514473AA73A506E6D4DD4D5088') # Jonathan Riddell

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DKDE_INSTALL_LIBDIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
