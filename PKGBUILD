# Maintainer: Jack Random <jack (at) random.to>

pkgname=abgx360
pkgver=1.0.6
pkgrel=2
pkgdesc="An app for checking Xbox 360 ISOs"
url="http://abgx360.cc/"
arch=('x86_64')
license=('unknown')
depends=('zlib' 'curl')
optdepends=('abgx360gui: a GUI for this tool')
source=("http://abgx360.cc/dl/${pkgname}-${pkgver}.tar.gz")
md5sums=('04b0c9e0461faa92ca5f8fac78bafe57')
install=abgx360.install

prepare() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  # abgx360.xecuter.com is somehow no longer working, so we'll switch to www.abgx360.cc for now
  sed -i 's/abgx360.net/www.abgx360.cc/g' src/abgx360.c
}

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  
  #./autogen.sh
  ./configure
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
