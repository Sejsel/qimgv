pkgname=qimgv
epoch=1
pkgver=1.0.3alpha
pkgrel=2
pkgdesc='Qt image viewer'
arch=('x86_64')
url='https://github.com/easymodo/qimgv'
license=('GPL-3.0-or-later')
depends=('glibc' 'hicolor-icon-theme' 'libgcc' 'libstdc++'
         'qt6-base' 'qt6-imageformats' 'qt6-svg')
optdepends=('kimageformats: support for additional image formats')
makedepends=('cmake')
source=()
sha256sums=()

build() {
    cmake -S "$startdir" -B "$srcdir/build" \
        -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DUSE_QT5=OFF \
        -DEXIV2=OFF \
        -DVIDEO_SUPPORT=OFF \
        -DOPENCV_SUPPORT=OFF
    cmake --build "$srcdir/build"
}

package() {
    DESTDIR="$pkgdir" cmake --install "$srcdir/build"
}
