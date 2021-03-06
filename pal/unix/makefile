# /*++
# 
#  Copyright (c) 2006 Microsoft Corporation.  All rights reserved.
# 
#  The use and distribution terms for this software are contained in the file
#  named license.txt, which can be found in the root of this distribution.
#  By using this software in any fashion, you are agreeing to be bound by the
#  terms of this license.
# 
#  You must not remove this notice, or any other, from this software.
# 
#
# Module Name : makefile
#
# This file is NOT generated
#
# --*/

SHELL = /bin/bash

.PHONY: all configure preconfigure clean clean_configure depend check_env

all: check_env
	cd obj${BUILD_ALT_DIR}/${_BUILDARCH} && \
	${MAKE} all

configure: check_env preconfigure
	if test X"${USE_VAC_CC}" = "X1"; \
	then \
		EXTRA_CONFIGURE_FLAGS="--with-vac"; \
	else \
		EXTRA_CONFIGURE_FLAGS= ;\
	fi; \
	if test "${NTDEBUG}" = "ntsdnodbg"; \
	then \
		EXTRA_CONFIGURE_FLAGS=$${EXTRA_CONFIGURE_FLAGS}" --disable-debug"; \
	fi; \
	cd obj${BUILD_ALT_DIR}/${_BUILDARCH} && \
	if [ ! -f ${ROTOR_DIR}/pal/${PAL_UNIX_DIR}/obj${BUILD_ALT_DIR}/${_BUILDARCH}/config.status ]; \
	then \
		./configure --srcdir=${ROTOR_DIR}/pal/${PAL_UNIX_DIR} $${EXTRA_CONFIGURE_FLAGS} > build${BUILD_ALT_DIR}_${_BUILDARCH}.log 2>&1; \
	fi


preconfigure:
	mkdir -p ./obj${BUILD_ALT_DIR}/${_BUILDARCH}
	if [ -f ./obj${BUILD_ALT_DIR}/${_BUILDARCH}/configure ]; then \
		rm -f ./obj${BUILD_ALT_DIR}/${_BUILDARCH}/configure;\
	fi
	cp -f configure ./obj${BUILD_ALT_DIR}/${_BUILDARCH}/configure


clean: check_env
	cd obj${BUILD_ALT_DIR}/${_BUILDARCH} && \
	${MAKE} clean

clean_configure:
	rm -f ./obj${BUILD_ALT_DIR}/${_BUILDARCH}/config.status

depend: check_env
	cd obj${BUILD_ALT_DIR}/${_BUILDARCH} && \
	${MAKE} depend

check_env:
	@if test X"${_NTTREE}" = "X"; \
	then \
		echo "ERROR: Set environment before running this."; \
		exit 1; \
	fi
	@if test X"${PAL_UNIX_DIR}" != "Xunix"; \
	then \
		echo "ERROR: PAL_UNIX_DIR does not point to this directory."; \
		exit 1; \
	fi


