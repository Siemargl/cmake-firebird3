# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace stubdata with binary name. e.g. mbase or FBase
SET (this_target icudt30)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/common
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/icu/source/stubdata/stubdata.c
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
	-DSTUBDATA_EXPORTS
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
#ADD_DEPENDENCIES(${this_target})

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		)

ADD_CUSTOM_TARGET(stubdatabuilt ALL
    DEPENDS ${this_target}
    COMMAND 
	@echo "File with stubdata build time, used as a dependency to trigger fresh data build, since stubdata dll will overwrite the real one." > ${ICU_SRC_PATH}\\stubdata\\stubdatabuilt.txt
)
