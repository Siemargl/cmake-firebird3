# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace fb2control with binary name. e.g. mbase or FBase
SET (this_target fb2control)
#PROJECT(${this_target})

##zws
SET(OutputDirectory "..\..\..\temp\$(PlatformName)\$(ConfigurationName)\firebird\system32")


## section: include directory

INCLUDE_DIRECTORIES(
  
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/utilities/fbcpl/ctrlpan.cpp
	../../../src/utilities/fbcpl/FBControl.cpp
	../../../src/utilities/fbcpl/FBControl.def
	../../../src/utilities/fbcpl/FBControl.rc
	../../../src/utilities/fbcpl/FBDialog.cpp
	../../../src/utilities/fbcpl/FBPanel.cpp
	../../../src/utilities/fbcpl/res/FBControl.rc2
	../../../src/utilities/fbcpl/res/server.ico
	../../../src/utilities/fbcpl/res/server_stop.ico
	../../../src/utilities/fbcpl/StdAfx.cpp
	../../../src/utilities/install/services.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/utilities/fbcpl/ctrlpan.h
	../../../src/utilities/fbcpl/FBControl.h
	../../../src/utilities/fbcpl/FBDialog.h
	../../../src/utilities/fbcpl/FBPanel.h
	../../../src/utilities/fbcpl/Resource.h
	../../../src/utilities/fbcpl/StdAfx.h
	../../../src/utilities/install/registry.h
	../../../src/utilities/install/servi_proto.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_USRDLL -DWINVER=0x400
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} shlwapi version)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		shlwapi version)
