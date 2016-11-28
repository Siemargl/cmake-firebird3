# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace io with binary name. e.g. mbase or FBase
SET (this_target icuio30)
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
	../../../extern/icu/source/io/io.rc
	../../../extern/icu/source/io/locbund.c
	../../../extern/icu/source/io/sprintf.c
	../../../extern/icu/source/io/sscanf.c
	../../../extern/icu/source/io/ufile.c
	../../../extern/icu/source/io/ufmt_cmn.c
	../../../extern/icu/source/io/uprintf.c
	../../../extern/icu/source/io/uprntf_p.c
	../../../extern/icu/source/io/uscanf.c
	../../../extern/icu/source/io/uscanf_p.c
	../../../extern/icu/source/io/ustdio.c
	../../../extern/icu/source/io/ustream.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/io/locbund.h
	../../../extern/icu/source/io/ufile.h
	../../../extern/icu/source/io/ufmt_cmn.h
	../../../extern/icu/source/io/unicode/ustdio.h
	../../../extern/icu/source/io/unicode/ustream.h
	../../../extern/icu/source/io/uprintf.h
	../../../extern/icu/source/io/uscanf.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DU_IO_IMPLEMENTATION
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

# common include files
SET (${this_target}_COPY_FILES
unicode/ustdio.h
unicode/ustream.h
)


FILE(MAKE_DIRECTORY ../../../../extern/icu/include/unicode)    

foreach(var ${${this_target}_COPY_FILES})
    FILE(COPY ../../../../extern/icu/source/io/${var} 
	DESTINATION ../../../extern/icu/include/unicode)
endforeach()


