# Maintainer: SpepS <dreamspepser at yahoo dot it>

pkgname=delaboratory
pkgver=0.8
pkgrel=1
pkgdesc="A realtime color correction utility"
arch=(i686 x86_64)
url="http://code.google.com/p/delaboratory/"
license=('GPL3')
depends=('wxgtk' 'desktop-file-utils')
optdepends=('dcraw: RAW files support')
install="$pkgname.install"
source=("http://$pkgname.googlecode.com/files/$pkgname-$pkgver.tar.gz"
        "$pkgname.desktop")
md5sums=('d4cf90d44d7a8a5708562273248838be'
         '3fc86481d6800a09f9226f7ca3a768e8')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  [ "$CARCH" = x86_64 ] && _arch=64
  make ARCH=$_arch
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  # bin
  install -Dm755 $pkgname \
    "$pkgdir/usr/bin/$pkgname"

  # desktop file
  install -Dm644 ../$pkgname.desktop \
    "$pkgdir/usr/share/applications/$pkgname.desktop"
}

# vim:set ts=2 sw=2 et:
