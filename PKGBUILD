# Maintainer: Evan Greenup <SKIP>
pkgname="clingofmt"
pkgver="0.1.1"
pkgrel=2
epoch=
pkgdesc="Tool to find and fix formatting issues in clingo files"
arch=(x86_64)
url="https://github.com/potassco/clingofmt"
license=('MIT')
groups=()
depends=()
makedepends=("cargo")
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("$pkgname-$pkgver.tar.gz::https://github.com/potassco/${pkgname}/archive/refs/tags/v${pkgver}.tar.gz")
noextract=()
sha256sums=('de70a1f3e2d82c8aa14ec3c6b6e0b27383f4d4832a2316db7f8621b8505edb57')
validpgpkeys=()

build() {
  cd "$pkgname-$pkgver"
  export RUSTUP_TOOLCHAIN=stable
  export CARGO_TARGET_DIR=target
  cargo build --release --all-features
}

check() {
  cd $pkgname-$pkgver
  export RUSTUP_TOOLCHAIN=stable
  cargo test --release --all-features
}

package() {
  cd $pkgname-$pkgver
  install -Dm0755 -t "$pkgdir/usr/bin/" "target/release/$pkgname"
  install -Dm644 ./LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
