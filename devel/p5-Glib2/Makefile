# Created by: clsung@dragon2.net
# $FreeBSD$

PORTNAME=	Glib
PORTVERSION=	1.329
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN SF/gtk2-perl/${PORTNAME}/${PORTVERSION}
MASTER_SITE_SUBDIR=	CPAN:XAOC
PKGNAMEPREFIX=	p5-
PKGNAMESUFFIX=	2

MAINTAINER=	swills@FreeBSD.org
COMMENT=	This module provides access to Glib and GObject libraries

LICENSE=	LGPL21
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${RUN_DEPENDS}
RUN_DEPENDS=	p5-ExtUtils-Depends>=0.300:devel/p5-ExtUtils-Depends \
		p5-ExtUtils-PkgConfig>=1:devel/p5-ExtUtils-PkgConfig

USE_GNOME=	glib20
USES=		perl5
USE_PERL5=	configure
MAKE_JOBS_UNSAFE=	yes

.include <bsd.port.mk>
