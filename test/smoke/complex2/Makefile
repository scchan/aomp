include ../Makefile.defs
TESTNAME     = complex
TESTSRC_MAIN = complex.cpp
TESTSRC_AUX  =
TESTSRC_ALL  = $(TESTSRC_MAIN) $(TESTSRC_AUX)

CLANG        = clang++
OMP_BIN      = $(AOMP)/bin/$(CLANG)
CC           = $(OMP_BIN) $(VERBOSE)

# removing -Xopenmp-target to illustrate bug in driver (crash)
TARGET  =  -fopenmp-targets=$(AOMP_GPUTARGET) -march=$(AOMP_GPU)

include ../Makefile.rules
