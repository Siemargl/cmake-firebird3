# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace gpre_boot with binary name. e.g. mbase or FBase
SET (this_target gpre_boot)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
	../../../src/include
	../../../src/include/gen
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/gpre/boot/gpre_meta_boot.cpp
	../../../src/jrd/version.rc
	../../../src/yvalve/gds.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_CONSOLE -DSUPERCLIENT
	)

## section: add target
ADD_EXECUTABLE (${this_target} ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} 
	gpre_common common
	comctl32 ws2_32 mpr version)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	gpre_common common
	comctl32 ws2_32 mpr version)
