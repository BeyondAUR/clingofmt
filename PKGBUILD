# Maintainer: Evan Greenup <SKIP>
pkgname="clingofmt"
pkgver="0.1.0"
pkgrel=1
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
source=("$pkgname-$pkgver.tar.gz::https://github.com/potassco/${pkgname}/releases/tag/v${pkgver}")
noextract=()
sha256sums=()
validpgpkeys=()

build() {
  cd "$pkgname-$pkgver"
  export RUSTUP_TOOLCHAIN=stable
  export CARGO_TARGET_DIR=target
  cargo build --locked --release --all-features
}

check() {
  cd $pkgname-$pkgver
  export RUSTUP_TOOLCHAIN=stable
  cargo test --locked --all-features
}

package() {
  cd $pkgname-$pkgver
  install -Dm0755 -t "$pkgdir/usr/bin/" "target/release/$pkgname"
}
