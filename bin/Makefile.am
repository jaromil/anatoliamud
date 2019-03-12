## Automake file
##

bin_SCRIPTS = ctl_anatolia.sh
ctl_anatolia.sh: ctl_anatolia.sh.in
	sed -e "s|ENTER_ANA_HOME|$(prefix)|g" < ctl_anatolia.sh.in > ctl_anatolia.sh.1
	sed -e "s|ENTER_ANA_BIN|$(bindir)|g" < ctl_anatolia.sh.1 > ctl_anatolia.sh.2
	sed -e "s|ENTER_ANA_ETC|$(sysconfdir)|g" < ctl_anatolia.sh.2 > ctl_anatolia.sh.3
	sed -e "s|ENTER_ANA_VAR|$(localstatedir)|g" < ctl_anatolia.sh.3 > ctl_anatolia.sh
	rm -f ctl_anatolia.sh.1
	rm -f ctl_anatolia.sh.2
	rm -f ctl_anatolia.sh.3
	chmod +x ctl_anatolia.sh
#
# Clean up so that Makefile will re-create it each time
install-data-local:
	rm -f ctl_anatolia.sh
#
EXTRA_DIST = ctl_anatolia.sh.in
