# Maintainer: Harry ten Berge <htenberge@gmail.com>

pkgname=roon-extension-alarm-clock
pkgver=0.7.4
pkgrel=1
arch=(any)
url="https://github.com/TheAppgineer/roon-extension-alarm-clock"
license=('Apache')
depends=('nodejs'
         'npm')
options=('!strip')
source=('alarm-clock-checkout::git://github.com/RoPieee/roon-extension-alarm-clock.git#branch=master')


md5sums=('SKIP')
install=${pkgname}.install



build() {
echo "build"
   cd ${srcdir}/alarm-clock-checkout
   rm -rf node_modules
   npm --verbose --production install
}

package() {
echo "package"

   install -d "${pkgdir}/opt/TheAppgineer/alarm-clock"
   install -d "${pkgdir}/etc/systemd/system"

   cp -R "${srcdir}/alarm-clock-checkout/node_modules"                                "${pkgdir}/opt/TheAppgineer/alarm-clock"
   install -m0644 "${srcdir}/alarm-clock-checkout/alarm-clock.js"                     "${pkgdir}/opt/TheAppgineer/alarm-clock/alarm-clock.js"
   install -m0644 "${srcdir}/alarm-clock-checkout/package.json"                       "${pkgdir}/opt/TheAppgineer/alarm-clock/package.json"
   install -m0644 "${srcdir}/alarm-clock-checkout/roon-extension-alarm-clock.service" "${pkgdir}/etc/systemd/system"

}
