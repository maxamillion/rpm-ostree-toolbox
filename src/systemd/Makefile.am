EXTRA_DIST = \
	$(srcdir)/src/systemd/rpm-ostree-toolbox-build-monitor@.service \
	$(srcdir)/src/systemd/rpm-ostree-toolbox-git-monitor.service \
	$(srcdir)/src/systemd/rpm-ostree-toolbox-kinit@.service \
	$(srcdir)/src/systemd/rpm-ostree-toolbox-kinit@.timer \
	$(srcdir)/src/systemd/rpm-ostree-toolbox-watch@.service

SYSTEMD_UNIT_DIR = $(prefix)/lib/systemd/system

install-systemd: $(EXTRA_DIST)
	$(MKDIR_P)                    $(DESTDIR)$(SYSTEMD_UNIT_DIR)
	$(INSTALL_DATA) $(EXTRA_DIST) $(DESTDIR)$(SYSTEMD_UNIT_DIR)/

uninstall-systemd:
	$(RM) -f $(DESTDIR)$(SYSTEMD_UNIT_DIR)/rpm-ostree-toolbox-build-monitor@.service
	$(RM) -f $(DESTDIR)$(SYSTEMD_UNIT_DIR)/rpm-ostree-toolbox-git-monitor.service
	$(RM) -f $(DESTDIR)$(SYSTEMD_UNIT_DIR)/rpm-ostree-toolbox-kinit@.service
	$(RM) -f $(DESTDIR)$(SYSTEMD_UNIT_DIR)/rpm-ostree-toolbox-kinit@.timer
	$(RM) -f $(DESTDIR)$(SYSTEMD_UNIT_DIR)/rpm-ostree-toolbox-watch@.service
	$(RMDIR) $(DESTDIR)$(SYSTEMD_UNIT_DIR) || :

install-data-local: install-systemd
uninstall-local:  uninstall-systemd
