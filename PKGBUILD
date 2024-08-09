pkgname=kyocera-ma-ppd
pkgver=9.3
pkgrel=1
pkgdesc="PPD file for Kyocera MA2000/MA2000w/MA2001/MA2001w"
arch=("any")
url="https://www.kyoceradocumentsolutions.com/download/"
license=('other')
depends=('cups')
source=('Kyocera_MA2000.ppd'
        'Kyocera_MA2000w.ppd'
        'Kyocera_MA2001.ppd'
        'Kyocera_MA2001w.ppd')
	   
sha256sums=('ddcaa261c8f56ed460030305172c8c4f16d8ee80760c22b5a5acf87f7d1b0f6a'
            '8a43683463cd5863357e9c2617bdd4ccf21323c7b865a6c85b04d6154faf2a89'
            '53b7586e018c7e2a0c983c226d27d5af68dcd5bd461f158788bc39332529a465'
            '73661b01530c3743164b569294ec062d993de3f79d31e1a7b8619fdf463f8bd0'
            )
package () {
	cd ${srcdir}

	 install -d -m755 ${pkgdir}/usr/share/ppd

	 install -D -m644 "Kyocera_MA2000.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2000.ppd"
	 install -D -m644 "Kyocera_MA2000w.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2000w.ppd"
	 install -D -m644 "Kyocera_MA2001.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2001.ppd"
	 install -D -m644 "Kyocera_MA2001w.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2001w.ppd"
}
