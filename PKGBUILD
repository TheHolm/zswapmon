# Maintainer: VHSgunzo <vhsgunzo.github.io>

# GitHub repo the release assets come from. CI sets ZSWAPMON_REPO to the repo
# it runs in ($GITHUB_REPOSITORY); the default is used for AUR/.SRCINFO.
_repo="${ZSWAPMON_REPO:-TheHolm/zswapmon}"

pkgname='zswapmon-bin'
pkgver='0.1.0'
pkgrel='1'
pkgdesc='Utility for monitoring zswap status and statistics'
arch=('x86_64' 'aarch64' 'armv7h')
url="https://github.com/${_repo}"
license=('MIT')
provides=("${pkgname%-bin}")
conflicts=("${pkgname%-bin}" "${pkgname%-bin}-git")
# Prebuilt static binary: nothing to strip, no debug info.
options=('!strip' '!debug')

# Local file names are versioned per arch. In CI the files are placed next to
# this PKGBUILD before makepkg runs, so nothing is downloaded (on tag builds
# the release does not exist yet).
_dl="${url}/releases/download/v${pkgver}"
source=("LICENSE::https://raw.githubusercontent.com/${_repo}/v${pkgver}/LICENSE")
source_x86_64=("zswapmon-${pkgver}-x86_64::${_dl}/zswapmon")
source_aarch64=("zswapmon-${pkgver}-aarch64::${_dl}/zswapmon-aarch64")
source_armv7h=("zswapmon-${pkgver}-armv7h::${_dl}/zswapmon-armhf")
sha256sums=('SKIP')
sha256sums_x86_64=('SKIP')
sha256sums_aarch64=('SKIP')
sha256sums_armv7h=('SKIP')

package() {
    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/${pkgname%-bin}/LICENSE"
    install -Dm755 "zswapmon-${pkgver}-${CARCH}" "$pkgdir/usr/bin/${pkgname%-bin}"
}
