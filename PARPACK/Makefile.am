SUBDIRS = UTIL SRC . EXAMPLES/MPI EXAMPLES/BLACS

lib_LTLIBRARIES = libparpack.la

libparpack_la_SOURCES =

# Force libparpack to be linked with the MPI Fortran compiler.
# The file dummy.f does not need to exist in the source tree.
F77 = $(MPIF77)
nodist_EXTRA_libparpack_la_SOURCES = dummy.f

libparpack_la_LDFLAGS = -no-undefined -version-info 2:0

libparpack_la_LIBADD = \
	$(top_builddir)/SRC/libarpacksrc.la \
	$(top_builddir)/UTIL/libarpackutil.la \
	$(top_builddir)/PARPACK/SRC/MPI/libparpacksrcmpi.la \
	$(top_builddir)/PARPACK/UTIL/MPI/libparpackutilmpi.la \
	$(BLAS_LIBS) $(LAPACK_LIBS) $(MPILIBS)
