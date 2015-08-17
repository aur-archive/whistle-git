# Maintainer: Manuel Fill <manuel.fill.42@gmail.com> 

pkgname=whistle-git
pkgver=0.0.0
pkgrel=1
pkgdesc="a curses-based commandline audio (mp3/ogg/flac) player"
arch=('i686' 'x86_64')
url="https://github.com/ap0calypse/whistle"
license=('MIT')
depends=('pacman' 'perl-curses-ui' 'perl-mp3-info' 'perl-file-mimeinfo' 'mplayer' 'perl-ogg-vorbis-header' 'perl-audio-flac-header')
makedepends=('git')
conflicts=('whistle')
provides=('whistle')
# The git repo is detected by the 'git:' or 'git+' beginning.
#source=('git+https://github.com/falconindy/expac.git'
# The repo is cloned into '$pkgname' (optional).
source=("$pkgname"::'git://github.com/ap0calypse/whistle.git')
# To check out a specific branch use #branch=<branch>:
#source=('git+https://github.com/falconindy/expac.git#branch=master'
# Because the sources are not static, skip Git checksum:
md5sums=('SKIP')

pkgver() {
        cd "$srcdir/$pkgname"
            # Use the tag of the last commit
                git describe --long | sed -E 's/([^-]*-g)/r\1/;s/-/./g'
}

build() {
        cd "$srcdir/$pkgname"
}

package() {
        cd "$srcdir/$pkgname"
            install -Dm755 "$srcdir/$pkgname/whistle" "$pkgdir/usr/bin/whistle"
}
