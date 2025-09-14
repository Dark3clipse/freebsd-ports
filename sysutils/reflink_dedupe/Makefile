PORTNAME=      reflink_dedupe
PORTVERSION=   0.9.0
CATEGORIES=    sysutils

MAINTAINER=     admin@mediarr.org
COMMENT=        A FreeBSD utility for deduplicating a filesystem using reflinks.
LICENSE=        BSD2CLAUSE

USE_GITHUB=     yes
GH_ACCOUNT=     Dark3clipse
GH_PROJECT=     ${PORTNAME}
GH_TAGNAME=     v${PORTVERSION}

NO_BUILD=      yes
NO_ARCH=       yes

do-install:
	${INSTALL_SCRIPT} ${FILESDIR}/reflink_dedupe \
	    ${STAGEDIR}${PREFIX}/bin/reflink_dedupe

	${INSTALL_SCRIPT} ${FILESDIR}/rc.d/reflink_dedupe \
	    ${STAGEDIR}${PREFIX}/etc/rc.d/reflink_dedupe

	${INSTALL_DATA} ${FILESDIR}/newsyslog.d/reflink_dedupe.conf \
	    ${STAGEDIR}${PREFIX}/etc/newsyslog.conf.d/reflink_dedupe.conf

	${INSTALL_DATA} ${FILESDIR}/reflink_dedupe.conf \
	    ${STAGEDIR}${PREFIX}/etc/reflink_dedupe.conf.sample

.include <bsd.port.mk>
