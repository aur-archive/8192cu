#Mantainer Renan Manola
pkgname=8192cu
pkgver=3.0.1590
pkgrel=1
pkgdesc="Drivers for realtek RTL8188CUS chipset wireless cards"
arch=('i686' 'x86_64')
url="http://218.210.127.131/downloads/downloadsView.aspx?Langid=1&PNid=21&PFid=48&Level=5&Conn=4&DownTypeID=3&Downloads=true"
depends=('kernel26')
makedepends=('kernel26-headers')
license='unknown'
install='install.8192cu'
md5sums=('8bb0c1c9614e2a20b878c56096bfad11' 'd6bf00749f8b2f95cb3600366982f371' '7fde0e422cee13edc0c8a61a578ff469')
fileprefix=''
source=("ftp://WebUser2:2mG8dBW@58.211.24.153/cn/wlan/RTL8188CUS_linux_v3.0.1590.20110511.zip"
	"osdep_service.patch"
	"rtw_io.patch")

build() {

  cd ${srcdir}/RTL8192CU_8188CUS_8188CE-VAU_linux_v3.0.1590.20110511/driver
  tar xvf rtl8192_8188CU_linux_v3.0.1590.20110511.tar.gz
  cd rtl8192_8188CU_linux_v3.0.1590.20110511
  patch include/osdep_service.h < ./../../../osdep_service.patch
  patch include/rtw_io.h < ./../../../rtw_io.patch
  make
}
package() {
  mkdir -p ${pkgdir}/lib/modules/`uname -r`/kernel/drivers/net/wireless/
  cd ${srcdir}/RTL8192CU_8188CUS_8188CE-VAU_linux_v3.0.1590.20110511/driver/rtl8192_8188CU_linux_v3.0.1590.20110511/
  install -p -m 644 8192cu.ko  ${pkgdir}/lib/modules/`uname -r`/kernel/drivers/net/wireless/
} 
