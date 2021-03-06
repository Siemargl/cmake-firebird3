# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace layoutex with binary name. e.g. mbase or FBase
SET (this_target layoutex)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/../include;
  ../../../../extern/icu/source/tools/ctestfw;
  ../../../../extern/icu/source/common;
  ../../../../extern/icu/source;
  ../../../../extern/icu/source/i18n;
  ../../../../extern/icu/source/tools/toolutil
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/icu/source/layoutex/layoutex.rc
	../../../extern/icu/source/layoutex/ParagraphLayout.cpp
	../../../extern/icu/source/layoutex/RunArrays.cpp
	../../../extern/icu/source/layoutex/LXUtilities.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/layoutex/layout/ParagraphLayout.h
	../../../extern/icu/source/layoutex/layout/RunArrays.h
	../../../extern/icu/source/layoutex/LXUtilities.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DU_LAYOUTEX_IMPLEMENTATION
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} icuuc30 icuin30 icudt30 icutu30)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	icuuc30 icuin30 icudt30 icutu30
		)
