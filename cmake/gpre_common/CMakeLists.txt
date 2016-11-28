# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace gpre_common with binary name. e.g. mbase or FBase
SET (this_target gpre_common)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
	../../../src/include
	../../../src/include/gen
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/gpre/c_cxx.cpp
	../../../src/gpre/cmd.cpp
	../../../src/gpre/cme.cpp
	../../../src/gpre/cmp.cpp
	../../../src/gpre/exp.cpp
	../../../src/gpre/gpre.cpp
	../../../src/gpre/hsh.cpp
	../../../src/gpre/int_cxx.cpp
	../../../src/gpre/jrdmet.cpp
	../../../src/gpre/languages/ada.cpp
	../../../src/gpre/languages/cob.cpp
	../../../src/gpre/languages/fbrmclib.cpp
	../../../src/gpre/languages/ftn.cpp
	../../../src/gpre/languages/pas.cpp
	../../../src/gpre/languages/rmc.cpp
	../../../src/gpre/movg.cpp
	../../../src/gpre/msc.cpp
	../../../src/gpre/par.cpp
	../../../src/gpre/pat.cpp
	../../../src/gpre/sqe.cpp
	../../../src/gpre/sql.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/gpre/cmd_proto.h
	../../../src/gpre/cme_proto.h
	../../../src/gpre/cmp_proto.h
	../../../src/gpre/exp_proto.h
	../../../src/gpre/gpre.h
	../../../src/gpre/gpre_meta.h
	../../../src/gpre/gpre_proto.h
	../../../src/gpre/gpreswi.h
	../../../src/gpre/hsh.h
	../../../src/gpre/hsh_proto.h
	../../../src/gpre/jrdme_proto.h
	../../../src/gpre/lang_proto.h
	../../../src/gpre/movg_proto.h
	../../../src/gpre/msc_proto.h
	../../../src/gpre/par_proto.h
	../../../src/gpre/parse.h
	../../../src/gpre/pat.h
	../../../src/gpre/pat_proto.h
	../../../src/gpre/sqe_proto.h
	../../../src/gpre/sql_proto.h
	../../../src/gpre/words.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DGPRE_FORTRAN -DGPRE_PASCAL -DGPRE_COBOL -DGPRE_ADA -D_LIB -DSUPERSERVER
	)

## section: add target
ADD_LIBRARY (${this_target} STATIC ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
#ADD_DEPENDENCIES(${this_target} )

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		)
