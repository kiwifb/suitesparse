ACLOCAL_AMFLAGS = -I m4
AM_LDFLAGS = -version-info @LT_CURRENT@:@LT_REVISION@:@LT_AGE@

include $(top_srcdir)/config/common.am

DISTCHECK_CONFIGURE_FLAGS = \
	--with-check \
	--with-cholesky \
	--with-matrixops \
	--with-modify \
	--with-supernodal \
	--with-doc

EXTRA_SUBDIRS=
EXTRA_LIBADD=

if WITH_CUDA
EXTRA_SUBDIRS += GPU
EXTRA_LIBADD += \
	$(top_builddir)/GPU/libcholmod_gpu.la
endif

if WITH_CHECK
EXTRA_SUBDIRS += Check
EXTRA_LIBADD += \
	$(top_builddir)/Check/libcheck.la \
	$(top_builddir)/Check/libcheckl.la
endif

if WITH_CHOLESKY
EXTRA_SUBDIRS += Cholesky
EXTRA_LIBADD += \
	$(top_builddir)/Cholesky/libcholesky.la \
	$(top_builddir)/Cholesky/libcholeskyl.la 
endif

if WITH_MATRIXOPS
EXTRA_SUBDIRS += MatrixOps
EXTRA_LIBADD += \
	$(top_builddir)/MatrixOps/libmatrixops.la \
	$(top_builddir)/MatrixOps/libmatrixopsl.la
endif

if WITH_MODIFY
EXTRA_SUBDIRS += Modify
EXTRA_LIBADD += \
	$(top_builddir)/Modify/libmodify.la \
	$(top_builddir)/Modify/libmodifyl.la
endif

if WITH_PARTITION
EXTRA_SUBDIRS += Partition
EXTRA_LIBADD += \
	$(top_builddir)/Partition/libpartition.la \
	$(top_builddir)/Partition/libpartitionl.la
endif

if WITH_SUPERNODAL
EXTRA_SUBDIRS += Supernodal
EXTRA_LIBADD += \
	$(top_builddir)/Supernodal/libsupernodal.la \
	$(top_builddir)/Supernodal/libsupernodall.la
endif

lib_LTLIBRARIES = libcholmod.la

SUBDIRS = Cored Include $(EXTRA_SUBDIRS) Demo Doc

libcholmod_la_SOURCES = 
libcholmod_la_LIBADD = \
	$(EXTRA_LIBADD) \
	$(top_builddir)/Cored/libcore.la \
	$(top_builddir)/Cored/libcorel.la
