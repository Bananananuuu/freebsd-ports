# Created by: Joe Marcus Clarke <marcus@FreeBSD.org>
# $FreeBSD$
#   $MCom: ports/trunk/graphics/gthumb/Makefile 19823 2014-08-20 09:28:14Z gusi $

PORTNAME=	gthumb
PORTVERSION=	3.6.1
PORTREVISION=	7
CATEGORIES=	graphics
MASTER_SITES=	GNOME
DIST_SUBDIR=	gnome3

MAINTAINER=	gnome@FreeBSD.org
COMMENT=	Image viewer and browser for the GNOME 3 environment

LICENSE=	GPLv2+

BUILD_DEPENDS=	gsettings-desktop-schemas>0:devel/gsettings-desktop-schemas \
		itstool:textproc/itstool
LIB_DEPENDS=	libclutter-1.0.so:graphics/clutter \
		libcogl.so:graphics/cogl \
		libgstreamer-1.0.so:multimedia/gstreamer1 \
		libjson-glib-1.0.so:devel/json-glib \
		liblcms2.so:graphics/lcms2 \
		liboauth.so:net/liboauth \
		libomp.so:devel/openmp \
		libpng.so:graphics/png \
		libsoup-2.4.so:devel/libsoup \
		libtiff.so:graphics/tiff
RUN_DEPENDS=	gsettings-desktop-schemas>0:devel/gsettings-desktop-schemas

USES=		bison compiler:c++11-lib desktop-file-utils gettext gmake \
		jpeg libtool localbase pathfix pkgconfig tar:xz
USE_GL=		egl
USE_GNOME=	cairo gtk30 intltool librsvg2
USE_XORG=	x11 xcomposite xdamage xext xfixes xrandr xi
GNU_CONFIGURE=	yes
CONFIGURE_ENV=	ac_cv_lib_jpeg_jpeg_destroy_decompress=yes \
		ac_cv_lib_tiff_TIFFWriteScanline=yes
CONFIGURE_ARGS=	--disable-libchamplain \
		--enable-librsvg
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes
INSTALLS_ICONS=	yes

PLIST_SUB=	GTHUMB_VER="3.6"

GLIB_SCHEMAS=	org.gnome.gthumb.change-date.gschema.xml \
		org.gnome.gthumb.comments.gschema.xml \
		org.gnome.gthumb.contact-sheet.gschema.xml \
		org.gnome.gthumb.convert-format.gschema.xml \
		org.gnome.gthumb.crop.gschema.xml \
		org.gnome.gthumb.enums.xml \
		org.gnome.gthumb.facebook.gschema.xml \
		org.gnome.gthumb.file-manager.gschema.xml \
		org.gnome.gthumb.flickr.gschema.xml \
		org.gnome.gthumb.gschema.xml \
		org.gnome.gthumb.gstreamer-tools.gschema.xml \
		org.gnome.gthumb.image-print.gschema.xml \
		org.gnome.gthumb.image-viewer.gschema.xml \
		org.gnome.gthumb.importer.gschema.xml \
		org.gnome.gthumb.photo-importer.gschema.xml \
		org.gnome.gthumb.picasaweb.gschema.xml \
		org.gnome.gthumb.pixbuf-savers.gschema.xml \
		org.gnome.gthumb.rename-series.gschema.xml \
		org.gnome.gthumb.resize-images.gschema.xml \
		org.gnome.gthumb.resize.gschema.xml \
		org.gnome.gthumb.rotate.gschema.xml \
		org.gnome.gthumb.slideshow.gschema.xml \
		org.gnome.gthumb.webalbums.gschema.xml

OPTIONS_DEFINE=		BRASERO CLUTTER EXIV2 GSTREAMER RAW SECRET \
			WEBP WEBSERVICES YELP
OPTIONS_DEFAULT=	BRASERO CLUTTER EXIV2 GSTREAMER RAW SECRET \
			WEBP WEBSERVICES YELP
OPTIONS_SUB=		yes

BRASERO_DESC=		Write galleries to CD/DVD (large dependency)
BRASERO_LIB_DEPENDS=	libbrasero-media3.so:sysutils/brasero
BRASERO_CONFIGURE_ENABLE=	libbrasero
CLUTTER_DESC=		Fancy slideshows
CLUTTER_LIB_DEPENDS=	libclutter-gtk-1.0.so:graphics/clutter-gtk3
CLUTTER_CONFIGURE_ENABLE=	clutter
EXIV2_LIB_DEPENDS=	libexiv2.so:graphics/exiv2
EXIV2_CONFIGURE_ENABLE=	exiv2
GSTREAMER_USE=		gstreamer1=yes
GSTREAMER_CONFIGURE_ENABLE=	gstreamer
RAW_DESC=		Raw image support via libraw
RAW_LIB_DEPENDS=	libraw.so:graphics/libraw
RAW_CONFIGURE_ENABLE=	libraw
SECRET_DESC=		Libsecret support for storing passwords
SECRET_LIB_DEPENDS=	libsecret-1.so:security/libsecret
SECRET_CONFIGURE_ENABLE=	libsecret
WEBP_LIB_DEPENDS=	libwebp.so:graphics/webp
WEBP_CONFIGURE_ENABLE=	libwebp
WEBSERVICES_DESC=	Web services
WEBSERVICES_LIB_DEPENDS=\
			libjson-glib-1.0.so:devel/json-glib \
			libsoup-gnome-2.4.so:devel/libsoup-gnome \
			libwebkit2gtk-4.0.so:www/webkit2-gtk3
WEBSERVICES_CONFIGURE_ENABLE=	libjson-glib libsoup webkit2
YELP_DESC=		Viewer for built-in help system
YELP_RUN_DEPENDS=	yelp:x11/yelp

post-patch:
	@${REINPLACE_CMD} -e 's|-Wl,--as-needed||' ${WRKSRC}/configure

.include <bsd.port.mk>
