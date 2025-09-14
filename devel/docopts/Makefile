PORTNAME=      docopts
PORTVERSION=   0.6.4
DISTVERSION=   0.6.4-with-no-mangle-double-dash
CATEGORIES=    devel

MAINTAINER=    admin@mediarr.org
COMMENT=       Command-line option parser for shell scripts
LICENSE=       MIT

USE_GITHUB=    yes
GH_ACCOUNT=    docopt
GH_PROJECT=    docopts
GH_TAGNAME=    v${PORTVERSION}

NO_BUILD=      yes
ONLY_FOR_ARCHS= amd64

PLIST_FILES=   bin/docopts

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/docopts_freebsd_amd64 \
	    ${STAGEDIR}${PREFIX}/bin/docopts

.include <bsd.port.mk>
