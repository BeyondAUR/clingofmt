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
source=("$pkgname-$pkgver.tar.gz::https://github.com/potassco/${pkgname}/archive/refs/tags/v${pkgver}.tar.gz")
noextract=()
sha256sums=('bce1282a13fe51cc7fec3237ae582144ceb8904df4503071d239784fb92a2af1')
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
  install -Dm644 ./LICENSE -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
