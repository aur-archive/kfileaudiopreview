# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kfileaudiopreview
pkgver=4.99.0
pkgrel=1
pkgdesc='KFile Audio Preview'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kfileaudiopreview'
license=('LGPL')
depends=('phonon-qt5' 'kio' 'kservice' 'kconfig')
makedepends=('extra-cmake-modules')
groups=('kf5-aids')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/portingAids/${pkgname}-${pkgver}.tar.xz")
md5sums=('dd1592936a8e7d0dcbba6948a9fa99ba')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
