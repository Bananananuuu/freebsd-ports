# $FreeBSD$

PORTNAME=	modules2tuple
PORTVERSION=	1.1.0
CATEGORIES=	devel

MAINTAINER=	dg@syrec.org
COMMENT=	Generate GH_TUPLE from modules.txt

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USES=		go:modules

GO_PKGNAME=	github.com/${GH_ACCOUNT}/${PORTNAME}

USE_GITHUB=	yes
GH_TUPLE=	dmgk:${PORTNAME}:v${PORTVERSION}:DEFAULT

PLIST_FILES=	bin/${PORTNAME}

.include <bsd.port.mk>
