 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-8-custom'
pkgver=2209
_build1=8.7.0
_build2=20616018
_cart='CART23FQ3_LIN_2209_TARBALL'
pkgrel=1
pkgdesc='VMware Horizon Client for Linux'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.vmware.com/software/${_cart}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}.tar.gz")
sha256sums=(222b645318cb67484a68810fae1209041462c1c8fb2b3e1a45f219dfba57c374)

prepare() {
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/"
    tar xzvf VMware-Horizon-Client-${pkgver}-${_build1}-${_build2}.x64.tar.gz
    tar xzvf VMware-Horizon-PCoIP-${pkgver}-${_build1}-${_build2}.x64.tar.gz
    tar xzvf VMware-Horizon-html5mmr-${pkgver}-${_build1}-${_build2}.x64.tar.gz
#     tar xzvf VMware-Horizon-TeamsOptimization-${pkgver}-${_build1}-${_build2}.x64.tar.gz
}

package() {
    mkdir -p "${pkgdir}/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/VMware-Horizon-Client-${pkgver}-${_build1}-${_build2}.x64"
    sed -i 's/vmware-view %u/XDG_CURRENT_DESKTOP=GNOME GTK_THEME=Default vmware-view %u/' share/applications/vmware-view.desktop
    cp -a bin "${pkgdir}/usr/"
    cp -a lib "${pkgdir}/usr/"
    mkdir -p "${pkgdir}/usr/share/doc/vmware-horizon-client"
    cp -a doc "${pkgdir}/usr/share/doc/vmware-horizon-client"
    cp -a share/locale "$pkgdir/usr/share/"
    cp -a share/applications "$pkgdir/usr/share/"
    cp -a share/icons "$pkgdir/usr/share/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/VMware-Horizon-PCoIP-${pkgver}-${_build1}-${_build2}.x64"
    cp -a lib "${pkgdir}/usr/"
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/VMware-Horizon-html5mmr-${pkgver}-${_build1}-${_build2}.x64"
    cp -a lib "${pkgdir}/usr/"
#     cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/VMware-Horizon-TeamsOptimization-${pkgver}-${_build1}-${_build2}.x64"
#     cp -a lib "${pkgdir}/usr/"
}
