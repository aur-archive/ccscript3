# Contributor:
# Contributor: arjan <arjan@archlinux.org>
# Contributor: John Proctor <jproctor@prium.net>

pkgname=ccscript3
pkgver=1.1.7
pkgrel=2
pkgdesc="GNU ccScript"
arch=('i686' 'x86_64')
url="http://www.gnu.org/software/ccscript"
license=('GPL2')
depends=('commoncpp2' 'unixodbc')
makedepends=('pkgconfig')
replaces=('ccscript')
options=('!libtool')
source=(ftp://ftp.gnu.org/pub/gnu/ccscript/$pkgname-$pkgver.tar.gz
        ccscript3-1.1.7-gcc44.patch)
md5sums=('126435f25568e88f0e5daf189dc0c847'
         'afdebdbcf835ee584a2a1c8eeddb0fdc')

build() {
  cd ${srcdir}/${pkgname}-${pkgver}
  patch -Np1 -i ${srcdir}/ccscript3-1.1.7-gcc44.patch || return 1
  ./configure --prefix=/usr
  make || return 1
}

package() {
  cd ${srcdir}/${pkgname}-${pkgver}
  make DESTDIR=${pkgdir} install || return 1
}
