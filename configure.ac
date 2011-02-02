
# Initialize Autoconf
AC_PREREQ([2.60])
AC_INIT([libICE], [1.0.7],
        [https://bugs.freedesktop.org/enter_bug.cgi?product=xorg], [libICE])
AC_CONFIG_SRCDIR([Makefile.am])
AC_CONFIG_HEADERS([config.h])

# Set common system defines for POSIX extensions, such as _GNU_SOURCE
# Must be called before any macros that run the compiler (like
# AC_PROG_LIBTOOL or XORG_DEFAULT_OPTIONS) to avoid autoconf errors.
AC_USE_SYSTEM_EXTENSIONS

# Initialize Automake
AM_INIT_AUTOMAKE([foreign dist-bzip2])
AM_MAINTAINER_MODE

# Initialize libtool
AC_PROG_LIBTOOL

# Require xorg-macros minimum of 1.10 for DocBook XML documentation
m4_ifndef([XORG_MACROS_VERSION],
          [m4_fatal([must install xorg-macros 1.10 or later before running autoconf/autogen])])
XORG_MACROS_VERSION(1.10)
XORG_DEFAULT_OPTIONS
XORG_ENABLE_DOCS
XORG_ENABLE_SPECS
XORG_WITH_XMLTO(0.0.20)
XORG_WITH_FOP
XORG_CHECK_SGML_DOCTOOLS(1.5)

# Obtain compiler/linker options for depedencies
PKG_CHECK_MODULES(ICE, xproto)
PKG_CHECK_MODULES(XTRANS, xtrans)

# Transport selection macro from xtrans.m4
XTRANS_CONNECTION_FLAGS
AC_DEFINE(ICE_t, 1, [Xtrans transport type])

# Checks for library functions.
AC_CHECK_FUNCS([asprintf])

# Allow checking code with lint, sparse, etc.
XORG_WITH_LINT
XORG_LINT_LIBRARY([ICE])
LINT_FLAGS="${LINT_FLAGS} ${ICE_CFLAGS} ${XTRANS_CFLAGS}"

AC_CONFIG_FILES([Makefile
		doc/Makefile
		specs/Makefile
		src/Makefile
		ice.pc])
AC_OUTPUT
