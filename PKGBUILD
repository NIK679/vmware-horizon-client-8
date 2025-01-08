 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-8-custom'
pkgver=2412
_ver=8.14.0
_build=12437214089
_cart='CART25FQ4'
pkgrel=1
pkgdesc='Omnissa Horizon Client for Linux'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.omnissa.com/software/${_cart}_LIN_${pkgver}_TARBALL/Omnissa-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}.tar.gz")
sha256sums=(b6098f7d9a876ef51f4683a6a94359f94355e4b867cd0b8a5f2117b020993c11)

prepare() {
    cd "${srcdir}/Omnissa-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/"
    tar xzvf Omnissa-Horizon-Client-${pkgver}-${_ver}-${_build}.x64.tar.gz
    tar xzvf Omnissa-Horizon-PCoIP-${pkgver}-${_ver}-${_build}.x64.tar.gz
}

package() {
    mkdir -p "${pkgdir}/usr/share/"
    cd "${srcdir}/Omnissa-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/Omnissa-Horizon-Client-${pkgver}-${_ver}-${_build}.x64/usr/"
    sed -i 's/horizon-client %u/env GTK_THEME=Default horizon-client %u/' share/applications/horizon-client.desktop
    cp -a bin "${pkgdir}/usr/"
    cp -a lib "${pkgdir}/usr/"
    cp -a share/locale "$pkgdir/usr/share/"
    cp -a share/applications "$pkgdir/usr/share/"
    cp -a share/icons "$pkgdir/usr/share/"
    cd "${srcdir}/Omnissa-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/Omnissa-Horizon-PCoIP-${pkgver}-${_ver}-${_build}.x64/usr/"
    cp -a lib "${pkgdir}/usr/"
}
