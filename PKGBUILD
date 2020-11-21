# Maintainer: jordi miralles <jordimirallesguri@gmail.com>
pkgname=bitwarden-rofi-git
pkgver=0.4.r20.ga53cc1e
pkgrel=1
pkgdesc="Wrapper for Bitwarden and Rofi - "
srcdest="/usr/share/bitwarden-rofi"
arch=('any')
url="https://github.com/mattydebie/$pkgname"
license=('GPL3')
depends=('rofi' 'jq' 'bitwarden-cli')
optdepends=('xsel: copy to clipboard'
            'xclip: copy to clipboard'
            'wl-clipboard: copy to clipboard on wayland'
            'xdotool')
makedepends=(git)
source=("git+https://github.com/mattydebie/${pkgname%-git}.git")
sha512sums=('SKIP')





package() {
	cd "$srcdir/${pkgname%-git}" || exit 1
  local doc_path="$pkgdir/usr/share/doc/${pkgname}"

  install -Dm755 "bwmenu" "$pkgdir/usr/bin/bwmenu"
  install -Dm755 "lib-bwmenu" "$pkgdir/usr/bin/lib-bwmenu"

  install -Dm755 -d "$pkgdir/usr/share/doc/${pkgname}"
  install -Dm755 -d "$pkgdir/usr/share/doc/${pkgname}/img"

  install -Dm644 "README.md" "${doc_path}/README.md"
  install -Dm644 img/* "${doc_path}/img/"

  install -Dm644 "LICENSE" "$pkgdir/usr/share/licenses/${pkgname}/LICENSE"
}
pkgver() {
  	cd "$srcdir/${pkgname%-git}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

