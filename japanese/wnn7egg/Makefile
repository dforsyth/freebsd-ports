PORTNAME=	wnn7egg
PORTVERSION=	1.02
PORTREVISION=	1
CATEGORIES=	japanese elisp
MASTER_SITES=	http://www.omronsoft.co.jp/SP/pcunix/wnn7/support/modules/wnn7egg/
DISTNAME=	wnn7-elisp-el-1.02-1
EXTRACT_SUFX=	.tgz

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Wnn7 elisp client
WWW=		https://www.omronsoft.co.jp/SP/pcunix/wnn7/support/wnn7egg_src.html

DEPRECATED=	Upstream disapeared and distfile is no more available
EXPIRATION_DATE=2025-03-31

EMACSDIR=	${STAGEDIR}${PREFIX}/share/emacs/site-lisp
ELISPDIR=	${EMACSDIR}/wnn7egg
MANIFEST=	MANIFEST.wnn7egg
WRKSRC=		${WRKDIR}/wnn7/elisp

NO_BUILD=	yes

PORTDOCS=	README Setup_wnn7egg

OPTIONS_DEFINE=	DOCS

do-install:
	${MKDIR} ${ELISPDIR}/its-v309
	${INSTALL_DATA} ${WRKSRC}/emacs20/*.el ${ELISPDIR}
	${INSTALL_DATA} ${WRKSRC}/emacs20/its-v309/*.el ${ELISPDIR}/its-v309

	${INSTALL_DATA} ${WRKSRC}/emacs20/eggrc-wnn7 ${ELISPDIR}
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
