# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace gbak with binary name. e.g. mbase or FBase
SET (this_target gbak)
#PROJECT(${this_target})

##zws OutputDirectory="..\..\..\temp\$(PlatformName)\$(ConfigurationName)\firebird\"


## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/burp/main/burpMain.cpp
	../../../src/jrd/version.rc
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/burp/backu_proto.h
	../../../src/burp/burp.h
	../../../src/burp/burp_proto.h
	../../../src/burp/burpswi.h
	../../../src/burp/canon_proto.h
	../../../src/burp/misc_proto.h
	../../../src/burp/mvol_proto.h
	../../../src/burp/OdsDetection.h
	../../../src/burp/resto_proto.h
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
	comctl32 ws2_32 mpr version gpre_boot
	mpr common fbclient alice burp
	${CMAKE_BINARY_DIR}/icu/common
	${CMAKE_BINARY_DIR}/icu/stubdata
	${CMAKE_BINARY_DIR}/icu/i18n
)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		burp alice common fbclient mpr ws2_32 
		comctl32 version
		${CMAKE_BINARY_DIR}/icu/common/icuuc30.lib
		${CMAKE_BINARY_DIR}/icu/stubdata/icudt30.lib
		${CMAKE_BINARY_DIR}/icu/i18n/icuin30.lib
)

