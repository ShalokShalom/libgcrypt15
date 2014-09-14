pkgname=libgcrypt15
_pkgname=libgcrypt
_apiver=11.8.3
pkgver=1.5.4
pkgrel=1
pkgdesc="General purpose cryptographic library based on the code from GnuPG"
arch=('x86_64')
url="http://www.gnupg.org"
license=('LGPL')
depends=('libgpg-error>=1.10-2')
options=('!libtool' '!emptydirs')
source=(ftp://ftp.gnupg.org/gcrypt/${_pkgname}/${_pkgname}-${pkgver}.tar.bz2)
sha1sums=('bdf4b04a0d2aabc04ab3564fbe38fd094135aa7a')

build() {
  cd ${_pkgname}-${pkgver}
  ./configure --prefix=/usr \
    --disable-static \
    --disable-padlock-support
  make
}

# check() {
  # cd ${_pkgname}-${pkgver}
  # make check
# }

package() {
  cd ${_pkgname}-${pkgver}
  install -Dm755 src/.libs/libgcrypt.so.${_apiver} "$pkgdir/usr/lib/libgcrypt.so.${_apiver}"
  cd "$pkgdir/usr/lib"
  ln -s libgcrypt.so.${_apiver} libgcrypt.so.11
}
