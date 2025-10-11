PORTNAME=      zmonitor
PORTVERSION=   0.1.0
CATEGORIES=    sysutils

MAINTAINER=     admin@mediarr.org
COMMENT=        A FreeBSD utility for sending node utilization and zpool statistics over a serial connection.
LICENSE=        BSD2CLAUSE

USE_GITHUB=     yes
GH_ACCOUNT=     Dark3clipse
GH_PROJECT=     ${PORTNAME}
GH_TAGNAME=     v${PORTVERSION}

NO_BUILD=      yes
NO_ARCH=       yes

USES=          python:run shebangfix
SHEBANG_FILES= zmonitor.py

RUN_DEPENDS=   ${PYTHON_PKGNAMEPREFIX}psutil>=0:sysutils/py-psutil@${PY_FLAVOR}
               ${PYTHON_PKGNAMEPREFIX}pyserial>=3.5:comms/py-pyserial@${PY_FLAVOR}


OPTIONS_DEFINE=
OPTIONS_DEFAULT=


do-install:
	# Create staging directories
	${MKDIR} ${STAGEDIR}${PREFIX}/bin
	${MKDIR} ${STAGEDIR}${PREFIX}/etc/rc.d
	${MKDIR} ${STAGEDIR}${PREFIX}/etc

	# Install files under ${PREFIX}
	${INSTALL_SCRIPT} ${WRKSRC}/zmonitor.py \
		${STAGEDIR}${PREFIX}/bin/zmonitor.py

	${INSTALL_SCRIPT} ${WRKSRC}/rc.d/zmonitor \
		${STAGEDIR}${PREFIX}/etc/rc.d/zmonitor

	${INSTALL_DATA} ${WRKSRC}/zmonitor.conf \
		${STAGEDIR}${PREFIX}/etc/zmonitor.conf.sample

.include <bsd.port.mk>
