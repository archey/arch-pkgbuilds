# Maintainer: kpcyrd <git@rxv.cc>

pkgname=sniffglue
pkgver=0.3.0
pkgrel=2
pkgdesc="Secure multithreaded packet sniffer"
url="https://github.com/kpcyrd/sniffglue"
depends=('libpcap' 'libseccomp')
makedepends=('cargo')
arch=('i686' 'x86_64' 'armv6h')
license=('GPL3')
backup=('etc/sniffglue.conf')
source=("https://github.com/kpcyrd/$pkgname/archive/v$pkgver/$pkgname-$pkgver.tar.gz"
        "sniffglue-sysuser.conf"
        "sniffglue.conf")
sha256sums=('f0c60b25bc31f968402e389dd66700ea12d7d68e025e0302224670022bd43552'
            '531e051488e57ed2f5bf5d8289fa5562aa0ca73783838c11ec13c043dc268d02'
            'a2e6cfa918a4e354b5c4c4c84867f3bb142833fde4acab545e13c8e89864004c')
sha512sums=('b35d2b7a167f86fc96261bff455d66b69e74bb0e33ebc9fc6f6327d382e58f05bafe1273f345dffdd3a5eaf4040efce1b317dcc1bd7e33148099868a278c4886'
            '2595eb4856bc7a59c078255bf2aeeaa44a4f6a69b37cc8982e5d70a8ef14cb29b83b4d191ab3baabfbcf209f3effd232c10ec5baabc6ce52990969526d6fda98'
            '66e6b87e832ba8424334d24e3457a214e60e67c731471098329d0ca54c574518f7856ba780bb6bffde53bdefe2c8f789a242138ae67e2fef3e562fa083b362b1')

build() {
  cd "$pkgname-$pkgver"
  cargo build --release
}

package() {
  cd "$pkgname-$pkgver"
  install -Dm755 "target/release/$pkgname" -t "$pkgdir/usr/bin"
  install -Dm644 "$srcdir/sniffglue-sysuser.conf" "$pkgdir/usr/lib/sysusers.d/sniffglue.conf"
  install -Dm644 "$srcdir/sniffglue.conf" -t "$pkgdir/etc"
  install -Dm644 docs/sniffglue.1 -t "$pkgdir/usr/share/man/man1"
  install -Dm644 LICENSE -t "$pkgdir/usr/share/licenses/$pkgname"
}
