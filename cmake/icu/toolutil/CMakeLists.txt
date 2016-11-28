# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace toolutil with binary name. e.g. mbase or FBase
SET (this_target icutu30)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/common;
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../../extern/icu/source/tools/toolutil/toolutil.c
	../../../../extern/icu/source/tools/toolutil/ucbuf.c
	../../../../extern/icu/source/tools/toolutil/ucm.c
	../../../../extern/icu/source/tools/toolutil/ucmpwrit.c
	../../../../extern/icu/source/tools/toolutil/ucmstate.c
	../../../../extern/icu/source/tools/toolutil/unewdata.c
	../../../../extern/icu/source/tools/toolutil/uoptions.c
	../../../../extern/icu/source/tools/toolutil/uparse.c
	../../../../extern/icu/source/tools/toolutil/uperf.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../../extern/icu/source/tools/toolutil/toolutil.h
	../../../extern/icu/source/tools/toolutil/ucbuf.h
	../../../../extern/icu/source/tools/toolutil/ucm.h
	../../../../extern/icu/source/tools/toolutil/ucmpwrit.h
	../../../../extern/icu/source/tools/toolutil/unewdata.h
	../../../../extern/icu/source/tools/toolutil/uoptions.h
	../../../../extern/icu/source/tools/toolutil/uparse.h
	../../../../extern/icu/source/tools/toolutil/uperf.h
	../../../../extern/icu/source/tools/toolutil/utimer.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
#ADD_DEPENDENCIES(${this_target} icuuc30 icuin30 icudt30)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		icuuc30 icuin30 icudt30)
