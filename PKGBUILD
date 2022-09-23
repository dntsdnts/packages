# Maintainer: Yukari Chiba <i@0x7f.cc>

pkgname=clover-efi
pkgver=5149
pkgrel=1
pkgdesc='Bootloader for macOS, Windows and Linux in UEFI and in legacy mode'
arch=('x86_64')
url='https://github.com/CloverHackyColor/CloverBootloader'
license=('BSD')
backup=('boot/EFI/CLOVER/config.plist')
source=("https://github.com/CloverHackyColor/CloverBootloader/releases/download/$pkgver/Clover-$pkgver-X64.iso.7z" config.plist.sample)
noextract=("Clover-$pkgver-X64.iso.7z")
sha256sums=('SKIP' 'SKIP')

prepare() {
  rm -rf EFI
  bsdtar -xf "Clover-$pkgver-X64.iso.7z" -O | bsdtar -xf - 'EFI'
}

package() {
  install -dm755 "$pkgdir/usr/share/$pkgname"
  install -dm755 "$pkgdir/usr/lib/$pkgname"
  install "config.plist.sample" "$pkgdir/usr/share/$pkgname/config.plist.sample"
  cp --archive 'EFI' "$pkgdir/usr/lib/$pkgname/EFI"
}
