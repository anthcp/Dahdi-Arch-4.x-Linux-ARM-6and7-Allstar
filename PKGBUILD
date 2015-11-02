# Maintainer : Xavier Devlamynck <magicrhesus@ouranos.be>
# Contributor: Jonathan Liu <net147@gmail.com>
# Contributor: VK2ACP <anthcp@gmail.com>

pkgname=dahdi-allstar
pkgver=2.9.1.1
pkgver_tools=2.9.1
pkgrel=2
pkgdesc="DAHDI drivers for Asterisk with allstar mods for Raspberry PI"
arch=('armv6h' 'armv7h')
url="http://www.asterisk.org/"
license=('GPL2')
depends=('linux>=4.0' 'linux<4.2' 'libusb' 'perl' 'alsa-lib' 'alsa-oss')
makedepends=('binutils' 'autoconf' 'linux-headers>=4.0' 'libnewt' 'libusb-compat')
conflicts=('zaptel' 'dahdi')
install="${pkgname}.install"
source=("http://downloads.asterisk.org/pub/telephony/dahdi-linux-complete/releases/dahdi-linux-complete-${pkgver}+${pkgver_tools}.tar.gz"
	"update4.patch"
	"allstar.conf")
sha1sums=('8a1b99aec5fb5b05f443aba8ce96d732703ee67b'
          'e415229d1b9a380e7fa9c4f2b31d94578ac9c609'
          '256db4f27f9ddd40e18f860e59d744f99e4bf94d')
build() {
  cd "${srcdir}/dahdi-linux-complete-${pkgver}+${pkgver_tools}"
  patch -p1 -i "${srcdir}/update4.patch"
  make DESTDIR="${pkgdir}" all
}

package() {
  cd "${srcdir}/dahdi-linux-complete-${pkgver}+${pkgver_tools}"
  make DYNFS=1 DESTDIR="${pkgdir}" install
  mkdir "${pkgdir}/etc/modules-load.d"
  cp "${srcdir}/allstar.conf" "${pkgdir}/etc/modules-load.d/allstar.conf"
}
# vim:set ts=2 sw=2 et:
