EXTRA_DIST = \
	test.config \
	flash.conf

CLEANFILES =
ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}
AM_MAKEFLAGS = --no-print-directory

AM_CPPFLAGS = \
	-include $(top_builddir)/config.h \
	-DSYSCONFDIR=\""$(sysconfdir)"\" \
	-DLIBEXECDIR=\""$(libexecdir)"\"

AM_CFLAGS = ${my_CFLAGS} \
	-fvisibility=hidden \
	-ffunction-sections \
	-fdata-sections

AM_LDFLAGS = \
	-Wl,--gc-sections \
	-Wl,--as-needed

bin_PROGRAMS = genimage
genimage_SOURCES = \
	genimage.c \
	config.c \
	util.c \
	image-ext2.c \
	image-file.c \
	image-flash.c \
	image-hd.c \
	image-jffs2.c \
	image-tar.c \
	image-ubi.c \
	image-ubifs.c

genimage_CFLAGS = \
	$(AM_CFLAGS) \
	$(CONFUSE_CFLAGS)

genimage_LDADD = \
	$(CONFUSE_LIBS)

noinst_HEADERS = \
	genimage.h \
	list.h
