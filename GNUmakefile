#  GNUmakefile
#  Note:  This makefile, and the two makefiles it calls recursively
#    are meant to be as generic as possible, with any changes being
#    affected from this top level makefile

SONAME = libcii.so
SONAMEFLAGS = -W1,-soname,libcii.so.1
BINARY_NAME = libcii.so.1.0.1
CC = gcc
CC_FLAGS = -shared -fpic -lc
LIB_FLAGS = 

CC_DEP_FLAGS = -MMD -g -c -Wall -fpic
SOURCES = ${notdir ${wildcard src/*.c}}
OBJECTS = ${SOURCES:.c=.o}

.EXPORT_ALL_VARIABLES: 
.phony: all clean

all:
		-ctags -R *
		-cscope -bR $(find . -name *.[ch])
		-tools/beautify.sh
		${MAKE} -C obj objects
		${MAKE} -C bin ${BINARY_NAME}

clean:
		${MAKE} -C obj $@
		${MAKE} -C bin $@
