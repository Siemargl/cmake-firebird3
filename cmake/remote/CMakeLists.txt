# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace remote with binary name. e.g. mbase or FBase
SET (this_target remote)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
	../../../src/include
	../../../src/include/gen
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/auth/trusted/AuthSspi.cpp
	../../../src/remote/inet.cpp
	../../../src/remote/merge.cpp
	../../../src/remote/os/win32/wnet.cpp
	../../../src/remote/os/win32/xnet.cpp
	../../../src/remote/parser.cpp
	../../../src/remote/protocol.cpp
	../../../src/remote/remote.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/auth/trusted/AuthSspi.h
	../../../src/remote/inet_proto.h
	../../../src/remote/merge_proto.h
	../../../src/remote/os/win32/wnet_proto.h
	../../../src/remote/os/win32/xnet.h
	../../../src/remote/os/win32/xnet_proto.h
	../../../src/remote/parse_proto.h
	../../../src/remote/proto_proto.h
	../../../src/remote/protocol.h
	../../../src/remote/remot_proto.h
	../../../src/remote/remote.h
	../../../src/remote/remote_def.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_LIB -DSUPERSERVER
	)

## section: add target
ADD_LIBRARY (${this_target} STATIC ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
#ADD_DEPENDENCIES(${this_target} )

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		)
