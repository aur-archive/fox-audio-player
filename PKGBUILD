# Maintainer: archtux <antonio dot arias99999 at gmail dot com>

pkgname=fox-audio-player
pkgver=0.10.2
pkgrel=2
pkgdesc="Simple and lightweight audio player built with Fox toolkit."
arch=('i686' 'x86_64')
url="http://foxaudioplayer.sourceforge.net/"
license=('GPL2')
depends=('fox')
optdepends=('libmodplug: A MOD playing library'
            'libsidplayfd: to play Commodore 64 music'
            'libvorbis: Ogg support'
            'libsndfile: to play sampled sounds'
            'libmad: MP3 support'
            'ffmpeg'
            'musepack-tools: mpc decoder'
            'wavpack: support for .wv files'
            'mpg123: MPEG Audio Player for Layer 1, 2 and 3'
            'libbs2b: Bauer stereophonic-to-binaural DSP effect library')
source=(http://sourceforge.net/projects/foxaudioplayer/files/fap/0.10/fap-$pkgver.tar.bz2)
md5sums=('19662778212aeb277571e79df37dcd39')

prepare() {
  cd $srcdir/fap-$pkgver
  # If 'musepack-tools' is installed delete '--disable-mpc-plugin' in next line 
  ./configure --prefix=/usr --disable-mpc-plugin --enable-tta-plugin --enable-gme-plugin --enable-hvl-plugin 
}

build() {
  cd $srcdir/fap-$pkgver  
  make
}

package() {
  cd $srcdir/fap-$pkgver
  make DESTDIR=$pkgdir install
}
