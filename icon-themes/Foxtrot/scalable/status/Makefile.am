size = scalable
context = status

iconsdir = $(datadir)/icons/Foxtrot/$(size)/$(context)

icons_DATA =			\
	folder-accept.svg	\
	folder-drag-accept.svg	\
	folder-open.svg		\
	gnome-fs-accept.svg	\
	user-trash-full.svg	\
	x-directory-drag-accept.svg	\
	x-directory-normal-accept.svg	\
	x-directory-normal-open.svg

EXTRA_DIST =		\
	$(icons_DATA)

MAINTAINERCLEANFILES =	\
	Makefile.in

install-data-local: install-iconsDATA
	(cd $(DESTDIR)$(datadir)/icons/Foxtrot/$(size) && $(ICONMAP) -c $(context))

check:
	if test -r CVS/Entries; then \
		for icon in *.svg; do \
			if grep $$icon CVS/Entries > /dev/null; then \
				if ! grep $$icon Makefile > /dev/null; then \
					echo "Missing $$icon in Makefile.am"; \
					exit 1; \
				fi; \
			fi; \
		done; \
	else \
		for icon in *.svg; do \
			if ! grep $$icon Makefile > /dev/null; then \
				echo "Missing $$icon in Makefile.am"; \
				exit 1; \
			fi; \
		done; \
	fi
