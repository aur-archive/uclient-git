# Maintainer: Luka Perkov <luka.perkov@sartura.hr>

pkgname=uclient-git
_gitname=uclient
pkgver=r65.e350ca4
# commit cb7867a867e45949950e03de0ea845e483ffc6eb
pkgrel=1
pkgdesc='ustream based protocol client library'
url='http://git.openwrt.org/?p=project/uclient.git'
arch=('i686' 'x86_64')
license=('ISC BSD-3c')
depends=('libubox-lua-git' 'ustream-ssl-git')
makedepends=('git' 'cmake' 'gcc' 'make')
provides=('uclient')
source=('git://git.openwrt.org/project/uclient.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/$_gitname"

	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
	cd "$srcdir/$_gitname"

	cmake CMakeLists.txt \
		-DCMAKE_INSTALL_PREFIX=/usr \

	make
}

package() {
	cd "$srcdir/$_gitname"

	make DESTDIR="$pkgdir" install
}
