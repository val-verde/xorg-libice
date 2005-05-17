lib_LTLIBRARIES=libICE.la

AM_CFLAGS= -I${top_srcdir}/include $(ICE_CFLAGS) $(XTRANS_CFLAGS)

libICE_la_LDFLAGS = -version-number 6:4:1 -no-undefined

libICE_la_LIBADD = $(ICE_LIBS) $(XTRANS_LIBS)

libICE_la_SOURCES = \
	ICElibint.h \
	accept.c \
	authutil.c \
	connect.c \
	error.c \
	getauth.c \
	globals.h \
	iceauth.c \
	icetrans.c \
	listen.c \
	listenwk.c \
	locking.c \
	misc.c \
	ping.c \
	process.c \
	protosetup.c \
	register.c \
	replywait.c \
	setauth.c \
	shutdown.c \
	watch.c

iceincludedir=$(includedir)/X11/ICE
iceinclude_HEADERS=\
	$(top_srcdir)/include/X11/ICE/ICE.h \
	$(top_srcdir)/include/X11/ICE/ICEconn.h \
	$(top_srcdir)/include/X11/ICE/ICElib.h \
	$(top_srcdir)/include/X11/ICE/ICEmsg.h \
	$(top_srcdir)/include/X11/ICE/ICEproto.h \
	$(top_srcdir)/include/X11/ICE/ICEutil.h

