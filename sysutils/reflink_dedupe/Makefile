PORTNAME=      reflink_dedupe
PORTVERSION=   1.0.0
CATEGORIES=    sysutils
MASTER_SITES=  https://github.com/Dark3clipse/reflink_dedupe/releases/download/v${PORTVERSION}/
DISTFILES=     ${PORTNAME}-${PORTVERSION}.tar.gz

MAINTAINER=    admin@mediarr.org
COMMENT=       A FreeBSD utility for deduplicating a filesystem using reflinks.

LICENSE=       BSD2CLAUSE

NO_BUILD=      yes
NO_ARCH=       yes

do-install:
	${INSTALL_SCRIPT} ${FILESDIR}/reflink_dedupe \
	    ${STAGEDIR}${PREFIX}/bin/reflink_dedupe

	${INSTALL_SCRIPT} ${FILESDIR}/reflink_dedupe.in \
	    ${STAGEDIR}${PREFIX}/etc/rc.d/reflink_dedupe

	${INSTALL_DATA} ${FILESDIR}/reflink_dedupe.newsyslog \
	    ${STAGEDIR}${PREFIX}/etc/newsyslog.conf.d/reflink_dedupe.conf

	${INSTALL_DATA} ${FILESDIR}/reflink_dedupe.conf \
	    ${STAGEDIR}${PREFIX}/etc/reflink_dedupe.conf.sample
