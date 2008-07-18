# $Id$

INCLUDES = \
	-I${top_srcdir} \
	-DDATADIR=\"$(datadir)\" \
	-DSRCDIR=\"$(top_srcdir)\" \
	-DLOCALEDIR=\"$(localedir)\" \
	-DG_LOG_DOMAIN=\"xfce4-display-settings\" \
	$(PLATFORM_CPPFLAGS)

bin_PROGRAMS = \
	xfce4-display-settings

xfce4_display_settings_SOURCES = \
	main.c \
	display-dialog_glade.h

xfce4_display_settings_CFLAGS = \
	$(GTK_CFLAGS) \
	$(GLIB_CFLAGS) \
	$(GLADE_CFLAGS) \
	$(DBUS_GLIB_CFLAGS) \
	$(LIBXFCEGUI4_CFLAGS) \
	$(XFCONF_CFLAGS) \
	$(XRANDR_CFLAGS) \
	$(XXF86VM_CFLAGS)

xfce4_displaye_settings_LDFLAGS = \
	-no-undefined \
	$(PLATFORM_LDFLAGS)

xfce4_display_settings_LDADD = \
	$(GTK_LIBS) \
	$(GLIB_LIBS) \
	$(GLADE_LIBS) \
	$(DBUS_GLIB_LIBS) \
	$(LIBXFCEGUI4_LIBS) \
	$(XFCONF_LIBS) \
	$(XRANDR_LIBS) \
	$(XXF86VM_LIBS)

if MAINTAINER_MODE

BUILT_SOURCES = \
	display-dialog_glade.h

display-dialog_glade.h: display-dialog.glade
	exo-csource --static --strip-comments --strip-content --name=display_dialog_glade $< >$@

endif

desktopdir = $(datadir)/applications
desktop_in_files = xfce4-display-settings.desktop.in
desktop_DATA = $(desktop_in_files:.desktop.in=.desktop)

settingsdir = $(datadir)/xfce4/settings-dialogs
settings_DATA = $(desktop_DATA)

@INTLTOOL_DESKTOP_RULE@

EXTRA_DIST = \
	$(desktop_in_files) \
	display-dialog.glade

DISTCLEANFILES = \
	$(desktop_DATA)

# vi:set ts=8 sw=8 noet ai nocindent syntax=automake: