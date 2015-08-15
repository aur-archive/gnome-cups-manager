# $Id: $
# Maintainer: Allan McRae <allan@archlinux.org>
# Contributor: Giacomo Rizzo <alt@free-os.it>
# Contributor: Charles-Henri d'Adhémar <cdadhemar@gmail.com>

pkgname=gnome-cups-manager
pkgver=0.33
pkgrel=6
pkgdesc="A CUPS manager for the Gnome Desktop Environment"
arch=('i686' 'x86_64')
url="http://www.gnome.org"
license=('GPL')
depends=('libgnomecups' 'libgnomeui' 'gksu')
makedepends=('pkgconfig' 'intltool')
install=gnome-cups-manager.install
options=('!libtool')
source=("http://ftp.gnome.org/pub/gnome/sources/$pkgname/$pkgver/$pkgname-$pkgver.tar.bz2")
md5sums=('a48eb85cd239760913c936d824062473')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  
  sed -i "s#gnomesu#gksu#" libgnomecups/gnome-cups-permission.c
  
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
  make || return 1
  make DESTDIR="${pkgdir}/" install
}
