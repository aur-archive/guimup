# Contributor: totoloco <totoloco at gmail>
pkgname=guimup
pkgver=0.3.3
pkgrel=1
pkgdesc="Guimup is a mouse operated graphical user interface (GUI) for MPD, the [Mu]sic [P]layer Daemon (0.12.0 or above)."
arch=("i686" "x86_64")
url="http://www.coonsden.com/"
license=('GPL2')
depends=('mpd' 'intltool' 'gtkmm' 'libsoup' 'gtkmm3' 'libunique3' 'libmpdclient')

DLAGENTS=('http::/usr/bin/wget -U "" -c -t 3 --waitretry=3 -O %o %u')

source=(http://sourceforge.net/projects/musicpd/files/Guimup/${pkgver}/guimup-${pkgver}_src.tar.gz guimup.desktop)
md5sums=('09ce42080c7e9e8488a5f4521d3f6a2d'
         '0150d821f2996ffb2fec72dde3d416a1')

build() {
  cd "${srcdir}/guimup-${pkgver}"
  ./configure --prefix=/usr
  make
}

check() {
  cd "${srcdir}/guimup-${pkgver}"
  make -k check
}

package() {
  cd "${srcdir}/guimup-${pkgver}"
  make DESTDIR="$pkgdir/" install
#  install -D -m644 $srcdir/Guimup-"$pkgver"/Icons/guimup64.png $pkgdir/usr/share/pixmaps/guimup.png
  install -D -m644 "${startdir}/guimup.desktop" "${pkgdir}/usr/share/applications/guimup.desktop"
}
