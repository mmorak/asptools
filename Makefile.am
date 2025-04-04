############################
# FLAGS:                   #
############################

# tell automake to pass certain flags to autoconf on re-run
ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}

# tell automake to pass certain flags to 'ctags'
AM_CTAGSFLAGS = --extra=+f

#FIXME: don't assume GCC, do feature detection in configure.ac
# tell automake to pass certain CFLAGS to the compiler
AM_CFLAGS = \
	-pedantic-errors \
	-Wpedantic \
	-Wall \
	-Wextra \
	-Wdouble-promotion \
	-Wswitch-default

# initialize variables
EXTRA_DIST =
CLEANFILES =
BUILT_SOURCES =

############################
# LIBRARIES TO BUILD:	   #
############################

############################
# PROGRAMS TO BUILD:	   #
############################

# tell automake which programs to build
bin_PROGRAMS = lpcat lpshift

# add conditional programs
if WITH_PLANAR
bin_PROGRAMS += planar
endif

#-----------------------#
# program build options #
#-----------------------#

# list all source code files for the programs
COMMON = src/relocate.h src/relocate.c src/scc.h src/scc.c 
lpcat_SOURCES = $(COMMON) src/lpcat.c
lpshift_SOURCES = $(COMMON) src/lpshift.c

if WITH_PLANAR
planar_SOURCES = src/planar.c
endif

############################
# DISTRIBUTION OPTIONS:	   #
############################

# tell automake about scripts that should be distributed in the tarball, but
# not installed on "make install"
dist_noinst_SCRIPTS = autogen.sh

# tell automake to clean the generated files on "make clean"
CLEANFILES += $(BUILT_SOURCES)

############################
# UNIT TESTS:              #
############################

# tell automake to recursively go into the test directory
#SUBDIRS = tests
