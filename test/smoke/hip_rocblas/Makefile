include ../Makefile.defs
$(warning "This test requires rocblas to be installed in /opt/rocm/rocblas. Rocblas works on AMD only.")

TESTNAME     = hip_rocblas
TESTSRC_MAIN = hip_rocblas.cpp
TESTSRC_AUX  =
TESTSRC_ALL  = $(TESTSRC_MAIN) $(TESTSRC_AUX)
OMP_FLAGS    =  --offload-arch=${AOMP_GPU}
CFLAGS       = -x hip -I /opt/rocm/rocblas/include/ --offload-arch=${AOMP_GPU} -std=c++11
OMPHIP ?= $(AOMP)
ifeq ($(shell expr $(VERS) \>= 12.0), 1)
  RPTH = -Wl,-rpath,$(AOMPHIP)/lib
endif
LINK_FLAGS =  -L /opt/rocm/rocblas/lib -lrocblas -Wl,-rpath,/opt/rocm/rocblas/lib -lamdhip64  $(RPTH)

ifeq ($(EPSDB),1)
OMP_BIN      = /opt/rocm/bin/hipcc
else
CLANG        = clang++
OMP_BIN      = $(AOMP)/bin/$(CLANG)
endif
CC           = $(OMP_BIN) $(VERBOSE)

#-ccc-print-phases
#"-\#\#\#"
#$(shell $(WARNING))
include ../Makefile.rules
