CLEANFILES =

lib_LTLIBRARIES = libayatana-ido3-0.4.la

ido_built_public_sources =		\
	idotypebuiltins.h

stamp_files =				\
	idotypebuiltins.h		\
	idotypebuiltins.c

sources_h =				\
	ayatanamenuitemfactory.h	\
	idoalarmmenuitem.h		\
	idocalendarmenuitem.h		\
	idoentrymenuitem.h		\
	idomessagedialog.h		\
	idorange.h			\
	idoscalemenuitem.h		\
	idoswitchmenuitem.h		\
	idousermenuitem.h		\
	idoappointmentmenuitem.h	\
	idobasicmenuitem.h		\
	idoprogressmenuitem.h		\
	idotimestampmenuitem.h		\
	idolocationmenuitem.h		\
	idotimeline.h			\
	libayatana-ido.h		\
	idoactionhelper.h		\
	idomediaplayermenuitem.h	\
	idoplaybackmenuitem.h		\
	idoapplicationmenuitem.h 	\
	idodetaillabel.h		\
	idosourcemenuitem.h

EXTRA_DIST =				\
	ido.list			\
	idotypebuiltins.h.template	\
	idotypebuiltins.c.template


idotypebuiltins.h: stamp-idotypebuiltins.h

stamp-idotypebuiltins.h: $(sources_h)
	( cd $(srcdir) && $(GLIB_MKENUMS) --template idotypebuiltins.h.template \
		$(sources_h) ) >> xgen-gtbh \
	&& (cmp -s xgen-gtbh idotypebuiltins.h || cp xgen-gtbh idotypebuiltins.h ) \
	&& rm -f xgen-gtbh && echo timestamp > $(@F)

idotypebuiltins.c: stamp-idotypebuiltins.h
	( cd $(srcdir) && $(GLIB_MKENUMS) --template idotypebuiltins.c.template \
		$(sources_h) ) > xgen-gtbc \
	&& cp xgen-gtbc idotypebuiltins.c && rm -f xgen-gtbc

INCLUDES =				\
	-I$(srcdir)			\
	-I$(top_srcdir)			\
	-DG_LOG_DOMAIN=\"IDO\"		\
	-DPREFIX=\"$(prefix)"\"		\
	-DLIBDIR=\"$(libdir)"\"		\
	-DG_DISABLE_DEPRECATED		\
	-DGDK_PIXBUF_DISABLE_DEPRECATED	\
	-DGDK_DISABLE_DEPRECATED

AM_CPPFLAGS =				\
	$(GCC_FLAGS)			\
	$(GTK_CFLAGS)			\
	$(MAINTAINER_CFLAGS)    \
	-Wall -Wextra -Wno-unused-parameter -Wno-error=deprecated-declarations

AM_CFLAGS =                             \
	$(COVERAGE_CFLAGS)

libayatana_ido_0_4_la_SOURCES =		\
	ayatanamenuitemfactory.c	\
	libayatana-ido.c		\
	idotypebuiltins.c		\
	idocalendarmenuitem.c		\
	idoalarmmenuitem.c		\
	idoentrymenuitem.c		\
	idomessagedialog.c		\
	idorange.c			\
	idoscalemenuitem.c		\
	idoswitchmenuitem.c		\
	idotimeline.c			\
	idomenuitemfactory.c		\
	idoactionhelper.c		\
	idousermenuitem.c		\
	idomediaplayermenuitem.c	\
	idoplaybackmenuitem.c		\
	idoappointmentmenuitem.c	\
	idobasicmenuitem.c		\
	idoprogressmenuitem.c		\
	idotimestampmenuitem.c		\
	idolocationmenuitem.c		\
	idoapplicationmenuitem.c	\
	idodetaillabel.c		\
	idosourcemenuitem.c

libayatana_ido3_0_4_la_SOURCES = $(libayatana_ido_0_4_la_SOURCES)

libayatana_idoincludedir=$(includedir)/libayatana-ido3-0.4/libayatana-ido

libayatana_idoinclude_HEADERS =		\
	idocalendarmenuitem.h		\
	idoentrymenuitem.h		\
	idomessagedialog.h		\
	idorange.h			\
	idoscalemenuitem.h		\
	idoswitchmenuitem.h		\
	idotimeline.h			\
	libayatana-ido.h

libayatana_ido_0_4_la_LIBADD = $(GTK_LIBS) $(LIBM)
libayatana_ido_0_4_la_LDFLAGS =                 \
	$(GTK_LT_LDFLAGS)               \
	$(COVERAGE_LDFLAGS)	\
	-no-undefined \
	-export-symbols-regex "^[^_].*"
libayatana_ido3_0_4_la_LIBADD = $(libayatana_ido_0_4_la_LIBADD)
libayatana_ido3_0_4_la_LDFLAGS =                \
	$(libayatana_ido_0_4_la_LDFLAGS)

DISTCLEANFILES =			\
	Makefile.in			\
	stamp-idotypebuiltins.h		\
	idotypebuiltins.h		\
	idotypebuiltins.c

-include $(INTROSPECTION_MAKEFILE)
INTROSPECTION_GIRS =
INTROSPECTION_SCANNER_ARGS = \
        --symbol-prefix=ido \
        --warn-all \
        --identifier-prefix=Ido

if HAVE_INTROSPECTION

AyatanaIdo3-0.4.gir: libayatana-ido3-0.4.la
AyatanaIdo3_0_4_gir_INCLUDES = Gtk-3.0
AyatanaIdo3_0_4_gir_CFLAGS =
AyatanaIdo3_0_4_gir_LIBS = libayatana-ido3-0.4.la
AyatanaIdo3_0_4_gir_FILES = \
	idocalendarmenuitem.h		\
	idoentrymenuitem.h		\
	idomessagedialog.h		\
	idorange.h			\
	idoscalemenuitem.h		\
	idoswitchmenuitem.h		\
	idotimeline.h			\
	$(libayatana_ido_0_4_la_SOURCES)
AyatanaIdo3_0_4_gir_NAMESPACE = AyatanaIdo3
AyatanaIdo3_0_4_gir_VERSION = 0.4
AyatanaIdo3_0_4_gir_SCANNER_FLAGS = $(INTROSPECTION_SCANNER_ARGS)

INTROSPECTION_GIRS += AyatanaIdo3-0.4.gir

girdir = $(datadir)/gir-1.0
gir_DATA = $(INTROSPECTION_GIRS)

typelibdir = $(libdir)/girepository-1.0
typelib_DATA = $(INTROSPECTION_GIRS:.gir=.typelib)

CLEANFILES += $(gir_DATA) $(typelib_DATA)

endif

if HAVE_INTROSPECTION

vapidir = $(datadir)/vala/vapi
vapi_DATA = AyatanaIdo3-0.4.vapi

AyatanaIdo3-0.4.vapi: AyatanaIdo3-0.4.gir
	$(VALA_API_GEN) --library=AyatanaIdo3-0.4 \
			--pkg gtk+-3.0 \
			$<

CLEANFILES += $(vapi_DATA)

endif
