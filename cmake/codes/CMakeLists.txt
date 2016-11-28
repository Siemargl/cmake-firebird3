# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace codes with binary name. e.g. mbase or FBase
SET (this_target codes)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	codes.cpp
	../../../src/misc/codes.epp
	../../../src/jrd/version.rc
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES

	)
add_custom_command (
  OUTPUT 
	codes.cpp
  COMMAND 
	@echo done by preprocess_tree
  COMMAND 
	@copy ..\\misc\\*.* .
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
ADD_DEPENDENCIES(${this_target} comctl32 ws2_32 mpr version preprocess_tree)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		comctl32 ws2_32 mpr version
	remote	common alice burp fbclient
)
