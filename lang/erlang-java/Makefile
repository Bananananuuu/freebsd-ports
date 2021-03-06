# $FreeBSD$

PORTNAME=	erlang
DISTVERSIONPREFIX=	OTP-
DISTVERSION=	19.3.6.13
PORTEPOCH=	1
CATEGORIES=	lang parallel java
PKGNAMESUFFIX=	-java
DIST_SUBDIR=	erlang

MAINTAINER=	erlang@FreeBSD.org
COMMENT=	Erlang interface for Java

LICENSE=	APACHE20

RUN_DEPENDS=	erl:lang/erlang

USES=		autoreconf:build gmake perl5
USE_GITHUB=	yes
GH_PROJECT=	otp
USE_JAVA=	yes
USE_PERL5=	build

GNU_CONFIGURE=	yes
MAKE_JOBS_UNSAFE=yes

PLIST_SUB=	APP_VERSION=${APP_VERSION}

APP_VERSION=	1.7.1
APP_DIR=	${PREFIX}/lib/erlang/lib/jinterface-${APP_VERSION}
ERLANG_REL=	19.3

CONFIGURE_ARGS+=--enable-threads --without-odbc --with-javac --without-wx
CONFIGURE_ENV+=	ac_cv_prog_JAVAC="${JAVAC}"

pre-configure:
	@cd ${WRKSRC} && ./otp_build autoconf

do-build:
	@${MKDIR} ${WRKSRC}/lib/jinterface/ebin
	cd ${WRKSRC}/lib/jinterface && ${GMAKE} ERL_TOP=${WRKSRC} TARGET=${CONFIGURE_TARGET}
	${RM} -r ${WRKSRC}/lib/jinterface/priv/com

do-install:
	@${MKDIR} ${STAGEDIR}${APP_DIR}
	@${MKDIR} ${STAGEDIR}${APP_DIR}/priv
	cd ${WRKSRC}/lib/jinterface && ${COPYTREE_SHARE} ebin ${STAGEDIR}${APP_DIR}
	cd ${WRKSRC}/lib/jinterface && ${COPYTREE_SHARE} java_src ${STAGEDIR}${APP_DIR}
	${INSTALL_DATA} ${WRKSRC}/lib/jinterface/priv/OtpErlang.jar ${STAGEDIR}${APP_DIR}/priv

.include <bsd.port.mk>
