#$Id: Makefile.template,v 26.133 2009/11/26 04:58:04 al Exp $ -*- Makefile -*-
# Copyright (C) 2001 Albert Davis
# Author: Albert Davis <aldavis@gnu.org>
#
# This file is part of "Gnucap", the Gnu Circuit Analysis Package
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 3, or (at your option)
# any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA
# 02110-1301, USA.
#------------------------------------------------------------------------
# In most cases you can just type "make" to build it.
# Generally, you will want "make your-system".
# Look in this file for the choices.
# If yours is not here, look for a similar one and copy.
# The special configurations listed here allow you to do multiple builds
# from the same source directory, and patch some problems.
#-----------------------------------------------------------------------------
# The default is to use the makefile built by "configure"
default: nothing
	-mkdir O
	cat Make1 Make2 ../Make3 Make.depend >O/Makefile
	(cd O; ${MAKE} -k)
#-----------------------------------------------------------------------------
# The most common configuration is g++
# This should work if it is properly installed
# and has the proper libraries and headers.
# It is optimized for speed.  Debugging is off.
g++: nothing
	-mkdir O
	cat Make1 Make2.g++ ../Make3 Make.depend >O/Makefile
	(cd O; ${MAKE} -k)
#-----------------------------------------------------------------------------
# This one makes a "debug" build ...
# Asserts and some tracing is turned on.
# It prints a trace when "untested" code is exercised.
# "Untested" means the regressions don't test it.
# It doesn't mean TOTALLY untested.
debug: nothing
	-mkdir O-DEBUG
	cat Make1 Make2.Debug ../Make3 Make.depend >O-DEBUG/Makefile
	(cd O-DEBUG; ${MAKE} -k)
#-----------------------------------------------------------------------------
#-----------------------------------------------------------------------------
# MS Windows using mingw32
mingw: nothing
	-mkdir MSW
	cat Make1 Make2 ../Make3 Make.depend >MSW/Makefile
	(cd MSW; ${MAKE} -k)
#-----------------------------------------------------------------------------
tags: nothing
	cat Make1 Make2 ../Make3 >Make.aux
	(${MAKE} tags -f Make.aux)
#-----------------------------------------------------------------------------
depend: nothing
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux depend
#-----------------------------------------------------------------------------
checkin: nothing
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux checkin
#-----------------------------------------------------------------------------
checkout: nothing
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux checkout
#-----------------------------------------------------------------------------
install: nothing
	${MAKE} default
	(cd O; ${MAKE} install)
#-----------------------------------------------------------------------------
uninstall: nothing
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux uninstall
#-----------------------------------------------------------------------------
#  Note that the /usr/local directory is overwritten by configure.
not_install: nothing
	if test -d /usr/local/bin; then \
		cp O/gnucap /usr/local/bin/gnucap; \
	else \
		mkdir -p /usr/local/bin && \
		cp O/gnucap /usr/local/bin/gnucap; \
	fi
#-----------------------------------------------------------------------------
not_uninstall: clean
	-rm /usr/local/bin/gnucap
#-----------------------------------------------------------------------------
unconfig: 
	rm -f Makefile
#-----------------------------------------------------------------------------
date: nothing
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux date
#-----------------------------------------------------------------------------
header-check:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux header-check
#-----------------------------------------------------------------------------
manifest:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux manifest
#-----------------------------------------------------------------------------
md5sums:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux md5sums
#-----------------------------------------------------------------------------
mostlyclean:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux mostlyclean
clean:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux clean
distclean:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux distclean
maintainer-clean:
	cat Make1 Make2 ../Make3 >Make.aux
	${MAKE} -f Make.aux maintainer-clean
#-----------------------------------------------------------------------------
nothing:
#-----------------------------------------------------------------------------
#-----------------------------------------------------------------------------
