#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.57)
AC_INIT([libICE],
        6.3.5,
        [keithp@keithp.com],
        libICE)

AC_CONFIG_SRCDIR([Makefile.am])
AM_INIT_AUTOMAKE([1.7], [dist-bzip2])

AM_MAINTAINER_MODE

AM_CONFIG_HEADER([config.h])

# Checks for programs.
AC_PROG_LIBTOOL
AC_PROG_CC

# Checks for pkg-config packages
PKG_CHECK_MODULES(ICE, xproto)
AC_SUBST(ICE_CFLAGS)
AC_SUBST(ICE_LIBS)

PKG_CHECK_MODULES(XTRANS, xtrans)
AC_SUBST(XTRANS_CFLAGS)
AC_SUBST(XTRANS_LIBS)

AC_DEFINE(LOCALCONN, 1, [Support local connections])
AC_DEFINE(UNIXCONN, 1, [Support UNIX socket connections])

# Checks for libraries.

# Checks for header files.
AC_HEADER_STDC

if test "x$GCC" = "xyes"; then
	GCC_WARNINGS="-Wall -Wpointer-arith -Wstrict-prototypes \
	-Wmissing-prototypes -Wmissing-declarations \
	-Wnested-externs -fno-strict-aliasing"
	CFLAGS="$GCC_WARNINGS $CFLAGS"
fi

AC_OUTPUT([Makefile
	   src/Makefile
	   ice.pc])
