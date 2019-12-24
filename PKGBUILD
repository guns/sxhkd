# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Contributor: Bastien Dejean <nihilhill@gmail.com>

pkgname=sxhkd-nerv
pkgver=0
pkgrel=1
pkgdesc='Simple X hotkey daemon'
arch=(x86_64)
conflicts=(sxhkd)
groups=(nerv-alt)
url='https://github.com/guns/sxhkd'
license=(custom:BSD)
depends=(xcb-util-keysyms)
makedepends=(git xcb-util)

pkgver() {
    printf %s "$(git describe --long --tags | tr - .)"
}

build() {
    make -C "$startdir" PREFIX=/usr
}

package() {
    cd "$startdir"
    make PREFIX=/usr DESTDIR="$pkgdir" install
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
