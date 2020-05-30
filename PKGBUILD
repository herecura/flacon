# Maintainer: ValHue <vhuelamo at gmail dot com>
# https://github.com/ValHue/AUR-PKGBUILDs
#
# Contributor: satanselbow <igdfpm at gmail dot com>
# Contributor: Artem Sereda <overmind88 at gmail dot com>

pkgname="flacon"
pkgver=6.0.0
pkgrel=1
pkgdesc="Extracts individual tracks from one big audio file containing the \
 entire album of music and saves them as separate audio files."
arch=('x86_64')
url="https://flacon.github.io/"
license=('LGPL2.1')
makedepends=('cmake' 'icu' 'qt5-tools')
depends=('qt5-base' 'uchardet' 'shntool' 'ffmpeg' 'desktop-file-utils' 'hicolor-icon-theme' 'shared-mime-info')
optdepends=('flac: For FLAC support'
            'vorbis-tools: For OGG support'
            'mac: For APE support'
            'wavpack: For WavPack support'
            'ttaenc: For TrueAudio support'
            'lame: For MP3 support'
            'mp3gain: For MP3 Replay Gain support'
            'vorbisgain: For OGG Replay Gain support'
            'opus-tools: For OPUS support')
conflicts=('flacon-git')
source=("$pkgname-$pkgver.tar.gz::https://github.com/$pkgname/$pkgname/archive/v$pkgver.tar.gz")
sha512sums=('236d3695295ad5a74cc689a8464493e51159667b945bc2aabc47f01a0921b0d39aa4331688cd94a0ee14de08250c1cea9865f13a5d2e07e7ee8776b88a36c94a')

build() {
    cd "$pkgname-$pkgver"
    mkdir build

    cd build
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd "$pkgname-$pkgver/build"
    install -d "$pkgdir/usr/share/licenses/$pkgname"
    install -m 644 ../LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
    make DESTDIR="$pkgdir" install
}


# vim:set ts=4 sw=2 ft=sh et:
