pkgname=easyarch-calamares
pkgver=2.1.0
pkgrel=1
pkgdesc="EasyArch Installer"
arch=('x86_64')
url=https://github.com/easyarch-iso
source=("$pkgname-$pkgver::git+$url/easyarch-calamares.git")
depends=(
    'parted'
    'kconfig'
    'kcoreaddons'
    'kiconthemes'
    'ki18n'
    'kio'
    'solid'
    'yaml-cpp'
    'kpmcore'
    'hwinfo'
    'qt5-svg'
    'polkit-qt5'
    'gtk-update-icon-cache'
    'plasma-framework'
    'qt5-xmlpatterns'
    'squashfs-tools'    
    'qt5-translations'
    'boost'
    'boost-libs'
    'mkinitcpio-openswap'
    'ckbcomp'
    'python-yaml'
    'python-jsonschema'
)
makedepends=(
    'cmake'
    'extra-cmake-modules'
    'qt5-tools'
)
sha256sums=('SKIP')
# options=(!strip)
build() {
    cd $srcdir/$pkgname-$pkgver
    mkdir -pv build
    cd build
    cmake   -DCMAKE_BUILD_TYPE:STRING=Release \
            -DWITH_PYTHON:BOOL=TRUE \
            -DWITH_PYTHONQT:BOOL=FALSE \
            -DWITH_KF5DBus:BOOL=FALSE \
            ..
    make -j2
}
package() {
    cd $srcdir/$pkgname-$pkgver/build
    make DESTDIR="$pkgdir" install
}
