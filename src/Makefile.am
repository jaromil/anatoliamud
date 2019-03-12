## Automake file
##

bin_PROGRAMS = anatolia
anatolia_SOURCES = act_comm.c act_hera.c act_info.c act_move.c act_obj.c act_wiz.c anatolia.h ban.c comm.c const.c db2.c db.c db.h effects.c fight.c flags.c handler.c healer.c interp.c interp.h lookup.c lookup.h magic2.c magic.c magic.h martial_art.c mob_prog.c note.c obj_prog.c quest.c recycle.c recycle.h save.c skills.c special.c tables.c tables.h telnet.h update.c

if ANA_FAST_SERVER
anatolia_CFLAGS = -Wall -DANATOLIA_FAST_SERVER
else
anatolia_CFLAGS = -Wall
endif

if ANA_NOCRYPT
AM_CFLAGS = -DNOCRYPT
endif

if ANA_SRC_INSTALL
anasrcdir = $(config_src_dir)
anasrc_DATA = $(anatolia_SOURCES) config.h

EXTRA_DIST = $(anasrc_DATA) Makefile.original

install-data-local:
	grep "^CC " Makefile | sed -e "s|CC|CC     |" > $(anasrcdir)/Makefile
	grep "^CFLAGS" Makefile | sed -e "s|CFLAGS|PROF   |" >> $(anasrcdir)/Makefile
	grep "^AM_CFLAGS" Makefile | sed -e "s|AM_CFLAGS|NOCRYPT|" >> $(anasrcdir)/Makefile
	grep "^anatolia_CFLAGS" Makefile | sed -e "s|anatolia_CFLAGS|AMFLAGS|" >> $(anasrcdir)/Makefile
	grep "^LIBS " Makefile | sed -e "s|LIBS|LIBS   |" >> $(anasrcdir)/Makefile
	sed -e "s|ENTER_ANA_BIN|$(bindir)/anatolia|g" < Makefile.original | more -9999 +7 >> $(anasrcdir)/Makefile

uninstall-local:
	rm -f $(anasrcdir)/Makefile
endif
