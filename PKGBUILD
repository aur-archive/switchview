# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: David Sugar <dyfet@gnutelephony.org>
pkgname=switchview
pkgver=0.2.3
pkgrel=1
#epoch=
pkgdesc="A sipwitch desktop control interface"
arch=('x86_64' 'i686')
url="http://www.gnutelephony.org"
license=('GPL3')
groups=()
depends=('coastal-qt' 'sipwitch' 'qt4>=4.8.0')
makedepends=('cmake>=2.6.0')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(http://dev.gnutelephony.org/dist/tarballs/$pkgname-$pkgver.tar.gz)
noextract=()
md5sums=('0383431a73eb7ea8f737cf2e0bb214f9')

build() {
	cd "$srcdir/$pkgname-$pkgver"
	cmake ./ -DCMAKE_INSTALL_PREFIX=/usr -DQT_QMAKE_EXECUTABLE=qmake-qt4 -DBUILD_QT4ONLY=true
	make
}

package() {
	cd "$srcdir/$pkgname-$pkgver"
	make DESTDIR="$pkgdir/" install
	install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
