AM_CPPFLAGS = -I$(top_srcdir)/Include @SUITESPARSECONFIG_CFLAGS@
AM_LDFLAGS = -version-info @LT_CURRENT@:@LT_REVISION@:@LT_AGE@

lib_LTLIBRARIES = libccolamd.la
noinst_LTLIBRARIES = libccolamdi.la libccolamdl.la

libccolamdl_la_SOURCES = ccolamd.c $(top_srcdir)/Include/ccolamd.h
libccolamdl_la_CPPFLAGS = $(AM_CPPFLAGS) -DDLONG

libccolamdi_la_SOURCES = $(libccolamdl_la_SOURCES)

libccolamd_la_SOURCES =
libccolamd_la_LIBADD = libccolamdi.la libccolamdl.la @SUITESPARSECONFIG_LIBS@

MAINTAINERCLEANFILES = Makefile.in

