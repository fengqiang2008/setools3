bin_PROGRAMS = seaudit seaudit_report

AM_CFLAGS = -I$(top_srcdir)/libseaudit -I$(top_srcdir)/libqpol/include -I$(top_srcdir)/libapol @GTK_CFLAGS@ @GLADE_CFLAGS@ @XML_CFLAGS@ -DAPOL_INSTALL_DIR='"${apol_install_dir}"'
AM_LDFLAGS = @GTK_LIBS@ @GLADE_LIBS@ @XML_LIBS@
LDADD = $(top_srcdir)/libseaudit/libseaudit.a $(top_srcdir)/libapol/libapol.a $(top_srcdir)/libqpol/src/libqpol.so @QPOL_LIB_FLAG@

seaudit_SOURCES = \
	auditlogmodel.c auditlogmodel.h \
	query_window.c query_window.h \
	filter_window.c filter_window.h \
	multifilter_window.c multifilter_window.h \
	utilgui.c utilgui.h \
	preferences.c preferences.h \
	seaudit_window.c seaudit_window.h \
	seaudit_callback.c seaudit_callback.h \
	filtered_view.c filtered_view.h \
	report_window.c report_window.h \
	seaudit.c report.c report.h
seaudit_DEPENDENCIES = $(top_srcdir)/libseaudit/libseaudit.a $(top_srcdir)/libapol/libapol.a \
                       $(top_srcdir)/libqpol/src/libqpol.so

seaudit_report_SOURCES = seaudit-report.c report.c report.h
seaudit_report_DEPENDENCIES = $(top_srcdir)/libseaudit/libseaudit.a $(top_srcdir)/libapol/libapol.a \
                              $(top_srcdir)/libqpol/src/libqpol.so

$(top_srcdir)/libapol/libapol.a:
	$(MAKE) -C $(top_srcdir)/libapol $(notdir $@)

$(top_srcdir)/libqpol/src/libqpol.so:
	$(MAKE) -C $(top_srcdir)/libqpol/src $(notdir $@)

$(top_srcdir)/libseaudit/libseaudit.a:
	$(MAKE) -C $(top_srcdir)/libseaudit $(notdir $@)

# FIX ME:
# install glade files, saudit_help.txt, dot_seaudit, conf file, report
# stylesheet, man pages, logwatch install, DEFAULT_LOG, INSTALL_LIBDIR
