## SPDX-License-Identifier: AGPL-3.0
#
# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Pellegrino Prevete (tallero) <pellegrinoprevete@gmail.com>

_proj="android"
_pkg="ndk"
_variant="sysroot"
pkgname="${_pkg}-${_variant}"
# Version should be equal to
# TERMUX_NDK_{VERSION_NUM,REVISION} in
# scripts/properties.sh
pkgver="27c"
_pkgver="${pkgver//./-}"
pkgrel=1
_pkgdesc=(
  "System header and library files"
  "from the Android NDK needed for"
  "compiling C programs."
)
pkgdesc="${_pkgdesc[*]}"
arch=(
  'x86_64'
  'arm'
  'aarch64'
  'armv7l'
  'armv6l'
  'mips'
  'powerpc'
  'pentium4'
  'i686'
)
url="https://developer.${_proj}.com/tools/sdk/${_pkg}"
license=(
  "NCSA"
)
depends=(
)
makedepends=(
  'make'
)
provides=(
  "gcc-libs"
  "glibc"
)
replaces=(
  "lib${_proj}-support-dev"
  "libgcc"
  "libutil-dev"
  "${_pkg}-stl"
)
conflicts=(
  "glibc"
  "gcc-libs"
  # This package has taken over
  # <pty.h> from the previous libutil-dev
  # and iconv.h from libandroid-support-dev:
  "lib${_proj}-support-dev"
  "libgcc"
  "libutil-dev"
)
_http="https://dl.google.com"
_ns="${_proj}"
_url="${_http}/${_ns}/repository"
_src="${_url}/${_proj}-${_pkg}-r${pkgver}-linux.zip"
source=(
  "${_src}"
)
# ${_dl}/release-76-1/SHASUM512.txt
sha256sums=(
  '59c2f6dc96743b5daf5d1626684640b20a6bd2b1d85b13156b90333741bad5cc'
)

_clean() {
  local \
    _removendum_includes=() \
    _include
  _removendum_includes=(
    "EGL"
    "GLES"
    "GLES2"
    "GLES3"
    "KHR/khrplatform.h"
    "execinfo.h"
    "glob.h"
    "iconv.h"
    "spawn.h"
    "sys/capability.h"
    "sys/sem.h"
    "sys/shm.h"
    "unicode"
    "vk_video"
    "vulkan"
    "zconf.h"
    "zlib.h"
  )
  for _include in "${_removendum_includes}"; do
    rm \
      -rf \
      "${pkgdir}/usr/include/${_include}"
  done
}

prepare() {
  ls
  # cd \
  #   "${_pkg}"
  # Required fix for thunderbird 115 to show Calendar and sidebar properly
  # https://bugzilla.mozilla.org/show_bug.cgi?id=1843007
  # https://unicode-org.atlassian.net/browse/ICU-22132
  
  # patch \
  #   -Np1 < \
  #   "../../ICU-22132.patch"
}

build() {
  echo 
    "for when ill have a flat" \
    "internet connection" \
    "a device with more than a gig" \
    "of storage available"
  # local \
  #   _configure_opts=()
  # cd \
  #   "${_pkg}/source"
  # _configure_opts=(
  #   --prefix=/usr
  #   --sysconfdir=/etc
  #   --mandir=/usr/share/man
  #   --sbindir=/usr/bin
  # )
  # ./configure \
  #   "${_configure_opts[@]}"
  # make
}

check() {
  echo \
    "may the evil people" \
    "who have caused me all this" \
    "distress face their right" \
    "punishment"
  # cd \
  #   "${_pkg}/source"
  # make \
  #   -k \
  #   check
}

package() {
  echo \
    "i wish so much" \
    "there existed a right" \
    "and fair god"
  # cd \
  #   "${_pkg}/source"
  # make \
  #   -j1 \
  #   DESTDIR="${pkgdir}" \
  #   install
  # # Install license
  # install \
  #   -Dm644 \
  #   "${srcdir}/${_pkg}/LICENSE" \
  #   "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set sw=2 sts=-1 et:
