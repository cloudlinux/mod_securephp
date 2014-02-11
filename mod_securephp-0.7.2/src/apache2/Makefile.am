if COND_APUSERGROUP
  DEFINE_USERGROUP = -DSUPHP_USE_USERGROUP
endif

AM_CFLAGS=-I@APXS_INCLUDEDIR@ -I@APR_INCLUDEDIR@ @APXS_EXTRA_CFLAGS@

AM_CPPFLAGS=@APR_CPPFLAGS@

if COND_BACKWARDCOMPATIBILITY

noinst_LTLIBRARIES = mod_suphp.la
mod_suphp_la_SOURCES = mod_suphp.c

mod_suphp_la_LDFLAGS = -module -rpath '@APXS_LIBEXECDIR@'
AM_CFLAGS+=-DSUPHP_PATH_TO_SUPHP=\"${sbindir}/suphp\" $(DEFINE_USERGROUP)

install-data-local:
	${INSTALL_SCRIPT} -d ${DESTDIR}'@APXS_LIBEXECDIR@'
	${INSTALL_SCRIPT} -m 0755 .libs/mod_suphp.so ${DESTDIR}'@APXS_LIBEXECDIR@'/mod_suphp.so
else

noinst_LTLIBRARIES = mod_sucurephp.la
mod_sucurephp_la_SOURCES = mod_suphp.c

mod_sucurephp_la_LDFLAGS = -module -rpath '@APXS_LIBEXECDIR@'
AM_CFLAGS+=-DSUPHP_PATH_TO_SUPHP=\"${sbindir}/securephp\" $(DEFINE_USERGROUP)

install-data-local:
	${INSTALL_SCRIPT} -d ${DESTDIR}'@APXS_LIBEXECDIR@'
	${INSTALL_SCRIPT} -m 0755 .libs/mod_sucurephp.so ${DESTDIR}'@APXS_LIBEXECDIR@'/mod_securephp.so
endif
