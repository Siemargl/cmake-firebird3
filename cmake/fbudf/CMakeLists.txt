# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace fbudf with binary name. e.g. mbase or FBase
SET (this_target fbudf)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/extlib/fbudf/fbudf.cpp
	../../../src/extlib/fbudf/fbudf.sql
	../../../src/extlib/fbudf/fbudf.txt
	../../../src/extlib/fbudf/stdafx.cpp
	../../../src/jrd/version.rc
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/extlib/fbudf/fbudf.h
	../../../src/extlib/fbudf/stdafx.h
	../../../src/jrd/ibase.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DSUPERCLIENT -DFBUDF_EXPORTS
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} 
	common fbclient
)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	common fbclient
)
		
