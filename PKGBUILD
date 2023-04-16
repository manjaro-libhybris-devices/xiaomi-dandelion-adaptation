# Maintainer: Bardia Moshiri <fakeshell@bardia.tech>

pkgname=xiaomi-dandelion-adaptation
provides=(halium10-post-install)
conflicts=(halium10-post-install)
pkgver=1$(date +%y%m%d)
pkgrel=1
pkgdesc="Manjaro libhybris adaptation for xiaomi dandelion"
arch=('any')
url="https://github.com/manjaro-libhybris-devices/xiaomi-dandelion-adaptation"
license=('GPL')
depends=('gzip' 'glibc-locales' 'wget' 'systemd')
makedepends=('git')
source=("xiaomi-dandelion-adaptation::git+https://github.com/manjaro-libhybris-devices/xiaomi-dandelion-adaptation.git")
install=$pkgname.install
md5sums=('SKIP')

package() {
    mv "${srcdir}/xiaomi-dandelion-adaptation/xiaomi-dandelion-adaptation.sh" "${srcdir}/xiaomi-dandelion-adaptation/xiaomi-dandelion-adaptation"

    mkdir -p "${pkgdir}/usr/bin/"
    install -Dm755 "${srcdir}/xiaomi-dandelion-adaptation/xiaomi-dandelion-adaptation" -t "${pkgdir}/usr/bin/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/xiaomi-dandelion-adaptation.service" -t "${pkgdir}/usr/lib/systemd/system/"

    mkdir -p "${pkgdir}/usr/lib/sysusers.d/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/android.conf" -t "${pkgdir}/usr/lib/sysusers.d/"

    cp -r "${srcdir}/xiaomi-dandelion-adaptation/droid-vendor-overlay" -t "${pkgdir}/usr/lib/"

    mkdir -p "${pkgdir}/lib/modules/"
    cp -r "${srcdir}/xiaomi-dandelion-adaptation/vendor" -t "${pkgdir}/lib/modules"

    mkdir -p ${pkgdir}/etc/phosh/
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/phoc.ini" -t "${pkgdir}/etc/phosh/"

    mkdir -p "${pkgdir}/etc/udev/rules.d/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/70-garden.rules" -t "${pkgdir}/etc/udev/rules.d/"

    mkdir -p "${pkgdir}/etc/systemd/user/pulseaudio.d/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/10-env.conf" -t "${pkgdir}/etc/systemd/user/pulseaudio.service.d/"

    mkdir -p "${pkgdir}/etc/pulse/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/arm_droid_card_custom.pa" -t "${pkgdir}/etc/pulse/"

    mkdir -p "${pkgdir}/etc/modules-load.d/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/performance.conf" -t "${pkgdir}/etc/modules-load.d/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/connectivity.conf" -t "${pkgdir}/etc/modules-load.d/"

    mkdir -p "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/boot.img" -t "${pkgdir}/boot/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/vbmeta.img" -t "${pkgdir}/boot/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/brightness.service" "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/pbhelper.service" "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/ssh-fix.service" "${pkgdir}/usr/lib/systemd/system/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/gnome-session-unfailed.service" "${pkgdir}/usr/lib/systemd/system/"

    mkdir -p "${pkgdir}/usr/lib/systemd/system/bluebinder.service.d/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/10-after.conf" "${pkgdir}/usr/lib/systemd/system/bluebinder.service.d"

    install -Dm755 "${srcdir}/xiaomi-dandelion-adaptation/gnome-session-not-failed" "${pkgdir}/usr/lib/gnome-session-not-failed"

    mkdir -p "${pkgdir}/usr/share/glib-2.0/schemas/"
    install -Dm644 "${srcdir}/xiaomi-dandelion-adaptation/90_manjaro.gschema.override" -t "${pkgdir}/usr/share/glib-2.0/schemas/"

    mkdir -p "${pkgdir}/usr/bin/"
    install -Dm755 "${srcdir}/xiaomi-dandelion-adaptation/pbhelper" "${pkgdir}/usr/bin/pbhelper"
}
