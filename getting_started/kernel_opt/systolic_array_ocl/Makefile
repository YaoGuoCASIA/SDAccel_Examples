COMMON_REPO := ../../../
#Common Includes
include ${COMMON_REPO}/utility/boards.mk
include ${COMMON_REPO}/libs/xcl2/xcl2.mk
include ${COMMON_REPO}/libs/opencl/opencl.mk

# Host Application
host_SRCS=./src/host.cpp $(xcl2_SRCS)
host_HDRS=$(xcl2_HDRS)
host_CXXFLAGS=-I./src/ $(xcl2_CXXFLAGS) $(opencl_CXXFLAGS)
host_LDFLAGS=$(opencl_LDFLAGS)
host_CXXFLAGS+=-Wall
# Kernel
mmult_SRCS=./src/mmult.cl
mmult_CLFLAGS=-k mmult

XOS=mmult

mmult_XOS=mmult
mmult_NDEVICES=xilinx:vcu1525:dynamic xilinx_vcu1525_dynamic_5_0

XCLBINS=mmult
EXES=host

# check
check_EXE=host
check_XCLBINS=mmult
check_NDEVICES=$(mmult_NDEVICES)

CHECKS=check

include ${COMMON_REPO}/utility/rules.mk
