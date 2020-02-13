# Maintainer: Ondrej Svoboda <theodik@gmail.com>

pkgname=bpi_ledset-git
pkgver=r9.63a06c2
pkgrel=1
pkgdesc="A utility to control the network (PHY-related) LEDs on Banana Pi (original model,\"BPi-M1\")."
arch=('armv7h')
url="https://github.com/evandar/bpi_ledset"
license=('custom')
makedepends=('git')
source=("git+https://github.com/evandar/bpi_ledset.git")
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/bpi_ledset"
  printf 'r%s.%s' "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$srcdir/bpi_ledset"
  make
}

package() {
  cd "$srcdir/bpi_ledset"
  install -D -o root -g root -m 744 bpi_ledset $pkgdir/usr/bin/bpi_ledset
  install -D -o root -g root -m 644 $startdir/bpi_ledset.service $pkgdir/usr/lib/systemd/system/bpi_ledset.service
}
