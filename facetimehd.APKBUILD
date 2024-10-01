# Maintainer: Joshua Rogers <Joshua@Joshua.Hu>
pkgname=facetimehd-src
_modname=facetimehd
pkgver=0.6.8.2
pkgrel=0
pkgdesc="Kernel module for Mac FaceTimeHD cameras"
url="https://github.com/patjak/facetimehd"
arch="noarch"
license="GPL-2.0-only"
makedepends="linux-lts-dev xz facetimehd-firmware"
depends="linux-lts"
install=
source="$pkgname-$pkgver.tar.gz::https://github.com/patjak/facetimehd/archive/refs/tags/$pkgver.tar.gz"
builddir="$srcdir/facetimehd-$pkgver"
options="!check"  # sources only

_kver=$(cd /usr/src/ && find . -mindepth 1 -maxdepth 1 -type d -name '*-lts' | sed 's!./linux-headers-!!')
_kbase="/lib/modules/${_kver}"
_srcdir="$builddir"

build() {
	make -C "$_srcdir" KVER="$_kver"
}

package() {
	xz "$_srcdir"/*.ko
	mkdir -p "$pkgdir"/lib/modules/"$_kver"/kernel/extra/facetimehd
	install -p -D -m 644 "$_srcdir"/*.ko.xz -t "$pkgdir"/lib/modules/"$_kver"/kernel/extra/facetimehd
}

sha512sums="
1b8fd6f72f58203978c3b5007e4789362891fe87e31c98582ab8323cd6c5bfc5947c5d7c228c6ba7c8e138c119196c3551098d4f8d4af9592782580bcee30745  facetimehd-src-0.6.8.2.tar.gz
"
