if ENABLE_LUA

module_LTLIBRARIES					+= modules/monitor-source/libmonitor-source.la

modules_monitor_source_libmonitor_source_la_CFLAGS	 = \
	$(INCUBATOR_CFLAGS)				   \
	$(LUA_CFLAGS)				   \
	-I$(top_srcdir)/modules/monitor-source		   \
	-I$(top_builddir)/modules/monitor-source

modules_monitor_source_libmonitor_source_la_SOURCES	 = \
	modules/monitor-source/monitor-source-grammar.y	   \
	modules/monitor-source/monitor-source.c		   \
	modules/monitor-source/monitor-source.h		   \
	modules/monitor-source/monitor-source-parser.c	   \
	modules/monitor-source/monitor-source-parser.h	   \
	modules/monitor-source/monitor-source-plugin.c

modules_monitor_source_libmonitor_source_la_LIBADD	 = \
	$(INCUBATOR_LIBS)				   \
	$(LUA_LIBS)                \
  modules/lua/libluautil.la

modules_monitor_source_libmonitor_source_la_LDFLAGS	 = \
	-avoid-version -module -no-undefined

modules/monitor-source mod-monitor: modules/monitor-source/libmonitor-source.la
else
modules/monitor-source mod-monitor:
endif

BUILT_SOURCES						+= \
	modules/monitor-source/monitor-source-grammar.y	   \
	modules/monitor-source/monitor-source-grammar.c	   \
	modules/monitor-source/monitor-source-grammar.h

EXTRA_DIST						+= \
	modules/monitor-source/monitor-source-grammar.ym	   \
	modules/monitor-source/monitor-source-example.conf

.PHONY: modules/monitor-source mod-monitor
