# Maintainer: Elrondo46 (https://github.com/Elrondo46)
# Contributor: kounch (https://github.com/kounch)

pkgname=argonone-rpi4
pkgver=20200607
pkgrel=1
pkgdesc="Argon One Service and Control Scripts"
arch=('any')
url='https://download.argon40.com/argon1.sh'
license=('GPL3')
depends=('i2c-tools' 'libffi' 'lm_sensors' 'python>=3.3' 'python-pip' 'gcc' 'raspberrypi-firmware')
provides=('argonone')
install=argonone.install

source=(
  "https://raw.githubusercontent.com/Elrondo46/argonone/master/argonone-config"
  "https://raw.githubusercontent.com/Elrondo46/argonone/master/argononed-poweroff.py"
  "https://raw.githubusercontent.com/Elrondo46/argonone/master/argononed.conf"
  "https://raw.githubusercontent.com/Elrondo46/argonone/master/argononed.py"
  "https://raw.githubusercontent.com/Elrondo46/argonone/master/argononed.service"
)

sha256sums=(
  "100a231ff8bc29910bad4cc1e216c1760fa2dc3ab67ca1a6691d672d8f50478b"
  "5a3c550bc0f866a87acac6a27d3539656fce4ec7931a368d4b56158b78daab94"
  "f6f82283a286c9694a5adc6db842fca2e75845f1ccf0bacfb7ce2efa3c8eaec3"
  "5547cc212563ca571b6c22a61a20be2dfce2dd289d035ecea9bc27f4040b3ace"
  "e538b916dc7842833ae9c9689a43bee714e7a18dc96a9ee59d29cd14f66021e8"
)

package() {
  install -Dm755 "${srcdir}"/argonone-config "${pkgdir}"/opt/argonone/bin/argonone-config
  install -Dm755 "${srcdir}"/argononed-poweroff.py "${pkgdir}"/usr/lib/systemd/system-shutdown/argononed-poweroff.py
  install -Dm666 "${srcdir}"/argononed.conf "${pkgdir}"/etc/argononed.conf
  install -Dm755 "${srcdir}"/argononed.py "${pkgdir}"/opt/argonone/bin/argononed.py
  install -Dm644 "${srcdir}"/argononed.service "${pkgdir}"/usr/lib/systemd/system/argononed.service
}
