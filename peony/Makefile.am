AM_CPPFLAGS =						\
	-DFR_DATADIR=\"$(datadir)\"			\
	-DMATELOCALEDIR=\""$(datadir)/locale"\" 	\
	-I$(top_srcdir)					\
	-I$(top_builddir)				\
	$(PEONY_CFLAGS)

peony_extensiondir=$(PEONY_EXTENSION_DIR)

peony_extension_LTLIBRARIES=libpeony-peony-archives.la

libpeony_peony-archives_la_SOURCES =     \
	peony-peony-archives.c           \
	peony-peony-archives.h           \
	peony-archives-module.c

libpeony_peony-archives_la_LDFLAGS = -module -avoid-version -no-undefined
libpeony_peony-archives_la_LIBADD  = $(PEONY_LIBS)

extensiondir = $(datadir)/peony/extensions
extension_in_files = libpeony-peony-archives.peony-extension.in
extension_DATA = $(extension_in_files:.peony-extension.in=.peony-extension)
%.peony-extension: %.peony-extension.in $(INTLTOOL_MERGE) $(wildcard $(top_srcdir)/po/*.po) ; $(AM_V_GEN) LC_ALL=C $(INTLTOOL_MERGE) -d -u -c $(top_builddir)/po/.intltool-merge-cache $(top_srcdir)/po $< $@

CLEANFILES = libpeony-peony-archives.peony-extension

EXTRA_DIST = $(extension_in_files)
-include $(top_srcdir)/git.mk
