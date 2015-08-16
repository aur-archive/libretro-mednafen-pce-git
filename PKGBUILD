# Maintainer:  prettyvanilla <prettyvanilla@posteo.at>
# Contributor: almostalive   <almostalive2003 at gmail dot com>

pkgname=libretro-mednafen-pce-git
pkgver=338.fcd6c71
pkgrel=1
pkgdesc="libretro implementation of Mednafen PCE Fast. (PC Engine/TurboGrafx-16)"
arch=('i686' 'x86_64' 'arm' 'armv6h')
url="https://github.com/libretro/mednafen-libretro"
license=('GPL')
makedepends=('git')

_gitname=mednafen-libretro
source=("git+https://github.com/libretro/${_gitname}.git"
        "https://raw.github.com/libretro/libretro-super/master/dist/info/mednafen_pce_fast_libretro.info")
md5sums=('SKIP'
         'SKIP')

pkgver() {
  cd "${_gitname}"
  echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
  cd "${_gitname}"
  make core=pce-fast
}

package() {
  install -Dm644 "${_gitname}/mednafen_pce_fast_libretro.so" "${pkgdir}/usr/lib/libretro/libretro-mednafen-pce.so"
  install -Dm644 "mednafen_pce_fast_libretro.info" "${pkgdir}/usr/lib/libretro/libretro-mednafen-pce.info"
}
