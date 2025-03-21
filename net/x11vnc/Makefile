PORTNAME=	x11vnc
PORTVERSION=	0.9.16
PORTREVISION=	8
CATEGORIES=	net

MAINTAINER=	dinoex@FreeBSD.org
COMMENT=	VNC server for use with real X displays
WWW=		https://github.com/LibVNC/x11vnc

LICENSE=	GPLv2

LIB_DEPENDS=	libvncserver.so:net/libvncserver

USES=		cpe iconv pkgconfig jpeg ssl gmake autoreconf xorg
USE_XORG=	x11 xcb xdamage xfixes xrandr xinerama xext xtst xau xrender \
		xdmcp xi xorgproto
# Sets LDFLAGS and adds to CONFIGURE_ENV, therefore we set LDFLAGS
LDFLAGS+=	-L${LOCALBASE}/lib
GNU_CONFIGURE=	yes
GNU_CONFIGURE_MANPREFIX=	${PREFIX}/share
CONFIGURE_ARGS=	--with-ssl=${OPENSSLBASE}
CPPFLAGS+=	-I${LOCALBASE}/include
USE_GITHUB=	yes
GH_ACCOUNT=	LibVNC

CPE_VENDOR=	x11vnc_project

PORTDOCS=	AUTHORS ChangeLog NEWS README

OPTIONS_DEFINE=	NLS AVAHI DOCS
OPTIONS_DEFAULT=AVAHI
NO_OPTIONS_SORT=yes
NLS_USES=	gettext
AVAHI_LIB_DEPENDS=	libavahi-common.so:net/avahi-app
AVAHI_CONFIGURE_OFF=	--without-avahi

post-install-DOCS-on:
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S,^,${WRKSRC}/,} ${STAGEDIR}${DOCSDIR}/

.include <bsd.port.mk>
