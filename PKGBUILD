# Maintainer: Aleksana QwQ <me@aleksana.moe>
# Contributor: Sergej Pupykin <pupykin.s+arch@gmail.com>
# Contributor: François Charette <firmicus ατ gmx δοτ net>

pkgname=perl-json
pkgver=4.09
pkgrel=1
pkgdesc="JSON (JavaScript Object Notation) encoder/decoder"
arch=('any')
url="https://search.cpan.org/dist/JSON"
license=('GPL' 'PerlArtistic')
depends=('perl>=5.10.0')
options=('!emptydirs')
source=(https://search.cpan.org/CPAN/authors/id/I/IS/ISHIGAKI/JSON-$pkgver.tar.gz)
sha256sums=('SKIP')

build() {
  cd  "$srcdir"/JSON-$pkgver
  PERL_MM_USE_DEFAULT=1 perl Makefile.PL INSTALLDIRS=vendor
  make
}

package() {
  cd  "$srcdir"/JSON-$pkgver
  make install DESTDIR="$pkgdir"
  find "$pkgdir" -name '.packlist' -delete
  find "$pkgdir" -name '*.pod' -delete
}
