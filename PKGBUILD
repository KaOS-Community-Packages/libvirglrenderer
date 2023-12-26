pkgname=libvirglrenderer
pkgver=1.0.0
pkgrel=1
pkgdesc='An OpenGL renderer for virtual machines.'
arch=('x86_64')
url='https://gitlab.freedesktop.org/virgl/virglrenderer'
license=('MIT')
depends=('libdrm' 'libepoxy' 'mesa' 'libx11')
makedepends=('meson' 'git')
source=("git+https://gitlab.freedesktop.org/virgl/virglrenderer.git#tag=${pkgver}")
sha512sums=('SKIP')
src_name="virglrenderer"

build() {
    cd "${src_name}"
    meson setup build --prefix=/usr
    cd build
    meson compile
}

package() {
    install -Dm644 ../LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    cd "${src_name}/build"
    DESTDIR=${pkgdir} meson install
}
