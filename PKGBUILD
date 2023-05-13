 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-8-custom'
pkgver=2303
_ver=8.9.0
_build=21435420
_cart='CART24FQ1_LIN_2303_TARBALL'
pkgrel=1
pkgdesc='VMware Horizon Client for Linux'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.vmware.com/software/${_cart}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}.tar.gz")
sha256sums=(a4dcc6afc0be7641e10e922ccbbab0a10adbf8f2a83e4b5372dfba095091fb78)

prepare() {
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/"
    tar xzvf VMware-Horizon-Client-${pkgver}-${_ver}-${_build}.x64.tar.gz
    tar xzvf VMware-Horizon-PCoIP-${pkgver}-${_ver}-${_build}.x64.tar.gz
#     tar xzvf VMware-Horizon-html5mmr-${pkgver}-${_ver}-${_build}.x64.tar.gz
#     tar xzvf VMware-Horizon-TeamsOptimization-${pkgver}-${_ver}-${_build}.x64.tar.gz
}

package() {
    mkdir -p "${pkgdir}/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/VMware-Horizon-Client-${pkgver}-${_ver}-${_build}.x64"
    sed -i 's/vmware-view %u/GTK_THEME=Materia vmware-view %u/' share/applications/vmware-view.desktop
    cp -a bin "${pkgdir}/usr/"
    cp -a lib "${pkgdir}/usr/"
    mkdir -p "${pkgdir}/usr/share/doc/vmware-horizon-client"
    cp -a doc "${pkgdir}/usr/share/doc/vmware-horizon-client"
    cp -a share/locale "$pkgdir/usr/share/"
    cp -a share/applications "$pkgdir/usr/share/"
    cp -a share/icons "$pkgdir/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/VMware-Horizon-PCoIP-${pkgver}-${_ver}-${_build}.x64"
    cp -a lib "${pkgdir}/usr/"
#     cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/VMware-Horizon-html5mmr-${pkgver}-${_ver}-${_build}.x64"
#     cp -a lib "${pkgdir}/usr/"
#     cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_ver}-${_build}/x64/VMware-Horizon-TeamsOptimization-${pkgver}-${_ver}-${_build}.x64"
#     cp -a lib "${pkgdir}/usr/"
}
