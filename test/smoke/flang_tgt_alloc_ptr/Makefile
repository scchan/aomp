include ../Makefile.defs

TESTNAME     = flang_tgt_alloc_ptr
TESTSRC_MAIN = flang_tgt_alloc_ptr.f90
TESTSRC_AUX  =
TESTSRC_ALL  = $(TESTSRC_MAIN) $(TESTSRC_AUX)

TARGET       = -fopenmp -O3 -w -i8 -fopenmp-targets=amdgcn-amd-amdhsa -Xopenmp-target=amdgcn-amd-amdhsa -march=$(AOMP_GPU)

FLANG        = flang
OMP_BIN      = $(AOMP)/bin/$(FLANG)
CC           = $(OMP_BIN) $(VERBOSE)
#-ccc-print-phases
#"-\#\#\#"

include ../Makefile.rules
