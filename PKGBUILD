# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>
# Contributor: Antonio Rojas

pkgname=khotkeys
pkgver=5.8.0
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
sha256sums=('e13dfac7bbf795ddaf2137f55647a7e5bcc16f7f54a15a68298cd4d8903e4c1b'
            'SKIP')
validpgpkeys=('2D1D5B0588357787DE9EE225EC94D18F7F05997E'  # Jonathan Riddell
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
