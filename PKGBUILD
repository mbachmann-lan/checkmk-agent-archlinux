# Maintainer 2016-2017: Milian Reichardt <mreichardt95@gmail.com>
# Maintainer since 2018: Christian Blechert <christian@anysrc.net>
# https://github.com/pfeilmann/check_mk-agent
# modified for the Checkmk 2.x Agent: Michael Bachmann <checkmk@bachmann-lan.de>

pkgname=check-mk-agent
pkgver=2.0.0p17
pkgrel=1
pkgdesc="Agent to send information to a Checkmk Server"
arch=(x86_64)
url="https://checkmk.com"
license=('GPLv2')
install=${pkgname}.install

source=("check_mk_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_agent.linux"
        "check_mk_caching_agent.linux::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/check_mk_caching_agent.linux"
        "check_mk-agent.service::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/cfg_examples/systemd/check_mk%40.service"
        "check_mk-agent.socket::https://raw.githubusercontent.com/tribe29/checkmk/v${pkgver}/agents/cfg_examples/systemd/check_mk.socket"
        "mrpe.cfg::mrpe.cfg"
        "check_pacman::check_pacman"
        "check_os::check_os")

sha512sums=('8efb35419dd113a9b5c7798ac065a3e2fb06efad18f6978416176257753259ee3971ad9bf5e0b1ec61e9a6774f589b569e70ed24344e7e8bdf8bba83626a387e'
'cfbf17d67b0295c428aa528529f8acec995311e9490e64c4b764c06cd8234c1e8008618e6684c11ebe93c07452942af1c5911e21dda7c02b4bed5dd4f3d0f123'
'788e192794ae2c076ac377c17094c405ec0faddf4471dbc54c380c8b4591a3abda7d95d489bf1d9bd67787408babe92a491c05d36e7945a70847c3afd9d54ff9'
'8f78f0e047a71966ad3c73cf9240cdba1414b4d56608c6333543d8d8744fc86eef1135257e905a52644415ffc7656b6600f8562cbd598ec7bf02ef794e2fa242'
'cd88baad088299fb6914bb68af68a51d7ccbf329cb35ddc62f19fbd85d3b01729ebcbf023ad21f2ec6325e33297cc14110d39efdfc65e1a4a63ce84d93520c0f'
'66842095e29058fadc3f83a2fc56892446574f0fd9cefeafd2d163d83d7c386afe0283f19704b6e23d28b294e29c419a9a003ef68a56fb7f882406e4ad03d323'
'78a8ec93c613f67899b31658f45a723cf42e627f67b861f105dc2def2c1f79098e1180e7c0a3de0ac80c6f84a9f9f7035fe3b679043e829569bb3a5a23b09a09')

package() {
        mkdir -p "$pkgdir/etc/check_mk/"
        mkdir -p "$pkgdir/usr/bin/"
        mkdir -p "$pkgdir/var/lib/check_mk_agent/cache"
        mkdir -p "$pkgdir/var/lib/check_mk_agent/job"
        mkdir -p "$pkgdir/var/lib/check_mk_agent/spool"
        mkdir -p "$pkgdir/usr/lib/check_mk_agent/local"
        mkdir -p "$pkgdir/usr/lib/check_mk_agent/plugins"
        mkdir -p "$pkgdir/etc/systemd/system"
        install -m744 "$srcdir/check_mk_agent.linux" "$pkgdir/usr/bin/check_mk_agent"
        install -m744 "$srcdir/check_mk_caching_agent.linux" "$pkgdir/usr/bin/check_mk_caching_agent"
        install -m644 "$srcdir/check_mk-agent.service" "$pkgdir/etc/systemd/system/check_mk-agent@.service"
        install -m644 "$srcdir/check_mk-agent.socket" "$pkgdir/etc/systemd/system/check_mk-agent.socket"
        install -m655 "$srcdir/check_os" "$pkgdir/etc/check_mk/check_os"
        install -m655 "$srcdir/check_pacman" "$pkgdir/etc/check_mk/check_pacman"
        install -m644 "$srcdir/mrpe.cfg" "$pkgdir/etc/check_mk/mrpe.cfg"
}
