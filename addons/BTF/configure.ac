AC_INIT([btf], [1.2.0], [davis@tamu.edu])

AC_CONFIG_SRCDIR([Source/btf_order.c])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_AUX_DIR([config])

AM_INIT_AUTOMAKE([no-dist-gzip dist-bzip2 foreign])

# use silent rules if available - automake 1.11
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES(yes)])

LT_INIT
LT_CURRENT=@SO_NAME@
LT_REVISION=0
LT_AGE=0
AC_SUBST(LT_CURRENT)
AC_SUBST(LT_REVISION)
AC_SUBST(LT_AGE)

AC_PROG_CC

# Checks for typedefs, structures, and compiler characteristics
AC_FUNC_ERROR_AT_LINE

# Checks and automatically links with required system libraries
AC_CHECK_LIB([m], [sqrt])

# Checks for required SuiteSparse libraries
AX_CHECK_PKG_LIB(
	[suitesparseconfig],
	[SuiteSparse_config.h],
	[SuiteSparse_malloc],,
	[AC_MSG_ERROR([Could not find suitesparseconfig library])])

AC_CONFIG_FILES([Doc/Makefile
                 Source/Makefile
                 btf.pc
                 Makefile])
AC_OUTPUT
