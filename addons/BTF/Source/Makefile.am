AM_CPPFLAGS = -I$(top_srcdir)/Include @SUITESPARSECONFIG_CFLAGS@
AM_LDFLAGS = -version-info @LT_CURRENT@:@LT_REVISION@:@LT_AGE@

BTFSRC = \
	$(top_srcdir)/Include/btf_internal.h \
	$(top_srcdir)/Include/btf.h \
	btf_order.c \
	btf_maxtrans.c \
	btf_strongcomp.c

noinst_LTLIBRARIES = libbtfi.la libbtfl.la
libbtfi_la_SOURCES = $(BTFSRC)
libbtfi_la_CPPFLAGS = $(AM_CPPFLAGS)
libbtfl_la_SOURCES = $(BTFSRC)
libbtfl_la_CPPFLAGS = $(AM_CPPFLAGS) -DDLONG

lib_LTLIBRARIES = libbtf.la
libbtf_la_SOURCES =
libbtf_la_LIBADD = libbtfl.la libbtfi.la @SUITESPARSECONFIG_LIBS@

MAINTAINERCLEANFILES = Makefile.in
