# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Antonio Rojas

pkgname=khotkeys
pkgver=5.7.3
pkgrel=1
pkgdesc='KHotKeys'
arch=('i686' 'x86_64')
url='https://www.kde.org/workspaces/plasmadesktop/'
license=('LGPL')
depends=('plasma-workspace')
makedepends=('extra-cmake-modules' 'kdoctools' 'python' 'kdesignerplugin')
conflicts=('kdebase-workspace')
groups=(plasma)
source=("http://download.kde.org/stable/plasma/${pkgver}/$pkgname-$pkgver.tar.xz"{,.sig})
sha256sums=('67b992690fb9ae6299e440b48c7620460211cae932ab36ec87ab77c7850407f7'
            'SKIP')
validpgpkeys=('13C16D03EDE728514473AA73A506E6D4DD4D5088'  # Jonathan Riddell
              '348C8651206633FD983A8FC4DEACEA00075E1D76'  # KDE Neon
              'D07BD8662C56CB291B316EB2F5675605C74E02CF') # David Edmundson

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
