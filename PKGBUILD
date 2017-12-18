# Maintainer: ValHue <vhuelamo at gmail dot com>
# https://github.com/ValHue/AUR-PKGBUILDs
#
# Contributor: satanselbow <igdfpm at gmail dot com>
# Contributor: Artem Sereda <overmind88 at gmail dot com>

pkgname="flacon"
pkgver=4.0.0
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
sha512sums=('64efc3369f11a7345d106a253873bcaf64ff0bbfb045e3554fecdc48a86ee5d150bef06643a5bf481d6e139a45a2bfdee91e730f9aa1354a4772f0d994297b78')

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
