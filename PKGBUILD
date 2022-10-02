# Maintainer: Null Talisman <webmaster@raspii.tech>

pkgname=steam-jupiter
pkgver=1.0.0.74
pkgrel=2.19
pkgdesc="Valve's digital software delivery system"
url='https://steampowered.com/'
arch=('x86_64')
license=('custom')
provides=('steam')
conflicts=('steam')
depends=('bash' 'desktop-file-utils' 'diffutils' 'hicolor-icon-theme' 'curl' 'dbus'
         'freetype2' 'gdk-pixbuf2' 'ttf-font' 'zenity' 'lsb-release' 'nss' 'usbutils'
         'xorg-xrandr' 'vulkan-driver' 'vulkan-icd-loader' 'lsof' 'python')
depends_x86_64=('lib32-libgl' 'lib32-gcc-libs' 'lib32-libx11' 'lib32-libxss'
                'lib32-alsa-plugins' 'lib32-libgpg-error' 'lib32-fontconfig'
                'lib32-nss' 'lib32-vulkan-driver' 'lib32-vulkan-icd-loader'
                'lib32-pipewire' 'lib32-systemd' 'lib32-libxinerama' 'lib32-libva')
optdepends=('lib32-libnm: integration with networkmanager')
source=("https://steamdeck-packages.steamos.cloud/archlinux-mirror/jupiter-main/os/x86_64/${pkgname}-stable-${pkgver}-${pkgrel}-x86_64.pkg.tar.zst")
sha256sums=('8c14484954f890ac6e3754dae20dd014400fe5b2fc9d351ac9e5b198de97ef4c')

package() {
    cd ${srcdir}
    tar -xvf ${pkgname}-stable-${pkgver}-${pkgrel}-x86_64.pkg.tar.zst -C ${pkgdir}

    rm -f ${pkgdir}/.PKGINFO ${pkgdir}/.MTREE ${pkgdir}/.BUILDINFO

    rm -f ${pkgdir}/usr/bin/steam ${pkgdir}/usr/bin/steamdeps
    ln -sf /usr/bin/steam-jupiter "${pkgdir}/usr/bin/steam"
    ln -sf /usr/bin/true "${pkgdir}/usr/bin/steamdeps"

    tar -xvf ${pkgdir}/usr/lib/steam/bootstraplinux_ubuntu12_32.tar.xz ./bootstrap.tar.xz
    rm ${pkgdir}/usr/lib/steam/bootstraplinux_ubuntu12_32.tar.xz
    mv ./bootstrap.tar.xz ${pkgdir}/usr/lib/steam/bootstraplinux_ubuntu12_32.tar.xz
}
