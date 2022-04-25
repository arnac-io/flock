# you probably want one of the following tasks:
# - all
# - install
# - pkg
# - doc
# - test

# utilities
OPEN=open
GIT=git
CPIO=cpio
LINT=splint
LINT_FLAGS=+posixlib

AM_CPPFLAGS = \
	-include config.h \
	-I$(top_srcdir)/include \
	-DLOCALEDIR=\"$(localedir)\" \
	-D_PATH_LOCALSTATEDIR=\"${localstatedir}\"

AM_CFLAGS = \
	-fsigned-char \
	-fno-common \
	-Wall \
	-Wextra \
	-Werror \
	-Wmissing-declarations \
	-Wmissing-prototypes \
	-Wredundant-decls \
	-Wtype-limits \
	-Wunused-parameter \
	-Wnested-externs \
	-Wpointer-arith \
	-Wstrict-prototypes \
	-Wformat=2

AM_LDFLAGS =

pkgconfigdir = $(usrlib_execdir)/pkgconfig

RCS_FIND_IGNORE = \( -o -name .git \) -prune -o

ACLOCAL_AMFLAGS = -I m4

bin_PROGRAMS = flock
flock_SOURCES = src/flock.c
flock_LDADD = $(LDADD)

EXTRA_DIST=\
	LICENSE.md \
	README.md \
	autogen.sh 

TEST_LOG_DRIVER = env AM_TAP_AWK='$(AWK)' $(SHELL) \
                  $(top_srcdir)/config/tap-driver.sh
TESTS = t/default.bats t/smartos.bats
EXTRA_DIST += $(TESTS)
