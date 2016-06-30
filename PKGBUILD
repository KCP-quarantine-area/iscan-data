pkgname=iscan-data
pkgver=1.36.0
pkgrel=1
pkgdesc="EPSON Image Scan! data files"
arch=('x86_64')
url="http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX"
license=('GPL2')
depends=('libxslt')
source=("http://support.epson.net/linux/src/scanner/iscan/iscan-data_1.36.0-1.tar.gz")
sha256sums=('3a0a0075d0f7fcb0f482cbde2e74c9f6bee64268db32a4e6f470f1a6069117ba')

build() {
  cd "${pkgname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  cd "${pkgname}-${pkgver}"

  # install files
  make DESTDIR="${pkgdir}" install

  # install additional documentation files
  install -m 755 -d "${pkgdir}/usr/share/doc/${pkgname}"
  install -t "${pkgdir}/usr/share/doc/${pkgname}" \
    KNOWN-PROBLEMS NEWS SUPPORTED-DEVICES
}

