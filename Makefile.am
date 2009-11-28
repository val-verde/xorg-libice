SUBDIRS = src

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = ice.pc

MAINTAINERCLEANFILES = ChangeLog INSTALL
EXTRA_DIST=ice.pc.in 

.PHONY: ChangeLog INSTALL

INSTALL:
	$(INSTALL_CMD)

ChangeLog:
	$(CHANGELOG_CMD)

dist-hook: ChangeLog INSTALL

if LINT
lint:
	(cd src && $(MAKE) $(MFLAGS) lint)
endif LINT
