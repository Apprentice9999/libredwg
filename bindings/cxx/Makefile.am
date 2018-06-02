## Makefile.am
##
## Copyright (C) 2010, 2015, 2018 Free Software Foundation, Inc.
##
## This file is part of LibreDWG.
##
## LibreDWG is free software: you can redistribute it and/or modify it
## under the terms of the GNU General Public License as published by
## the Free Software Foundation, either version 3 of the License, or
## (at your option) any later version.
##
## LibreDWG is distributed in the hope that it will be useful,
## but WITHOUT ANY WARRANTY; without even the implied warranty
## of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
## See the GNU General Public License for more details.
##
## You should have received a copy of the GNU General Public License
## along with this program.  If not, see <http://www.gnu.org/licenses/>.

## bindings/python/Makefile.am: call SWIG and build python module
## written by Rodrigo Rodrigues da Silva

## TODO: place generated files out of source tree

ACLOCAL_AMFLAGS = -I $(top_srcdir)/m4

if HAVE_SWIG

BUILT_SOURCES = swig_wrap_cxx.hpp
SWIG_SOURCES = $(srcdir)/../dwg.i $(top_srcdir)/include/dwg.h

lib_LTLIBRARIES = libredwgcxx.la

libredwgcxx_la_SOURCES = $(BUILT_SOURCES)  $(SWIG_SOURCES)
## libredwg_la_CPPFLAGS = $(SWIG_CXX_CPPFLAGS) -I$(top_srcdir)/src
libredwgcxx_la_CPPFLAGS = -I$(top_srcdir)/include
libredwgcxx_la_LDFLAGS = -module
libredwgcxx_la_LIBADD = ../../src/libredwg.la

## not elegant, but works
swig_wrap_cxx.hpp : $(SWIG_SOURCES) Makefile.am
	$(SWIG) -c++ -importall -I$(top_srcdir)/include -o $@ $(srcdir)/../dwg.i

endif
