# Contributor: Artem Sereda <overmind88@gmail.com>
# Maintainer from 0.8.0 release satanselbow <igdfpm@gmail.com>
pkgname=flacon
pkgver=1.2.0
pkgrel=1
pkgdesc="Extracts individual tracks from one big audio file containing the \
 entire album of music and saves them as separate audio files."
arch=('i686' 'x86_64')
url="https://github.com/flacon/flacon/"
license=('LGPL')
makedepends=('cmake')
depends=('qt4' 'uchardet' 'flac' 'shntool' 'hicolor-icon-theme')
optdepends=(
  'vorbis-tools: For OGG support'
  'mac: For APE support'
  'wavpack: For WavPack support'
  'ttaenc: For TrueAudio support'
  'lame: For MP3 support'
  'mp3gain: For MP3 Replay Gain support'
  'vorbisgain: For OGG Replay Gain support'
)

source=("$pkgname-$pkgver.tar.gz::https://github.com/flacon/flacon/archive/v$pkgver.tar.gz")

prepare() {
  	mkdir -p "$pkgname-$pkgver/build"
}

build() {
	cd "$pkgname-$pkgver/build"
	cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr .. && make
}

package() {
	cd "$pkgname-$pkgver/build"
	make DESTDIR=${pkgdir} install
}

sha256sums=('2ebc83d733ea6d50f2bd4ad8c20c65368be5eaf351e0195c9b4d47a54957b8f8')
