# Maintainer: Baptiste Jonglez <baptiste--aur at jonglez dot org>
# Contributor: et50292@gmail.com
# Modified version, inspired from pdcurses (AUR)
pkgname=mingw32-pdcurses-sdl
pkgver=3.4
pkgrel=1
arch=(i686 x86_64)
pkgdesc="An implementation of the curses library for Win32, DOS, OS/2, X11 and SDL. Compiled with SDL support."
makedepends=('mingw32-gcc' 'mingw32-binutils' 'mingw32-w32api')
url="http://pdcurses.sourceforge.net/"
license=(custom)
source=(http://downloads.sourceforge.net/pdcurses/PDCurses-$pkgver.tar.gz
  pdcurses_sdl1_mingw.patch)
md5sums=('4e04e4412d1b1392a7f9a489b95b331a'
         '251a9c000fade565b13a2ede0af89d71')
options=(!strip)

build()
{
  cd $srcdir/PDCurses-$pkgver/sdl1
  patch -i $srcdir/pdcurses_sdl1_mingw.patch  

  CC=i486-mingw32-gcc LIBEXE=i486-mingw32-ar make -f Makefile.mng libs

  mkdir -p $pkgdir/usr/i486-mingw32/lib $pkgdir/usr/i486-mingw32/include

  install -m 644 libpdcurses.a $pkgdir/usr/i486-mingw32/lib/libpdcurses.a
  install -m 644 ../curses.h ../panel.h $pkgdir/usr/i486-mingw32/include
}

