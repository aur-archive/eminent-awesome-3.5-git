# Contributor:  Lucas de Vries <lucasdevries@gmail.com>
arch=(i686 x86_64)
pkgname=eminent-awesome-3.5-git
pkgver=4.fcf7c99
pkgrel=2
pkgdesc="Effortless wmii-style dynamic tagging for the awesome window manager version 3.5 or later, second iteration"
license=('GPL')
url="http://git.glacicle.org/eminent"

depends=('awesome')
makedepends=('git')
conflicts=('eminent')
provides=('eminent')

#_gitroot=git://github.com/guotsuan/eminent.git
_gitname=eminent

source=("git://github.com/guotsuan/eminent.git")
md5sums=('SKIP')

pkgver() {
    cd $_gitname
    echo $(git rev-list --count master).$(git rev-parse --short master)
}


build() {
  cd $_gitname
  luac -o eminent.luac eminent.lua
}

package() {
  cd $_gitname
  install -D -m644 eminent.lua ${pkgdir}/usr/share/awesome/lib/eminent.lua
  install -D -m644 eminent.luac ${pkgdir}/usr/share/awesome/lib/eminent.luac
}
