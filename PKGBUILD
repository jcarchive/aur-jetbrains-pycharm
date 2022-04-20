# Maintainer: Jose C.

pkgname=jetbrains-pycharm
pkgver='2022.1'
pkgrel=1
pkgdesc='Cross-platform PYCHARM IDE based on the IntelliJ platform'
arch=('x86_64')
options=('!strip' 'staticlibs')
url='https://www.jetbrains.com/pycharm/'
license=('Commercial')
optdepends=()
provides=('pycharm')
conflicts=('pycharm')

_filename="pycharm-professional-$pkgver.tar.gz"
_filextract="pycharm-2022.1"


source=("https://download.jetbrains.com/python/$_filename"
	"${pkgname}.desktop")

sha256sums=( 
'9b160ed74f384be31ff376af73f91924a212e6440ce142a581b22f261e6cf605'
'42b0779ce70247d4b3863ca722a72e4fcfcfa486c8a890ea0dc712f719286ac3'
)

package() {
	#Create directories with permission rwxr-xr-x
	install -m755 -d "${pkgdir}/usr/share" "${pkgdir}/usr/bin" "${pkgdir}/usr/share/applications"

	#Copy files to pkg destination
	cp -r "${srcdir}/${_filextract}" "${pkgdir}/usr/share/${pkgname}"
  chown -R root:root "${pkgdir}/usr/share/${pkgname}"

	ln -s "/usr/share/${pkgname}/bin/pycharm.sh" "${pkgdir}/usr/bin/pycharm"
  install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications"
}
