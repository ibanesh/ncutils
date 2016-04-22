# Environment
MKDIR=mkdir
CP=cp
GREP=grep
NM=nm
CCADMIN=CCadmin
RANLIB=ranlib
CC=gcc
CCC=g++
CXX=g++
FC=gfortran
AS=as

# build
build: .build-conf

# clean
clean: .clean-conf

# all
all: build

# Object Directory
OBJECTDIR=obj

# Lib Directory
LIBDIR=../../../csrc/lib

# Inclide Directory
INCLUDEDIR=../../../csrc/include

# Object Files
OBJECTFILES= \
	${OBJECTDIR}/coded_packet.o \
	${OBJECTDIR}/coding_vector_decoder.o \
	${OBJECTDIR}/finite_field.o \
	${OBJECTDIR}/packet_decoder.o \
	${OBJECTDIR}/uncoded_packet.o \
	${OBJECTDIR}/vector.o


# C Compiler Flags
CFLAGS=-fPIC

# CC Compiler Flags
CCFLAGS=
CXXFLAGS=

# Fortran Compiler Flags
FFLAGS=

# Assembler Flags
ASFLAGS=

# Link Libraries and Options
LDLIBSOPTIONS=-lm

# Build Targets
.build-conf: .move-includes
	"${MAKE}" libncutils.a

libncutils.a: ${OBJECTFILES}
	${RM} ${LIBDIR}/libncutils.a
	${AR} -rv ${LIBDIR}/libncutils.a ${OBJECTFILES} 
	$(RANLIB) ${LIBDIR}/libncutils.a

${OBJECTDIR}/coded_packet.o: coded_packet.c 
	${MKDIR} -p ${OBJECTDIR}
	${RM} "$@.d"
	$(COMPILE.c) -g -Wall -MMD -MP -MF "$@.d" -o ${OBJECTDIR}/coded_packet.o coded_packet.c

${OBJECTDIR}/coding_vector_decoder.o: coding_vector_decoder.c 
	${MKDIR} -p ${OBJECTDIR}
	${RM} "$@.d"
	$(COMPILE.c) -g -Wall -MMD -MP -MF "$@.d" -o ${OBJECTDIR}/coding_vector_decoder.o coding_vector_decoder.c

${OBJECTDIR}/finite_field.o: finite_field.c 
	${MKDIR} -p ${OBJECTDIR}
	${RM} "$@.d"
	$(COMPILE.c) -g -Wall -MMD -MP -MF "$@.d" -o ${OBJECTDIR}/finite_field.o finite_field.c

${OBJECTDIR}/packet_decoder.o: packet_decoder.c 
	${MKDIR} -p ${OBJECTDIR}
	${RM} "$@.d"
	$(COMPILE.c) -g -Wall -MMD -MP -MF "$@.d" -o ${OBJECTDIR}/packet_decoder.o packet_decoder.c

${OBJECTDIR}/uncoded_packet.o: uncoded_packet.c 
	${MKDIR} -p ${OBJECTDIR}
	${RM} "$@.d"
	$(COMPILE.c) -g -Wall -MMD -MP -MF "$@.d" -o ${OBJECTDIR}/uncoded_packet.o uncoded_packet.c

${OBJECTDIR}/vector.o: vector.c 
	${MKDIR} -p ${OBJECTDIR}
	${RM} "$@.d"
	$(COMPILE.c) -g -Wall -MMD -MP -MF "$@.d" -o ${OBJECTDIR}/vector.o vector.c

#Move Includes
.move-includes:
	${MKDIR} -p ${INCLUDEDIR}/ncutils
	${CP} ncutils.h ${INCLUDEDIR}/ncutils/ncutils.h
	${CP} ncutils_priv.h ${INCLUDEDIR}/ncutils/ncutils_priv.h

# Clean Targets
.clean-conf: 
	${RM} -r ${OBJECTDIR}
	${RM} ${LIBDIR}/libncutils.a
	
