# Maintainer: Natalie <natalie@localhost>
pkgname=messenger-pwa
pkgver=1.0.0
pkgrel=1
pkgdesc="Facebook Messenger Electron Wrapper"
arch=('any')
url="https://github.com/spivanatalie64/Messenger-pwa"
license=('ISC')
depends=('electron')
makedepends=('npm' 'git')
source=("git+https://github.com/spivanatalie64/Messenger-pwa.git"
        "messenger-pwa.desktop"
        "messenger-pwa.sh")
sha256sums=('SKIP'
            '1c187d06d298f0e87d0565c9de7782862aad3765773ceee3cbfbf6b0aaf076bd'
            'fad573ae1f7fb78cc0220ea477cb2ccea9ec17c2533227dce9abbae50888ff6d')

package() {
  # Install source code
  install -d "$pkgdir/usr/lib/$pkgname"
  cp -r "$srcdir/Messenger-pwa/"* "$pkgdir/usr/lib/$pkgname"
  
  # Remove build-only or unnecessary files if any (e.g. .git)
  rm -rf "$pkgdir/usr/lib/$pkgname/.git"
  
  # Install launcher script
  install -Dm755 "$srcdir/messenger-pwa.sh" "$pkgdir/usr/bin/$pkgname"
  
  # Install desktop entry
  install -Dm644 "$srcdir/messenger-pwa.desktop" "$pkgdir/usr/share/applications/$pkgname.desktop"
}
