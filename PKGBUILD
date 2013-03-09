# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Your Name <youremail@domain.com>
pkgname='postgis'
pkgver='2.1.0SVN'
pkgrel=1
epoch=
pkgdesc="PostGIS SVN"
arch=(i686 x86_64)
url="http://postgis.net/stuff"
license=('GPL')
depends=('geos' 'gtk2' 'gdal' 'json-c' 'libxml2' 'postgresql')
options=('!libtool')
install=
changelog=
source=($url/$pkgname-$pkgver.tar.gz)
noextract=()
md5sums=('e3b806f939de584e9ee34af529a3d245')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --with-gui
  make

  cd utils
  make
}


package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install

  cd utils
  make DESTDIR=${pkgdir} install
}

# vim:set ts=2 sw=2 et:
