SUBDIRS = src

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = ice.pc

EXTRA_DIST=ice.pc.in ChangeLog

CLEANFILES=ChangeLog

.PHONY: ChangeLog

ChangeLog:
	env GIT_DIR=${srcdir}/.git git-log > ChangeLog

dist-hook: ChangeLog
