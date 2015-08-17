# Contributor: Lex Black <autumn-wind at web dot de>
# Contributor: Hervé Cauwelier <herve ¤ oursours.net>
# Contributor: Santi Villalba <sdvillal ¤ gmail.com>

pkgbase=python-stdeb
pkgname=('python-stdeb' 'python2-stdeb')
pkgver=0.8.2
pkgrel=2
pkgdesc="Python to Debian source package conversion utility"
arch=('any')
license=('MIT')
url="http://github.com/astraw/stdeb"
depends=('debhelper>=7')
makedepends=('python' 'python2')
source=(http://pypi.python.org/packages/source/s/stdeb/stdeb-$pkgver.tar.gz)
md5sums=('d5b75b3bebfd31ab68f5e98c078fc5f2')


package_python-stdeb() {
  pkgdesc=" (Python3.x)"
  depends+=('python')

  cd "$srcdir/stdeb-$pkgver"

  python setup.py install --root=${pkgdir} --prefix=/usr
}

package_python2-stdeb() {
  pkgdesc=" (Python2.x)"
  depends+=('python2')

  cd "$srcdir/stdeb-$pkgver"

  python2 setup.py install --root=${pkgdir} --prefix=/usr

  # Avoid clashes between python2 and python3 versions
  cd ${pkgdir}/usr/bin
  for f in ./*
  do
    mv "${f}" "${f}2"
  done
}
