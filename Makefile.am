AUTOMAKE_OPTIONS = subdir-objects
ACLOCAL_AMFLAGS = ${ACLOCAL_FLAGS} -I m4
COMMON_FLAGS = -g -O3 -flto -fuse-linker-plugin -Isupport
AM_CFLAGS = -std=gnu11
AM_CXXFLAGS = -std=gnu++11
AM_CPPFLAGS = $(COMMON_FLAGS)
AM_LDFLAGS = $(COMMON_FLAGS)

bin_PROGRAMS = map

map_SOURCES = \
src/map.c \
src/map_std_unordered.cpp \
src/map_google_densehash.cpp \
src/map_ulib_align_hash_map.cpp \
src/map_tommyds_hashdyn.c \
src/map_khash.c \
src/map_libdynamic.c \
support/tommyds/tommyhash.c \
support/tommyds/tommyhashdyn.c \
support/tommyds/tommylist.c \
support/dynamic/buffer.c \
support/dynamic/vector.c \
support/dynamic/map.c \
src/map.h \
src/map_std_unordered.h \
src/map_google_densehash.h \
src/map_ulib_align_hash_map.h \
src/map_tommyds_hashdyn.h \
src/map_khash.h \
src/map_libdynamic.h \
src/map.R

benchmark: map.pdf

map.pdf: map.dat src/map.R
	./src/map.R

map.dat: map
	./$^ > $@

CLEANFILES = *.dat *.pdf
MAINTAINERCLEANFILES = aclocal.m4 config.h.in configure Makefile.in
maintainer-clean-local:; rm -rf autotools m4
