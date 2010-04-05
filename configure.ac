#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.60])
AC_INIT([libICE],
        [1.0.6],
        [https://bugs.freedesktop.org/enter_bug.cgi?product=xorg],
        [libICE])

AC_CONFIG_SRCDIR([Makefile.am])
AM_INIT_AUTOMAKE([foreign dist-bzip2])

AM_MAINTAINER_MODE
AM_CONFIG_HEADER([config.h])

# Require xorg-macros: XORG_DEFAULT_OPTIONS
m4_ifndef([XORG_MACROS_VERSION],
	  [m4_fatal([must install xorg-macros 1.3 or later before running autoconf/autogen])])
XORG_MACROS_VERSION(1.3)
XORG_DEFAULT_OPTIONS

# Checks for programs.
AC_PROG_LIBTOOL
AC_PROG_CC

# Checks for pkg-config packages
PKG_CHECK_MODULES(ICE, xproto)

PKG_CHECK_MODULES(XTRANS, xtrans)
AC_SUBST(XTRANS_CFLAGS)
AC_SUBST(XTRANS_LIBS)

# Transport selection macro from xtrans.m4
XTRANS_CONNECTION_FLAGS
AC_DEFINE(ICE_t, 1, [Xtrans transport type])

# Checks for libraries.

# Checks for header files.
AC_HEADER_STDC

dnl Allow checking code with lint, sparse, etc.
XORG_WITH_LINT
XORG_LINT_LIBRARY([ICE])
LINT_FLAGS="${LINT_FLAGS} ${ICE_CFLAGS} ${XTRANS_CFLAGS}"


AC_OUTPUT([Makefile
	   src/Makefile
	   ice.pc])
