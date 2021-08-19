# Maintainer: Cat2048
pkgname=nordvpn
pkgver=3.9.5
pkgrel=1
pkgdesc="A VPN that protects your privacy online and lets access media content without regional restrictions. Strong encryption and no-log policy with 6000+ servers in 60+ countries."
arch=('x86_64' 'i686' 'aarch64' 'armv7h')
url="https://nordvpn.com/"
license=('unknown')
depends=(libxml2)
install="nordvpn.install"
# Nordvpn sources
source_x86_64=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_amd64.deb")
source_i686=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_i386.deb")
source_aarch64=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_arm64.deb")
source_armv7h=("https://repo.nordvpn.com/deb/nordvpn/debian/pool/main/${pkgname}_$pkgver-1_armhf.deb")
# Unoffical sha256 sums
sha256sums_x86_64=('36fccf2e53792766cedb6b4b95f2945b2adb6714482460c21afcc65a33fa3ca3')
sha256sums_i686=('e1f356051e0dd16a26d963ee81330fdfe045195f195a66a0304a4441242fc953')
sha256sums_aarch64=('807ce776213052ce4426ce97b11258c7d1ecf0667a17de9b297cb9381beaffb2')
sha256sums_armv7h=('6c1e0637b13fe932c733c281b4e75c7bd4516e578a5e5536ac93718d71b06da6')

package() {
	# Extract tarballs 
	bsdtar -x -f data.tar.gz && bsdtar -x -f control.tar.gz
	# Deal with sbin
	mv usr/sbin/* usr/bin && rm -r usr/sbin 
	# Copy data from extracted deb to pkgdir
	cp -r usr $pkgdir/usr && cp -r var $pkgdir/var && cp -r etc $pkgdir/etc
}
