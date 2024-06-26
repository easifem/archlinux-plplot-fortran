# Maintainer: Jan Kohnert <bughunter at jan-kohnert dot de>
# Contributor: Miguel de Val-Borro <miguel dot deval at gmail dot com>
# Contributor: James Tappin <jtappinatgmaildotcom>
# Contributor: Gergely Imreh <imrehgATgmailDOTcom>
# Contributor: Eric Belanger <eric@archlinux.org>
# Contributor: Vikas Sharma <vickysharma@gmail.com>
# Maintainer: Jan Kohnert <bughunter at jan-kohnert dot de>
# Contributor: Miguel de Val-Borro <miguel dot deval at gmail dot com>
# Contributor: James Tappin <jtappinatgmaildotcom>
# Contributor: Gergely Imreh <imrehgATgmailDOTcom>
# Contributor: Eric Belanger <eric@archlinux.org>
pkgname=plplot
pkgver=5.15.0
pkgrel=8
pkgdesc="A cross-platform software package for creating scientific plots"
arch=("i686" "x86_64")
url="http://plplot.sourceforge.net/"
license=(
    "LGPL-2.0-or-later"
    "GPL-2.0-or-later"
    "LicenseRef-custom"
)
depends=(
    "cairo"
    "gcc-libs"
    "glib2"
    "glibc"
    "java-runtime"
    "libtool"
    "libx11"
    "lua52"
    "pango"
    "python"
    "python-numpy"
    "python-pillow"
    "qhull"
    "qt5-base"
    "qt5-svg"
    "shapelib"
    "tcl"
    "tk"
    "wxwidgets-common"
    "wxwidgets-gtk3"
)
makedepends=(
    "cmake"
    "jdk-openjdk"
    "pkg-config"
    "python-setuptools"
    "swig"
)
optdepends=("bash")
options=("!libtool")
source=(
    "http://downloads.sourceforge.net/sourceforge/plplot/${pkgname}-${pkgver}.tar.gz"
    "plplot.patch"
)
sha512sums=(
    "54533245569b724a7ef90392cc6e9ae65873e6cbab923df0f841c8b43def5e4307690894c7681802209bd3c8df97f54285310a706428f79b3340cce3207087c8"
    "92da6a88fc626a56febb61d0fce3960ea17771e8eae4e881d708ac196ee2238909e2da07056c31e07c59ef75a7a627a629f2ca1a40ac58904bc44ff3ded042dc"
)

prepare() {
    cd "$pkgname-$pkgver"
    patch --forward --strip=1 --input="${srcdir}/plplot.patch"
}

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    if [ -d build ]; then
        rm -r build
    fi
    mkdir build
    cd build
    cmake -DCMAKE_INSTALL_PREFIX=/usr -DENABLE_ada=OFF -DENABLE_c=ON -DENABLE_cxx=ON -DENABLE_d=OFF \
        -DENABLE_fortran=ON -DENABLE_itcl=OFF -DENABLE_itk=OFF -DENABLE_java=ON -DENABLE_lua=ON \
        -DENABLE_ocaml=OFF -DENABLE_octave=OFF -DENABLE_pyqt5=OFF -DENABLE_python=ON -DENABLE_qt=ON \
        -DENABLE_tcl=ON -DENABLE_tk=ON -DENABLE_wxwidgets=ON -DPLD_wxwidgets=ON  ..

    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}/build"
    make DESTDIR="${pkgdir}" install
    install -D -m644 ../Copyright "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

