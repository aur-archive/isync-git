# Contributor: Mark Pustjens <pustjens@dds.nl>
# Contributor: Timothée Ravier <tim@siosm.fr>
# Previous Contributor: Geoffroy Carrier <geoffroy.carrier@koon.fr>
# Previous Contributor: Giorgio Lando <patroclo7@gmail.com>
# Previous Contributor: Leslie P. Polzer <polzer@gnu.org>

pkgname=isync-git
_gitname=isync
pkgver=1.1.2.629.9a46376
pkgrel=1
pkgdesc="IMAP mail synchronizer for offline/batch mail editing"
url="http://isync.sourceforge.net"
arch=('i686' 'x86_64')
license=('GPL')
depends=('openssl')
makedepends=('perl-timedate')
conflicts=('isync')
replaces=('isync')
source=('git://git.code.sf.net/p/isync/isync')
sha256sums=('SKIP')

pkgver() {
  cd ${_gitname}
  echo -n $(grep -m 1 -o -E "[0-9.]*" configure.ac)
  echo '.'$(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

prepare() {
  cd ${_gitname}
  ./autogen.sh
}

build() {
  cd ${_gitname}
  ./configure --prefix=/usr
  make
}

package() {
  cd ${_gitname}
  make DESTDIR="${pkgdir}" install
}

# vim: ts=2 sw=2 et:
