PORTNAME=      docopts
PORTVERSION=   0.6.4
DISTVERSION=   0.6.4-with-no-mangle-double-dash
CATEGORIES=    devel

MAINTAINER=    admin@mediarr.org
COMMENT=       Command-line option parser for shell scripts
LICENSE=       MIT

ONLY_FOR_ARCHS= amd64
NO_BUILD=       yes
NO_CHECKSUM=    yes
NO_EXTRACT=     yes

DISTFILES=     docopts_freebsd_amd64
MASTER_SITES=  https://github.com/docopt/docopts/releases/download/v${DISTVERSION}/

PLIST_FILES=   bin/docopts

do-install:
	${INSTALL_PROGRAM} ${DISTDIR}/docopts_freebsd_amd64 \
	    ${STAGEDIR}${PREFIX}/bin/docopts

.include <bsd.port.mk>
