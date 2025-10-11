PORTNAME=      lsdisks
PORTVERSION=   1.0.0
CATEGORIES=    sysutils

MAINTAINER=     admin@mediarr.org
COMMENT=        A FreeBSD utility for listing disks, partitions, and associated zpools.
LICENSE=        BSD2CLAUSE

USE_GITHUB=     yes
GH_ACCOUNT=     Dark3clipse
GH_PROJECT=     ${PORTNAME}
GH_TAGNAME=     v${PORTVERSION}

NO_BUILD=      yes
NO_ARCH=       yes

RUN_DEPENDS=   smartctl:sysutils/smartmontools


do-install:
	# Create staging directories
	${MKDIR} ${STAGEDIR}${PREFIX}/bin

	# Install files under ${PREFIX}
	${INSTALL_SCRIPT} ${WRKSRC}/lsdisks \
		${STAGEDIR}${PREFIX}/bin/lsdisks

.include <bsd.port.mk>
