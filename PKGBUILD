# Contributor: Vadzim Dambrouski <pftbest@gmail.com>

pkgname=qgears2
pkgver=1.0
pkgrel=2
pkgdesc="Very simple qt4 graphics benchmark based on David Reveman cairogears"
arch=(i686 x86_64)
url="http://zrusin.blogspot.com/2008/08/fast-graphics.html"
license=('custom')
depends=('qt4' 'libgl')
source=('http://www.phoronix-test-suite.com/benchmark-files/qgears2.tar.bz2')
md5sums=('1a5d0f555745c397216caa551fbda305')

build() {
  cd $srcdir/$pkgname
  sed -i 's/bg.png/\/usr\/share\/qgears2\/bg.png/' composite.cpp
  sed -i 's/fg.png/\/usr\/share\/qgears2\/fg.png/' composite.cpp
  qmake
  make || return 1
}

package() {
  cd $srcdir/$pkgname
  dstpath=$pkgdir/usr/share/qgears2
  mkdir -p $dstpath
  cp *.png $dstpath
  mkdir -p $pkgdir/usr/bin
  cp qgears $pkgdir/usr/bin/$pkgname
}
