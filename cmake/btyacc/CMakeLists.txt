# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace btyacc with binary name. e.g. mbase or FBase
SET (this_target btyacc)
#PROJECT(${this_target})

## section: include directory

SET (CMAKE_BUILD_TOOL SMAKE)

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/btyacc/closure.c
	../../../extern/btyacc/error.c
	../../../extern/btyacc/lalr.c
	../../../extern/btyacc/lr0.c
	../../../extern/btyacc/main.c
	../../../extern/btyacc/mkpar.c
	../../../extern/btyacc/mstring.c
	../../../extern/btyacc/output.c
	../../../extern/btyacc/reader.c
	../../../extern/btyacc/readskel.c
	../../../extern/btyacc/skeleton.c
	../../../extern/btyacc/symtab.c
	../../../extern/btyacc/verbose.c
	../../../extern/btyacc/warshall.c
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/btyacc/defs.h
	../../../extern/btyacc/mstring.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_MSC_VER=1500
	)

## section: add target
#ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )
ADD_EXECUTABLE(${this_target} ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
#ADD_DEPENDENCIES(${this_target} )

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		)
