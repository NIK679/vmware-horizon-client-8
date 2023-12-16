 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-8-custom'
pkgver=2309.1
_ver=8.11.1
_build=22775487
_cart='CART24FQ4'
pkgrel=1
pkgdesc='VMware Horizon Client for Linux'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.vmware.com/software/${_cart}_LIN_${pkgver}_TARBALL/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}.tar.gz")
sha256sums=(3f66d21c0e97324d1cb85ac75132a69768e8e7ff57da33841e4e8bd37089d245)

prepare() {
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/"
    tar xzvf VMware-Horizon-Client-${pkgver}-${_ver}-${_build}.x64.tar.gz
    tar xzvf VMware-Horizon-PCoIP-${pkgver}-${_ver}-${_build}.x64.tar.gz
}

package() {
    mkdir -p "${pkgdir}/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/VMware-Horizon-Client-${pkgver}-${_ver}-${_build}.x64/usr/"
    sed -i 's/vmware-view %u/env GTK_THEME=Default vmware-view %u/' share/applications/vmware-view.desktop
    cp -a bin "${pkgdir}/usr/"
    cp -a lib "${pkgdir}/usr/"
    cp -a share/locale "$pkgdir/usr/share/"
    cp -a share/applications "$pkgdir/usr/share/"
    cp -a share/icons "$pkgdir/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/VMware-Horizon-PCoIP-${pkgver}-${_ver}-${_build}.x64/usr/"
    cp -a lib "${pkgdir}/usr/"
}
