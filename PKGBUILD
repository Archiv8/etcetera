#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

pkgname=etcetera
pkgver=1.0
pkgrel=2
pkgdesc="A simple command line tool to keep track of changes to config files of a linux system"
arch=("x86_64" "armv6h")
url="https://gitlab.com/jeancf/etcetera"
license=("GPL3")
depends=(
  "python"
)
optdepends=(
  "python-cysystemd"
)
options=()
backup=("etc/etcetera.conf")
source=(
  "https://gitlab.com/jeancf/${pkgname}/-/archive/${pkgver}/${pkgname}-${pkgver}.tar.gz"
)
sha512sums=(
  'abd13d4acd151f8923c154d36ce9dc3c'
)

package() {

  cd ${srcdir}/${pkgname}-${pkgver}

  install -Dm755 etcetera ${pkgdir}/usr/bin/etcetera

  install -Dm644 commands.py ${pkgdir}/usr/lib/etcetera/commands.py

  install -Dm644 toolbox.py ${pkgdir}/usr/lib/etcetera/toolbox.py

  install -Dm755 parser.py ${pkgdir}/usr/lib/etcetera/parser.py

  install -Dm644 term_colors.py ${pkgdir}/usr/lib/etcetera/term_colors.py

  install -Dm644 README.md ${pkgdir}/usr/share/etcetera/README.md

  install -Dm644 etcetera-logo.png ${pkgdir}/usr/share/etcetera/etcetera-logo.png

  install -Dm644 etcetera.conf ${pkgdir}/etc/etcetera.conf

  install -Dm644 LICENSE ${pkgdir}/usr/share/LICENSES/etcetera/LICENSE

  cd ${pkgdir}
}
