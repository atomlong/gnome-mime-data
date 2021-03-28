# Maintainer: Brian Bidulock <bidulock@openss7.org>
pkgname=gnome-mime-data
pkgver=2.18.0
pkgrel=8
pkgdesc="The base MIME and Application database for GNOME"
arch=('any')
url=http://www.gnome.org
license=('GPL')
makedepends=('intltool')
depends=('shared-mime-info')
source=("https://download.gnome.org/sources/$pkgname/${pkgver%.0}/$pkgname-$pkgver.tar.bz2"
		config.guess
        config.sub)
sha256sums=('37196b5b37085bbcd45c338c36e26898fe35dd5975295f69f48028b1e8436fd7'
			'7d1e3c79b86de601c3a0457855ab854dffd15163f53c91edac54a7be2e9c931b'
			'0c6489c65150773a2a94eebaa794b079e74a403b50b48d5adb69fc6cd14f4810')

prepare() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  cp -vf ${srcdir}/config.guess	${srcdir}/${pkgname}-${pkgver}/
  cp -vf ${srcdir}/config.sub	${srcdir}/${pkgname}-${pkgver}/
}

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr --sysconfdir=/etc
  make V=0
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
