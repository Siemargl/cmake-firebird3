# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace burp with binary name. e.g. mbase or FBase
SET (this_target burp)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
	../../../src/include
	../../../src/include/gen
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	backup.cpp
	OdsDetection.cpp
	restore.cpp
	../../../src/burp/backup.epp
	../../../src/burp/burp.cpp
	../../../src/burp/canonical.cpp
	../../../src/burp/misc.cpp
	../../../src/burp/mvol.cpp
	../../../src/burp/OdsDetection.epp
	../../../src/burp/restore.epp
	)

add_custom_command (
  OUTPUT 
	backup.cpp
	OdsDetection.cpp
	restore.cpp
  COMMAND @echo done by preprocess_boot
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
	-D_LIB
	)

## section: add target
ADD_LIBRARY (${this_target} STATIC ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} ws2_32 preprocess_boot)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		ws2_32)
