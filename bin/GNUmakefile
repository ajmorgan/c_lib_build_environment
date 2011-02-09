#  GNUmakefile

OBJDIR = ../obj/
vpath %.o ${OBJDIR}

.phony: default clean

default: 
		@echo -e "\n\
this makefile is to be called recursively --\n\
you must call make from the parent directory\n\
"

${BINARY_NAME}: ${OBJECTS}
		-echo '${BINARY_NAME}\n${SONAME}' > .gitignore
		${CC} $^ ${CC_FLAGS} ${LIB_FLAGS} ${SONAMEFLAGS} -o $@
		-ln -s ${BINARY_NAME} ${SONAME}

clean:
		-rm -f ${BINARY_NAME} ${SONAME}
