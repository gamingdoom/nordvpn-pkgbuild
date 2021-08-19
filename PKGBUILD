# Maintainer: Cat2048
pkgname=nordvpn
pkgver=3.10.0
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
sha256sums_x86_64=('04d0089e326542c629c5f50a235de82bf3fa9fa829065be0490a0902e6770b63')
sha256sums_i686=('57b99b801d3e9364b0ae8bf0e9790204cbae0a120db9f1fdbd57ef6f1f0fd657')
sha256sums_aarch64=('d215b33979090bda4220401872255e8c638f4efc4e7efe3bb25254ddb0c10445')
sha256sums_armv7h=('08ab1bd5692732530a51c5690bc91eb0368b66ff4a0d9d4c9d943d9248326097')

package() {
	# Extract tarballs 
	bsdtar -x -f data.tar.gz && bsdtar -x -f control.tar.gz
	# Deal with sbin
	mv usr/sbin/* usr/bin && rm -r usr/sbin 
	# Copy data from extracted deb to pkgdir
	cp -r usr $pkgdir/usr && cp -r var $pkgdir/var && cp -r etc $pkgdir/etc
}
