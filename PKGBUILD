# Maintainer: Christoph Drexler <chrdr at gmx dot at>

pkgname=leptonica
pkgver=1.68
pkgrel=1
pkgdesc="Software that is broadly useful for image processing and image analysis applications"
arch=('i686' 'x86_64')
url="http://www.leptonica.com/"
license=('custom')
depends=('glibc')
optdepends=('giflib:  for supporting gif files'
            'gnuplot: gnuplot support'
            'libjpeg: for supporting jpeg files'
            'libpng:  for supporting png files'
            'libtiff: for supporting tiff files'
            'webp:    for supporting webp files'
            'zlib:    for supporting compressed files')
source=(http://www.leptonica.com/source/${pkgname}-${pkgver}.tar.gz)
md5sums=('5cd7092f9ff2ca7e3f3e73bfcd556403')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}

  ./configure --prefix=/usr

  make
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install

  install -D ${srcdir}/${pkgname}-${pkgver}/${pkgname}-license.txt ${pkgdir}/usr/share/licenses/${pkgname}/${pkgname}-license.txt
}
