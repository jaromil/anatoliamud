etcdir = $(sysconfdir)
etc_DATA = anatolia.conf areas.list

EXTRA_DIST = $(etc_DATA) anatolia.conf.in

install-data-local:
	sed -e "s|ENTER_ANA_HOME|$(prefix)|g" < anatolia.conf.in > anatolia.conf.1
	sed -e "s|ENTER_ANA_BIN|$(bindir)|g" < anatolia.conf.1 > anatolia.conf.2
	sed -e "s|ENTER_ANA_ETC|$(sysconfdir)|g" < anatolia.conf.2 > anatolia.conf.3
	sed -e "s|ENTER_ANA_LIB|$(libdir)|g" < anatolia.conf.3 > anatolia.conf.4
	sed -e "s|ENTER_ANA_VAR|$(localstatedir)|g" < anatolia.conf.4 > anatolia.conf
	rm -f anatolia.conf.1
	rm -f anatolia.conf.2
	rm -f anatolia.conf.3
	rm -f anatolia.conf.4

