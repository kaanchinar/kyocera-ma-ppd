pkgname=kyocera-ma-ppd
pkgver=9.3
pkgrel=1
pkgdesc="PPD file for Kyocera MA2000/MA2000w/MA2001/MA2001w"
arch=("any")
url="https://www.kyoceradocumentsolutions.com/download/"
license=('other')
depends=('cups' 'cups-filters' 'libcups' 'krb5' 'python' 'python-reportlab' 'python-setuptools' 'qt5-base')
source=('Kyocera_MA2000.ppd'
        'Kyocera_MA2000w.ppd'
        'Kyocera_MA2001.ppd'
        'Kyocera_MA2001w.ppd'
        'data.tar.gz')
	   
sha256sums=('ddcaa261c8f56ed460030305172c8c4f16d8ee80760c22b5a5acf87f7d1b0f6a'
            '8a43683463cd5863357e9c2617bdd4ccf21323c7b865a6c85b04d6154faf2a89'
            '53b7586e018c7e2a0c983c226d27d5af68dcd5bd461f158788bc39332529a465'
            '73661b01530c3743164b569294ec062d993de3f79d31e1a7b8619fdf463f8bd0'
            'acdb862b7aa35968d2563620340c482ea73c94e0534f869d3ba9ea37e97f0622'
)

prepare (){
        tar xfv data.tar.gz
}

package() {
        cd ${srcdir}

        install -D -m644 "Kyocera_MA2000.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2000.ppd"
        install -D -m644 "Kyocera_MA2000w.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2000w.ppd"
        install -D -m644 "Kyocera_MA2001.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2001.ppd"
        install -D -m644 "Kyocera_MA2001w.ppd" "${pkgdir}/usr/share/ppd/Kyocera_MA2001w.ppd"
        
        install -D -m644 "${srcdir}/data/etc/xdg/autostart/knmd.desktop" "${pkgdir}/etc/xdg/autostart/knmd.desktop"
        
        #DBUS configuration
        install -D -m644 "${srcdir}/data/etc/dbus-1/system.d/com.kyocera.knm.conf" "${pkgdir}/etc/dbus-1/system.d/com.kyocera.knm.conf" 

        #Binary files
        # find "${srcdir}/data/usr/bin" -type f -exec install -D -m755 "{}" "${pkgdir}/usr/bin/{}" \;

        # install -D -m755 "${srcdir}/data/usr/bin" "${pkgdir}/usr/bin"
        for file in "${srcdir}/data/usr/bin"/*; do
                install -D -m755 "$file" "${pkgdir}/usr/bin/$(basename "$file")"
        done        

        #CUPS filters
        # find "${srcdir}/data/usr/lib/cups/filter" -type f -exec install -D -m755 "{}" "${pkgdir}/usr/lib/cups/filter/{}" \;
        for file in "${srcdir}/data/usr/lib/cups/filter"/*; do
                install -D -m755 "$file" "${pkgdir}/usr/lib/cups/filter/$(basename "$file")"
        done   

        # Create directories
        for dir in $(find "${srcdir}/data/usr/share" -mindepth 1 -type d); do
            target_dir="${pkgdir}/usr/share/${dir#${srcdir}/data/usr/share/}"
            install -d -m755 "$target_dir"
        done
        
        # Copy files
        for file in $(find "${srcdir}/data/usr/share" -type f); do
            target_file="${pkgdir}/usr/share/${file#${srcdir}/data/usr/share/}"
            install -D -m644 "$file" "$target_file"
        done

        

        




}




