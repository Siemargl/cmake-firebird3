# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace empbuild with binary name. e.g. mbase or FBase
SET (this_target empbuild)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../src/include,../../../src/include/gen,../../../src/jrd
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../gen/examples/empbuild.c
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	<header>
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_CRT_SECURE_NO_WARNINGS -D_CONSOLE 
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} )

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		)
