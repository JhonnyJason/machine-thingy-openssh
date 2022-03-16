# Maintainer: Lenard Frommelt <lenny09918050@gmail.com>

pkgname=machine-thingy-openssh
pkgver=r3.19ec636
pkgrel=1
pkgdesc='Package to configure openssh for a machine-thingy'
arch=('any')
url=''
license=('UNLICENSE')
makedepends=('git')
depends=('openssh')
install=machine-thingy-openssh.install
source=("machine-thingy-openssh::git+https://github.com/JhonnyJason/machine-thingy-openssh-config.git")
md5sums=('SKIP')

pkgver() {
  cd "$pkgname"
  ( set -o pipefail
    git describe --long 2>/dev/null | sed 's/\([^-]*-g\)/r\1/;s/-/./g' ||
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
  )
}

package() {
    mkdir -p $pkgdir/etc/arch-evolver/config/ssh/
    install -g root -o root -m 644 $pkgname/sshd_config $pkgdir/etc/arch-evolver/config/ssh/sshd_config
}
