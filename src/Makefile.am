SUBDIRS =					\
	suggest					\
	httpd

NONEXISTENT_CXX_SOURCE = nonexistent.cpp

bin_PROGRAMS = groonga groonga-benchmark
noinst_PROGRAMS = grnslap

EXTRA_DIST =					\
	CMakeLists.txt

AM_CFLAGS =					\
	$(NO_STRICT_ALIASING_CFLAGS)		\
	$(COVERAGE_CFLAGS)			\
	$(GRN_CFLAGS)				\
	$(MESSAGE_PACK_CFLAGS)			\
	$(MRUBY_CFLAGS)
DEFS += $(GRN_DEFS)

AM_LDFLAGS = -no-undefined

DEFAULT_INCLUDES =				\
	-I$(top_builddir)			\
	-I$(srcdir)				\
	-I$(top_srcdir)				\
	-I$(top_srcdir)/include			\
	$(GROONGA_INCLUDEDIR)

include groonga_sources.am
nodist_EXTRA_groonga_SOURCES = $(NONEXISTENT_CXX_SOURCE)
groonga_CFLAGS = $(AM_CFLAGS) $(LIBEDIT_CFLAGS)
groonga_LDADD =					\
	$(top_builddir)/lib/libgroonga.la	\
	$(LIBEDIT_LIBS)				\
	$(MESSAGE_PACK_LIBS)

include grnslap_sources.am
nodist_EXTRA_grnslap_SOURCES = $(NONEXISTENT_CXX_SOURCE)
grnslap_LDADD =					\
	$(top_builddir)/lib/libgroonga.la	\
	$(MESSAGE_PACK_LIBS)

include groonga_benchmark_sources.am
nodist_EXTRA_groonga_benchmark_SOURCES = $(NONEXISTENT_CXX_SOURCE)
groonga_benchmark_LDADD =			\
	$(top_builddir)/lib/libgroonga.la	\
	$(MESSAGE_PACK_LIBS)
