 
# Maintainer: Nikhil Alex <nikhil.wtp@gmail.com>

pkgname='vmware-horizon-client-8'
pkgver=2206
_build1=8.6.0
_build2=20094634
_cart='CART23FQ2_LIN_2206_TARBALL'
pkgrel=1
pkgdesc='VMware Horizon Client for Linux'
arch=('x86_64')
url='https://www.vmware.com/go/viewclients'
license=('custom')
source=("https://download3.vmware.com/software/${_cart}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}.tar.gz")
sha256sums=(9819eae5708bf0d71156b81283e3a70100e2e22de9db827a8956ca8e83b2414a)

prepare() {
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/"
    tar xzvf VMware-Horizon-Client-${pkgver}-${_build1}-${_build2}.x64.tar.gz
    tar xzvf VMware-Horizon-PCoIP-${pkgver}-${_build1}-${_build2}.x64.tar.gz
    tar xzvf VMware-Horizon-html5mmr-${pkgver}-${_build1}-${_build2}.x64.tar.gz
    tar xzvf VMware-Horizon-TeamsOptimization-${pkgver}-${_build1}-${_build2}.x64.tar.gz
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
    cd "${srcdir}/VMware-Horizon-Client-Linux-${pkgver}-${_build1}-${_build2}/x64/VMware-Horizon-TeamsOptimization-${pkgver}-${_build1}-${_build2}.x64"
    cp -a lib "${pkgdir}/usr/"
}
