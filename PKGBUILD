# Maintainer : David Phillips <dbphillipsnz gmail>
# Contributor: Anatol Pomozov <anatol.pomozov@gmail.com>
# Originally generated by gem2arch (https://github.com/anatol/gem2arch)


_gemname=colorize
pkgname=ruby-$_gemname
pkgver=0.8.1
pkgrel=1
pkgdesc='Add color methods to String class'
arch=(any)
url='http://github.com/fazibear/colorize'
license=('GPL2')
depends=('ruby')
options=(!emptydirs)
source=("https://rubygems.org/downloads/${_gemname}-${pkgver}.gem")
noextract=("${_gemname}-${pkgver}.gem")
sha256sums=('0ba0c2a58232f9b706dc30621ea6aa6468eeea120eb6f1ccc400105b90c4798c')

package() {
	local _gemdir="$(ruby -e'puts Gem.default_dir')"
	gem install \
		--ignore-dependencies \
		--no-user-install \
		-i "${pkgdir}/${_gemdir}" \
		-n "${pkgdir}/usr/bin" \
		"${_gemname}-${pkgver}.gem"

	rm "${pkgdir}/${_gemdir}/cache/${_gemname}-${pkgver}.gem"

	install -D -m644 \
		"${pkgdir}/${_gemdir}/gems/${_gemname}-${pkgver}/LICENSE" \
		"${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
