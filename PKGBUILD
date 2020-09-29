# Maintainer: Lost Souls Guild - Nemesis <lost.souls.nemesis@gmail.com>
pkgname=ajour
pkgver=0.3.4.r0.g4f0e7f7
pkgrel=1
pkgdesc="Ajour is a World of Warcraft addon manager written in Rust with a strong focus on performance and simplicity"
arch=('i686' 'x86_64')
url="https://www.getajour.com/"
license=('MIT')
depends=('fontconfig' 'openssl' 'libxcb' 'vulkan-tools' 'vulkan-icd-loader')
makedepends=('git' 'cargo')
optdepends=('vulkan-intel' 'nvidia-utils' 'vulkan-radeon')
backup=()
source=('git+https://github.com/casperstorm/ajour.git#tag=0.3.4')
md5sums=('SKIP')
install="ajour.install"
	 
pkgver() {
  cd ajour 
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build(){
  cd ajour
  cargo build --release
}

package() {
  install -D -m755 "${srcdir}/ajour/target/release/ajour" "${pkgdir}/usr/bin/ajour"
  install -D -m644 "${srcdir}/ajour/LICENSE" "${pkgdir}/usr/share/licenses/ajour/LICENSE"
}
