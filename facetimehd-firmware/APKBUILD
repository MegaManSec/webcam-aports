# Maintainer: Joshua Rogers <Joshua@Joshua.Hu>
pkgname=facetimehd-firmware
pkgver=1.0.0
pkgrel=0
pkgdesc="Alpine package for downloading and installing facetimehd firmware"
url="https://github.com/patjak/facetimehd-firmware"
arch="noarch"
license="GPL-2.0-only"
makedepends="bash cpio curl xz"
source="$pkgname-$pkgver.tar.gz::https://github.com/patjak/facetimehd-firmware/archive/refs/tags/v$pkgver.tar.gz"

build() {
	make DESTDIR="$pkgdir"
}

check() {
	[ -e firmware.bin ] || return 1
}

package() {
	make DESTDIR="$pkgdir" install
}

sha512sums="
68e62bf792805812b91c6270e0396f4ca2d120d41d8a6e6ecc203ca45668c9c5a59b0a8500914068039b1dbe75e118754af233bec436da9e1c12351d3a6870e5  facetimehd-firmware-1.0.0.tar.gz
"
