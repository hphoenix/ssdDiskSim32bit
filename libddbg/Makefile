
# libddbg (version 1.0)
# Authors: John Bucy, Greg Ganger
# Contributors: John Griffin, Jiri Schindler, Steve Schlosser
#
# Copyright (c) of Carnegie Mellon University, 2001-2008.
#
# This software is being provided by the copyright holders under the
# following license. By obtaining, using and/or copying this
# software, you agree that you have read, understood, and will comply
# with the following terms and conditions:
#
# Permission to reproduce, use, and prepare derivative works of this
# software is granted provided the copyright and "No Warranty"
# statements are included with all reproductions and derivative works
# and associated documentation. This software may also be
# redistributed without charge provided that the copyright and "No
# Warranty" statements are included in all redistributions.
#
# NO WARRANTY. THIS SOFTWARE IS FURNISHED ON AN "AS IS" BASIS.
# CARNEGIE MELLON UNIVERSITY MAKES NO WARRANTIES OF ANY KIND, EITHER
# EXPRESSED OR IMPLIED AS TO THE MATTER INCLUDING, BUT NOT LIMITED
# TO: WARRANTY OF FITNESS FOR PURPOSE OR MERCHANTABILITY, EXCLUSIVITY
# OF RESULTS OR RESULTS OBTAINED FROM USE OF THIS SOFTWARE. CARNEGIE
# MELLON UNIVERSITY DOES NOT MAKE ANY WARRANTY OF ANY KIND WITH
# RESPECT TO FREEDOM FROM PATENT, TRADEMARK, OR COPYRIGHT
# INFRINGEMENT.  COPYRIGHT HOLDERS WILL BEAR NO LIABILITY FOR ANY USE
# OF THIS SOFTWARE OR DOCUMENTATION.  



CC = cc -m32

# needs bitvector.h
# -D_LIBDDBG_FREEBSD for freebsd kernel
CFLAGS = -g -I../libparam

all: libddbg.a
	mkdir -p include/libddbg lib
	cp -p libddbg.h include/libddbg
	cp -p libddbg.a lib 

LT_SRC = ddbg_assert.c ddbg_trace.c
LT_OBJ = $(LT_SRC:.c=.o) 

clean: 
	rm -f $(LT_OBJ) libddbg.a
	rm -rf include lib

distclean: clean
	rm -f *~

libddbg.a: $(LT_OBJ)
	ar cru $@ $^


#test: test.c libddbg.a libddbg.h
#	$(CC) -g -o $@ test.c -L. -lddbg

