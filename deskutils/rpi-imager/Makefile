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

USES=		compiler:c++20-lang qt:6 cmake pkgconfig libarchive:run \
		desktop-file-utils gl shared-mime-info
USE_QT=		base tools:build svg declarative imageformats:run
USE_GL=		opengl

USE_GITHUB=	yes
GH_ACCOUNT=	jainnimish

WRKSRC_SUBDIR=	src

CMAKE_ARGS=	-DDEFAULT_VERSION_STRING="v2.0.10"
CMAKE_ON=	BUILD_REPO_PACKAGE
CMAKE_OFF=	ENABLE_CHECK_VERSION
CMAKE_OFF=	ENABLE_TELEMETRY

.include <bsd.port.mk>
