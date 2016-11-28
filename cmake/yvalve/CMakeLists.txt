# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace yvalve with binary name. e.g. mbase or FBase
SET (this_target fbclient)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../src/include
	../../../src/include/gen
	../../../extern/icu/include
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	array.cpp
	blob.cpp
	../../../src/auth/SecurityDatabase/LegacyClient.cpp
	../../../src/jrd/os/win32/ibinitdll.cpp
	../../../src/jrd/version.rc
	../../../src/remote/client/interface.cpp
	../../../src/yvalve/alt.cpp
	../../../src/yvalve/array.epp
	../../../src/yvalve/blob.epp
	../../../src/yvalve/gds.cpp
	../../../src/yvalve/keywords.cpp
	../../../src/yvalve/MasterImplementation.cpp
	../../../src/yvalve/perf.cpp
	../../../src/yvalve/PluginManager.cpp
	../../../src/yvalve/preparse.cpp
	../../../src/yvalve/user_dsql.cpp
	../../../src/yvalve/utl.cpp
	../../../src/yvalve/utly.cpp
	../../../src/yvalve/why.cpp
	../defs/firebird.def
	)

add_custom_command (
  OUTPUT 
	 array.cpp
	 blob.cpp
  COMMAND @echo done by preprocess_boot
)


## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/auth/SecurityDatabase/LegacyClient.h
	../../../src/yvalve/alt_proto.h
	../../../src/yvalve/array_proto.h
	../../../src/yvalve/blob_proto.h
	../../../src/yvalve/gds_proto.h
	../../../src/yvalve/keywords.h
	../../../src/yvalve/perf.h
	../../../src/yvalve/perf_proto.h
	../../../src/yvalve/PluginManager.h
	../../../src/yvalve/prepa_proto.h
	../../../src/yvalve/user__proto.h
	../../../src/yvalve/utl_proto.h
	../../../src/yvalve/utly_proto.h
	../../../src/yvalve/why_proto.h
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
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} mpr ws2_32 parsing preprocess_boot )

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		remote common mpr  ws2_32 
		${CMAKE_BINARY_DIR}/icu/common/icuuc30.lib
		${CMAKE_BINARY_DIR}/icu/stubdata/icudt30.lib
		${CMAKE_BINARY_DIR}/icu/i18n/icuin30.lib
)

