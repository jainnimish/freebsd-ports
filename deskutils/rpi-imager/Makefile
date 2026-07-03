PORTNAME=	rpi-imager
DISTVERSIONPREFIX=v
DISTVERSION=	2.0.10
CATEGORIES=	deskutils

MAINTAINER=	njain15@protonmail.com
COMMENT=	Raspberry Pi Imaging Utility
WWW=		https://github.com/jainnimish/rpi-imager

LICENSE=	APACHE20
LICENSE_FILE=	${WRKDIR}/${PORTNAME}-${PORTVERSION}/license.txt

LIB_DEPENDS=	libcurl.so:ftp/curl \
		libgnutls.so:security/gnutls \
		libidn2.so:dns/libidn2 \
		libnettle.so:security/nettle \
		libzstd.so:archivers/zstd

FLAVORS=	default cli
FLAVOR?=	${FLAVORS:[1]}
cli_PKGNAMESUFFIX=-cli

USES=	qt:6 cmake pkgconfig libarchive:run
USE_QT=	base tools:build

USE_GITHUB=	yes
GH_ACCOUNT=	jainnimish

WRKSRC_SUBDIR=	src
CMAKE_ON=	USE_LOCAL_ONLY

.if ${FLAVOR} == cli
CMAKE_ON+=	BUILD_CLI_ONLY
PLIST_SUB=	GUI="@comment " CLI=""
.else
USES+=		desktop-file-utils gl shared-mime-info
USE_QT+=	svg declarative imageformats:run
USE_GL=		opengl
PLIST_SUB=	CLI="@comment " GUI=""
.endif

.include <bsd.port.mk>