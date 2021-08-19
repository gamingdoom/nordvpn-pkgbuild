# Maintainer: Cat2048
pkgname=nordvpn
pkgver=3.9.5
pkgrel=1
pkgdesc="A VPN that protects your privacy online and lets access media content without regional restrictions. Strong encryption and no-log policy with 6000+ servers in 60+ countries."
arch=(x86_64)
url="https://nordvpn.com/"
license=('unknown')
depends=(iptables iproute procps ca-certificates libxml2)
install="nordvpn.install"
source=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_amd64.deb")
#source_i386=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_i386.deb")
#source_aarch64=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_arm64.deb")
sha256sums=('SKIP')

package() {
	bsdtar -x -f data.tar.gz
	bsdtar -x -f control.tar.gz
	mv usr/sbin/* usr/bin
	rm -vr usr/sbin 
	cp -rv usr $pkgdir/usr
	cp -rv var $pkgdir/var
	cp -rv etc $pkgdir/etc
	mv postinst nordvpnsetup
	chmod 755 "nordvpnsetup"
  	install -Dt "usr/bin" "nordvpnsetup"
}
