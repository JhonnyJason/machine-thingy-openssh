# Maintainer: Lenard Frommelt <lenny09918050@gmail.com>

pkgname=machine-thingy-nginx
pkgver=r2.e051e83
pkgrel=1
pkgdesc='Package to configure nginx for a machine-thingy'
arch=('any')
url=''
license=('UNLICENSE')
makedepends=('git')
depends=('nginx')
install=machine-thingy-nginx.install
source=("machine-thingy-nginx::git+https://github.com/JhonnyJason/machine-thingy-nginx-config.git")
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  ( set -o pipefail
    git describe --long 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  )
}

package() {
    mkdir -p $pkgdir/etc/arch-evolver/config/nginx/
    install -g root -o root -m 644 $pkgname/nginx.conf $pkgdir/etc/arch-evolver/config/nginx/nginx.conf
}