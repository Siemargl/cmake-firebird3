# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace fbtrace with binary name. e.g. mbase or FBase
SET (this_target fbtrace)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../src/include/gen
	../../../src/include
	../../../src/common/classes
	../../../extern/icu/include
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/jrd/version.rc
	../../../src/utilities/ntrace/os/win32/platform.cpp
	../../../src/utilities/ntrace/PluginLogWriter.cpp
	../../../src/utilities/ntrace/TraceConfiguration.cpp
	../../../src/utilities/ntrace/traceplugin.cpp
	../../../src/utilities/ntrace/TracePluginImpl.cpp
	../../../src/utilities/ntrace/TraceUnicodeUtils.cpp
	../defs/plugin.def
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/utilities/ntrace/os/platform.h
	../../../src/utilities/ntrace/paramtable.h
	../../../src/utilities/ntrace/PluginLogWriter.h
	../../../src/utilities/ntrace/TracePluginConfig.h
	../../../src/utilities/ntrace/TracePluginImpl.h
	../../../src/utilities/ntrace/TraceUnicodeUtils.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DFBTRACE_EXPORTS -DSUPERCLIENT -DNAMESPACE=Vulcan
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} 
	mpr icuuc30 common fbclient)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	mpr common fbclient
	${CMAKE_BINARY_DIR}/icu/common/icuuc30.lib
)