#
#  Copyright 2001-2009 Texas Instruments - http://www.ti.com/
#
#  Licensed under the Apache License, Version 2.0 (the "License");
#  you may not use this file except in compliance with the License.
#  You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
#  Unless required by applicable law or agreed to in writing, software
#  distributed under the License is distributed on an "AS IS" BASIS,
#  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#  See the License for the specific language governing permissions and
#  limitations under the License.

#
#  syslink/usr/src/Makefile
#
#  SysLink Api library Makefile.

PROJROOT = ../

include $(PROJROOT)/make/start.mk

# Do not change above "include" line(s)

# Arguments to tools, will move to make system once finalized.

CFLAGS         =
CDEFS          =
#Uncomment the below line to use sys manager
CDEFS          += SYSLINK_USE_LOADER
ifeq ($(BUILD),udeb)
CDEFS          += DEBUG
endif

EXEC_ARGS      =
ST_LIB_ARGS    =
SH_LIB_ARGS    =

# Define this macro if target runs in kernel mode
#__KERNEL__ = 1

# Target name and extension
# static library        (ST_LIB): filename.a
# shared library soname (SH_LIB): filename.so.maj_ver.min_ver
# executable            (EXEC)  : filename.out

TARGETNAME  = syslink_tilertest


# TARGETTYPE must be EXEC, ST_LIB or SH_LIB in upper case.

TARGETTYPE  = EXEC

# install directory relative to the HOSTTARGET directory
HOSTRELEASE = syslink

# install directory relative to the root filesystem
ROOTFSRELEASE = syslink

# Folders in which gmake will run before building current target

SUBMODULES  = \

# Filename must not begin with '.', '/' or '\'

SOURCES     = \
TilerSyslinkApp.c \
TilerTestApp.c

# Search path for include files

INCLUDES    = \
    $(PROJROOT)/../api/include \
    $(PROJROOT)/inc \
    $(TILER_INC_PATH) \

# Libraries needed for linking.

ST_LIBS        =
SH_LIBS        = pthread rt ipcutils procmgr ipc rcm syslinknotify timemmgr
#Uncomment the below line to use sys manager
SH_LIBS        += sysmgr

# Search path for library (and linker command) files.
# Current folder and target folder are included by default.

LIBINCLUDES += $(TILER_INC_PATH)/../ $(TILER_INC_PATH)


# Do not change below "include" line(s)

include $(PROJROOT)/make/build.mk
