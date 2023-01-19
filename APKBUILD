# Maintainer: Shadichy <shadichy.dev@gmail.com>
pkgname=nlplug-findfs
pkgdesc="Part of mkinitfs - Tool to generate initramfs images for Alpine"
url="https://gitlab.alpinelinux.org/alpine/mkinitfs"
arch="all"
license="GPL-2.0-only"
options="!check"
makedepends="busybox apk-tools"
depends="busybox>=1.28.2-r1 lddtree>=1.25 kmod mdev-conf"
source=""

apk fetch mkinitfs
busybox tar -xzf mkinitfs-*.apk

_ver="$(grep "pkgver" .PKGINFO | awk -F"= " '{print $2}')"
pkgver="$(echo "$_ver" | awk -F"-r" '{print $1}')"
pkgrel="$(echo "$_ver" | awk -F"-r" '{print $2}')"

package() {
	install -dm755 "$pkgdir/bin"
	install -m755 sbin/nlplug-findfs "$pkgdir/bin"
}
