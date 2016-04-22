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

# Macros
CND_PLATFORM=GNU-Linux-x86
CND_DLIB_EXT=so
CND_CONF=Coverage
CND_DISTDIR=dist
CND_BUILDDIR=build

# Include project Makefile

# build
build: .build-conf

# clean
clean: .clean-conf

# all
all: build

# Object Directory
OBJECTDIR=obj

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
LDLIBSOPTIONS=

# Build Targets
.build-conf: ${BUILD_SUBPROJECTS}
	"${MAKE}" build/lib/libncutils.a

build/lib/libncutils.a: ${OBJECTFILES}
	${MKDIR} -p build/lib
	${RM} build/lib/libncutils.a
	${AR} -rv build/lib/libncutils.a ${OBJECTFILES} 
	$(RANLIB) build/lib/libncutils.a

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

# Clean Targets
.clean-conf: 
	${RM} -r ${OBJECTDIR}
	${RM} build/lib/libncutils.a
