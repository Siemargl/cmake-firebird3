# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace ib_util with binary name. e.g. mbase or FBase
SET (this_target ib_util)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/extlib/ib_util.cpp
	../../../src/jrd/version.rc
	../defs/ib_util.def
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/extlib/ib_util.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_USRDLL -DIB_UTIL_EXPORTS
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} comctl32 ws2_32 mpr version)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		comctl32 ws2_32 mpr version)
