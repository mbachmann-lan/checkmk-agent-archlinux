# Maintainer 2016-2017: Milian Reichardt <mreichardt95@gmail.com>
# Maintainer since 2018: Christian Blechert <christian@anysrc.net>
# https://github.com/pfeilmann/check_mk-agent
# modified for agent 2.0.0p8: Michael Bachmann <checkmk@bachmann-lan.de>

pkgname=check-mk-agent
pkgver=2.0.0p11
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

sha512sums=('3e972fa22f9a0f281d904ea465afac7b24a69bdf34498c753631441f0e084561073279fa73f3bf21e9a4fe653453320d1372348fd054fdfd3f24e592bf3ce8a3'
'cfbf17d67b0295c428aa528529f8acec995311e9490e64c4b764c06cd8234c1e8008618e6684c11ebe93c07452942af1c5911e21dda7c02b4bed5dd4f3d0f123'
'788e192794ae2c076ac377c17094c405ec0faddf4471dbc54c380c8b4591a3abda7d95d489bf1d9bd67787408babe92a491c05d36e7945a70847c3afd9d54ff9'
'8f78f0e047a71966ad3c73cf9240cdba1414b4d56608c6333543d8d8744fc86eef1135257e905a52644415ffc7656b6600f8562cbd598ec7bf02ef794e2fa242'
'36337e349f04fc20e9c1113dc34699fed97bd609dd69e47925bf0ad17454b870dae8a6297a36cf4b4cda649e08d4066660a74dbce69cfab05f8f153bce950740'
'68f5aaacdf1527e7a52b433ab78c94e974a0097ef4475c4fc1ecde32e761a2e167c5ec43eeada6836616b9c39c69a899b8ff49170528a94c13873716fbab23e9'
'6e1a63fb2e23a4e3d4afd2aef57faf957e057f661eb1a99f3054b56202f4dd47622029f15c8370c6f8cc5b0cc586979180d121aff86d1c71d605c4c0af4d6d38')

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