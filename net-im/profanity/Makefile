# $FreeBSD$

PORTNAME=	profanity
PORTVERSION=	0.6.0
PORTREVISION=	1
CATEGORIES=	net-im
MASTER_SITES=	http://www.profanity.im/ \
		LOCAL/arved

MAINTAINER=	arved@FreeBSD.org
COMMENT=	Console based XMPP client

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BUILD_DEPENDS=	autoconf-archive>=0:devel/autoconf-archive
LIB_DEPENDS=	libmesode.so:net-im/libmesode \
		libcurl.so:ftp/curl \
		libotr.so.5:security/libotr \
		libuuid.so:misc/e2fsprogs-libuuid \
		libgpgme.so:security/gpgme \
		libassuan.so:security/libassuan \
		libgpg-error.so:security/libgpg-error

USES=		ncurses pkgconfig ssl python readline autoreconf libtool gnome
USE_GNOME=	glib20

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--enable-otr --enable-python-plugins --enable-c-plugins \
		--enable-pgp --enable-icons=no --with-xscreensaver=no
CONFIGURE_ENV=	LIBS="${CFLAGS} -lcrypto"
INSTALL_TARGET=	install-strip
OPTIONS_DEFINE=	NOTIFY

NOTIFY_LIB_DEPENDS=	libnotify.so:devel/libnotify
NOTIFY_CONFIGURE_ENABLE=notifications

.include <bsd.port.pre.mk>

post-patch:
	${REINPLACE_CMD} "s,python-config,${PYTHON_VERSION}-config,g" \
		${WRKSRC}/configure.ac

.include <bsd.port.post.mk>
