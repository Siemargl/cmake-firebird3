# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace fbserver with binary name. e.g. mbase or FBase
SET (this_target fbserver)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/auth/SecurityDatabase/LegacyServer.cpp
	../../../src/remote/server/os/win32/caution.ico
	../../../src/remote/server/os/win32/chop.cpp
	../../../src/remote/server/os/win32/cntl.cpp
	../../../src/remote/server/os/win32/property.cpp
	../../../src/remote/server/os/win32/server.ico
	../../../src/remote/server/os/win32/srvr_w32.cpp
	../../../src/remote/server/os/win32/window.cpp
	../../../src/remote/server/os/win32/window.rc
	../../../src/remote/server/server.cpp
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
	-DSUPERSERVER 
	)

## section: add target
ADD_EXECUTABLE (${this_target} WIN32 ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} comctl32 ws2_32 mpr version 
	icuuc30 remote common alice burp fbclient  make_boot engine
)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		comctl32 ws2_32 mpr version 
	remote	common alice burp fbclient 
	${CMAKE_BINARY_DIR}/icu/common/icuuc30.lib
	${CMAKE_BINARY_DIR}/icu/stubdata/icudt30.lib
	${CMAKE_BINARY_DIR}/icu/i18n/icuin30.lib
)
