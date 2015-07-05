# Contributor: Artem Sereda <overmind88@gmail.com>
pkgname=flacon
pkgver=0.8.0
pkgrel=1
pkgdesc="Extracts individual tracks from one big audio file containing the \
 entire album of music and saves them as separate audio files."
arch=('any')
url="http://code.google.com/p/flacon/"
license=('GPL')
depends=('python2-qt' 'shntool')
optdepends=(
  'flac: for decoding and encoding FLAC files'
  'mac: for decoding APE files'
  'wavpack: for decoding WV files'
  'oggenc: for encoding OGG files'
  'lame: for encoding MP3 files'
  'vorbisgain: for OGG replay gain'
  'mp3gain: for MP3 replay gain'
)
source=("http://flacon.googlecode.com/files/$pkgname-$pkgver.tgz")

package() {
  cd $pkgname-$pkgver
  sed 's/python/python2/' \
	  -i Makefile \
	  -i misc/flacon \
	  -i flacon.py
  make DESTDIR="$pkgdir" install
}
sha256sums=('d2889b364ea49b19c400ce8081d829e5a37149dfdcb82d55f6ab453b679d1f85')
