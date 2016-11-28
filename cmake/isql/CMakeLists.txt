# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace isql with binary name. e.g. mbase or FBase
SET (this_target isql)
#PROJECT(${this_target})

##zws OutputDirectory="..\..\..\temp\$(PlatformName)\$(ConfigurationName)\firebird\"


## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	extract.cpp
	isql.cpp
	show.cpp
	../../../src/common/fb_exception.cpp
	../../../src/isql/ColList.cpp
	../../../src/isql/Extender.cpp
	../../../src/isql/extract.epp
	../../../src/isql/InputDevices.cpp
	../../../src/isql/isql.epp
	../../../src/isql/iutils.cpp
	../../../src/isql/OptionsBase.cpp
	../../../src/isql/show.epp
	../../../src/jrd/version.rc
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/isql/ColList.h
	../../../src/isql/Extender.h
	../../../src/isql/extra_proto.h
	../../../src/isql/InputDevices.h
	../../../src/isql/isql.h
	../../../src/isql/isql_proto.h
	../../../src/isql/iutils_proto.h
	../../../src/isql/OptionsBase.h
	../../../src/isql/show_proto.h
	)

add_custom_command (
  OUTPUT 
	extract.cpp
	isql.cpp
	show.cpp
  COMMAND 
	@echo done by preprocess_boot
  COMMAND 
	@copy ..\\isql\\*.* .
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
	comctl32 ws2_32 mpr version)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		comctl32 ws2_32 mpr version)

ADD_DEPENDENCIES(${this_target} 
	comctl32 ws2_32 mpr version
	common fbclient alice burp preprocess_boot
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
