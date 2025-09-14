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

RUN_DEPENDS=   docopts:devel/docopts \
               ${AWK}:lang/awk \
               sqlite3:databases/sqlite3 \
               parallel:sysutils/parallel

OPTIONS_DEFINE=    WATCHER ZFS
OPTIONS_DEFAULT=   WATCHER

WATCHER_DESC=        Enable support for watching directories using fswatch for monitoring file changes and making reflinks on the go.
WATCHER_RUN_DEPENDS= fswatch:sysutils/fswatch-mon

ZFS_DESC=            Enable support for zpool statistics monitoring in interactive mode. (optional)


do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/reflink_dedupe \
	    ${STAGEDIR}${PREFIX}/bin/reflink_dedupe

	${INSTALL_SCRIPT} ${WRKSRC}/rc.d/reflink_dedupe \
	    ${STAGEDIR}${PREFIX}/etc/rc.d/reflink_dedupe

	${INSTALL_DATA} ${WRKSRC}/newsyslog.d/reflink_dedupe.conf \
	    ${STAGEDIR}${PREFIX}/etc/newsyslog.conf.d/reflink_dedupe.conf

	${INSTALL_DATA} ${WRKSRC}/reflink_dedupe.conf \
	    ${STAGEDIR}${PREFIX}/etc/reflink_dedupe.conf.sample

.include <bsd.port.mk>
