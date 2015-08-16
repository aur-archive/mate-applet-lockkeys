# Maintainer : Martin Wimpress <code@flexion.org>

pkgname=mate-applet-lockkeys
pkgver=0.2.3
pkgrel=1
pkgdesc="A MATE panel applet that shows which of the CapsLock, NumLock and ScrollLock keys are on and which are off."
url="http://www.zavedil.com/mate-lock-keys-applet/"
arch=('i686' 'x86_64' 'armv6h' 'armv7h')
license=('GPL')
depends=('gtk2' 'mate-panel')
makedepends=('mate-common' 'mate-doc-utils' 'perl-xml-parser')
source=("http://www.zavedil.com/wp-content/uploads/2013/12/${pkgname}-${pkgver}.tar.gz")
md5sums=('84515b805609daf1998590ee5f1fcb6a')
install=${pkgname}.install

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --libexecdir=/usr/lib/${pkgname}
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
    rm -f "${pkgdir}/usr/share/glib-2.0/schemas/gschemas.compiled"
}
