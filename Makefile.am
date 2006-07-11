SUBDIRS = src

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = ice.pc

EXTRA_DIST=ice.pc.in ChangeLog

CLEANFILES=ChangeLog

.PHONY: ChangeLog

ChangeLog:
	git-log > ChangeLog

dist-hook: ChangeLog
