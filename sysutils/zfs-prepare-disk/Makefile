PORTNAME=      zfs-prepare-disk
PORTVERSION=   1.0.0
CATEGORIES=    sysutils

MAINTAINER=     admin@mediarr.org
COMMENT=        A FreeBSD utility for preparing a disk for ZFS.
LICENSE=        BSD2CLAUSE

USE_GITHUB=     yes
GH_ACCOUNT=     Dark3clipse
GH_PROJECT=     ${PORTNAME}
GH_TAGNAME=     v${PORTVERSION}

NO_BUILD=      yes
NO_ARCH=       yes

RUN_DEPENDS=   bash:shells/bash \
               docopts:devel/docopts


do-install:
	# Create staging directories
	${MKDIR} ${STAGEDIR}${PREFIX}/bin

	# Install files under ${PREFIX}
	${INSTALL_SCRIPT} ${WRKSRC}/zfs-prepare-disk \
		${STAGEDIR}${PREFIX}/bin/zfs-prepare-disk

.include <bsd.port.mk>
