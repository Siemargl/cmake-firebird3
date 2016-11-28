# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace gpre with binary name. e.g. mbase or FBase
SET (this_target gpre)
#PROJECT(${this_target})

##zws OutputDirectory="..\..\..\temp\$(PlatformName)\$(ConfigurationName)\firebird\"


## section: include directory

INCLUDE_DIRECTORIES(
  ../../../src/include,../../../src/include/gen,../../../src/jrd
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	gpre_meta.cpp
	../../../src/gpre/std/gpre_meta.epp
	../../../src/jrd/version.rc
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	)

add_custom_command (
  OUTPUT 
	gpre_meta.cpp
  COMMAND 
	@echo done by preprocess_boot
  COMMAND 
	@copy ..\\gpre\\std\\*.* .
)


SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DGPRE_FORTRAN -DGPRE_PASCAL -DGPRE_COBOL -DGPRE_ADA -D_CONSOLE -DSUPERCLIENT
	)

## section: add target
ADD_EXECUTABLE (${this_target} ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} 
	preprocess_boot
	comctl32 ws2_32 mpr version
	gpre_common common fbclient
)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		comctl32 ws2_32 version mpr
		gpre_common common fbclient
)
