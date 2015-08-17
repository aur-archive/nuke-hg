pkgname=nuke-hg
pkgver=r41.cfaa1f9ddfdc
pkgrel=1
pkgdesc="Simple but powerful IDE for Python & Web written in pure Python and GTK 2 (nightly beta)."
arch=('any')
url="http://bitbucket.org/AndrewDunai/nuke"
license=('GPL')
depends=('python2>=2.7.0' 'python2-rope' 'pygtk>=2.24.0' 'pygtksourceview2>=2.10.0')
makedepends=('mercurial')
conflicts=('nuke')
md5sums=('SKIP')
source=('hg+http://bitbucket.org/AndrewDunai/nuke')
install=nuke-hg.install

_hgroot='http://bitbucket.org/AndrewDunai'
_hgrepo='nuke'

pkgver() {
    cd "$srcdir/$_hgrepo"
    printf "r%s.%s" "$(hg identify -n)" "$(hg identify -i)"
}
package() {
    mkdir -p ${pkgdir}/usr/share/nuke/
    mkdir -p ${pkgdir}/usr/share/applications/
    cp -r ${srcdir}/nuke/share/* ${pkgdir}/usr/share/nuke
    install -Dm755 ${srcdir}/nuke/src/nuke.py ${pkgdir}/usr/bin/nuke
    install -Dm644 ${srcdir}/nuke/share/nuke.desktop ${pkgdir}/usr/share/applications/
}
