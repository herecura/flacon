# Contributor: Artem Sereda <overmind88@gmail.com>
# Maintainer from 0.8.0 release satanselbow <igdfpm@gmail.com>
pkgname=flacon
pkgver=2.0.1
pkgrel=3
pkgdesc="Extracts individual tracks from one big audio file containing the \
    entire album of music and saves them as separate audio files."
arch=('i686' 'x86_64')
url="https://github.com/flacon/flacon/"
license=('LGPL')
makedepends=('cmake' 'icu')
depends=('qt4' 'uchardet' 'flac' 'shntool' 'ffmpeg' 'desktop-file-utils' 'hicolor-icon-theme' 'shared-mime-info')
optdepends=(
    'vorbis-tools: For OGG support'
    'mac: For APE support'
    'wavpack: For WavPack support'
    'ttaenc: For TrueAudio support'
    'lame: For MP3 support'
    'mp3gain: For MP3 Replay Gain support'
    'vorbisgain: For OGG Replay Gain support'
    'opus-tools: For OPUS support'
)

source=("$pkgname-$pkgver.tar.gz::https://github.com/flacon/flacon/archive/v$pkgver.tar.gz")
sha256sums=('3408304e7ab524a2e8a621ea780579e1be7b3359fefe7d37a1b88f34d6120e02')

prepare() {
    mkdir -p "$pkgname-$pkgver/build"
}

build() {
    cd "$pkgname-$pkgver/build"
    cmake -DCMAKE_INSTALL_PREFIX=/usr ..
    make
}

package() {
    cd "$pkgname-$pkgver/build"
    make DESTDIR=${pkgdir} install
}

