# Maintainer: Brian Bidulock <bidulock@openss7.org>
# Contributor: Tom Newsom <Jeepster@gmx.co.uk>
# Contributor: andrewy <andrew@andrewyates.net>
#
pkgname=bbkeys
pkgver=0.9.2
pkgrel=1
pkgdesc="Blackbox tool for setting keyboard shortcuts for manipulating windows and virtual desktop"
arch=('x86_64')
url="http://bbkeys.sourceforge.net/"
license=('custom')
groups=('blackbox')
depends=('blackboxwm')
source=("https://github.com/bbidulock/$pkgname/releases/download/rel-092/$pkgname-$pkgver.tar.lz"
	"bbkeys.desktop")
sha512sums=('bf36da8fc70073392aaacee157d2b8b7f5231943bf24644e8a2122f4e4c83647810918cec7c2ceb149285178f5e8f64fec0e11be291bdacbd51b8121a5ec8336'
            '6bbda6ae655d41ae4beb45937b6e4d408b7710163b144f37df41383a756c35d930e5ceb64fff63b5c7ed9941f22d45e6d523bc9acd43a5bc93e774ba3f4bc5f2')

build() {
  cd $pkgname-$pkgver
  ./configure
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
  install -m644 -D "COPYING" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
  install -m644 -D "../bbkeys.desktop" "$pkgdir/usr/share/applications/bbkeys.desktop"
  install -m644 -D "../bbkeys.desktop" "$pkgdir/etc/xdg/autostart/bbkeys.desktop"
}
