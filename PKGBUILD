# Maintainer: Felix Yan <felixonmars@archlinux.org>
# Maintainer: Antonio Rojas <arojas@archlinux.org>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=khotkeys
pkgver=5.27.6
_dirver=$(echo $pkgver | cut -d. -f1-3)
pkgrel=1
pkgdesc='KHotKeys'
arch=(x86_64)
url='https://kde.org/plasma-desktop/'
license=(LGPL)
depends=(plasma-workspace kdelibs4support)
makedepends=(extra-cmake-modules kdoctools kdesignerplugin kinit)
groups=(plasma)
source=(https://download.kde.org/stable/plasma/$_dirver/$pkgname-$pkgver.tar.xz{,.sig})
sha256sums=('dbc7ec600e0450901648e6513f25f7c1ccad6798ce38b70437258daa6d833d7e'
            'SKIP')
validpgpkeys=('E0A3EB202F8E57528E13E72FD7574483BB57B18D'  # Jonathan Esk-Riddell <jr@jriddell.org>
              '0AAC775BB6437A8D9AF7A3ACFE0784117FBCE11D'  # Bhushan Shah <bshah@kde.org>
              'D07BD8662C56CB291B316EB2F5675605C74E02CF'  # David Edmundson <davidedmundson@kde.org>
              '1FA881591C26B276D7A5518EEAAF29B42A678C20') # Marco Martin <notmart@gmail.com>

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
