# Generated automatically from Makefile.in by configure.
# dynamic/Makefile - dynamic library Makefile
# 
#  This file is part of adns, which is
#    Copyright (C) 1997-2000,2003,2006  Ian Jackson
#    Copyright (C) 1999-2000,2003,2006  Tony Finch
#    Copyright (C) 1991 Massachusetts Institute of Technology
#  (See the file INSTALL for full details.)
#  
#  This program is free software; you can redistribute it and/or modify
#  it under the terms of the GNU General Public License as published by
#  the Free Software Foundation; either version 2, or (at your option)
#  any later version.
#  
#  This program is distributed in the hope that it will be useful,
#  but WITHOUT ANY WARRANTY; without even the implied warranty of
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#  GNU General Public License for more details.
#  
#  You should have received a copy of the GNU General Public License
#  along with this program; if not, write to the Free Software Foundation,
#  Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307, USA. 

srcdir=		.

TARGETS=	$(SHLIBFILE) $(SHLIBSONAME) $(SHLIBFORLINK)
include		$(srcdir)/../settings.make
include		$(srcdir)/../src/adns.make

ALLOBJS=	$(addsuffix _p.o, $(basename $(LIBOBJS)))

install:
		mkdir -p $(libdir)
		$(INSTALL_PROGRAM) $(SHLIBFILE) $(libdir)/$(SHLIBFILE)
		ln -sf $(SHLIBFILE) $(libdir)/$(SHLIBSONAME)
		ln -sf $(SHLIBSONAME) $(libdir)/$(SHLIBFORLINK)

uninstall:
		rm -f $(libdir)/$(SHLIBFILE) $(libdir)/$(SHLIBSONAME)

$(SHLIBFORLINK):
		ln -s $(SHLIBSONAME) $(SHLIBFORLINK)

$(SHLIBSONAME):
		ln -s $(SHLIBFILE) $(SHLIBSONAME)

$(SHLIBFILE):	$(ALLOBJS)
		rm -f $@
		$(MKSHLIB_1) $@ $(MKSHLIB_2) $(ALLOBJS) $(LDLIBS) $(MKSHLIB_3)

%_p.o:		$(srcdir)/../src/%.c $(srcdir)/../src/adns.h \
			$(srcdir)/../src/internal.h $(srcdir)/../src/config.h
		$(SHLIBCC) -I$(srcdir)/../src -c -o $@ $<

$(LIBOBJS):	
