# Created by: Sunpoet Po-Chuan Hsieh <sunpoet@FreeBSD.org>
# $FreeBSD$

PORTNAME=	geoalchemy2
PORTVERSION=	0.6.1
CATEGORIES=	databases geography python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	GeoAlchemy2-${PORTVERSION}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Using SQLAlchemy with Spatial Databases

LICENSE=	MIT

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}sqlalchemy12>=0.8:databases/py-sqlalchemy12@${PY_FLAVOR}

USES=		python
USE_PYTHON=	autoplist concurrent distutils

NO_ARCH=	yes

.include <bsd.port.mk>
