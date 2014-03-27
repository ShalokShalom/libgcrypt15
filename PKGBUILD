pkgname=libgcrypt15
_pkgname=libgcrypt
pkgver=1.5.3
pkgrel=1
pkgdesc="General purpose cryptographic library based on the code from GnuPG"
arch=('x86_64')
url="http://www.gnupg.org"
license=('LGPL')
depends=('libgpg-error>=1.10-2')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.gnupg.org/gcrypt/${_pkgname}/${_pkgname}-${pkgver}.tar.bz2)
sha1sums=('2c6553cc17f2a1616d512d6870fe95edf6b0e26e')

build() {
  cd ${_pkgname}-${pkgver}
  ./configure --prefix=/usr \
	--disable-static \
	--disable-padlock-support
  make
}

check() {
  cd ${_pkgname}-${pkgver}
  make check
}

package() {
  cd ${_pkgname}-${pkgver}
  install -Dm755 src/.libs/libgcrypt.so.11.8.2 "$pkgdir/usr/lib/libgcrypt.so.11.8.2"
  cd "$pkgdir/usr/lib"
  ln -s libgcrypt.so.11.8.2 libgcrypt.so.11
}
