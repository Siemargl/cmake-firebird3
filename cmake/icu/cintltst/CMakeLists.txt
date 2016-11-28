# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace cintltst with binary name. e.g. mbase or FBase
SET (this_target cintltst)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/../include;
  ../../../../extern/icu/source/tools/ctestfw;
  ../../../../extern/icu/source/common;
  ../../../../extern/icu/source/i18n;
  ../../../../extern/icu/source/tools/toolutil
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/icu/source/test/cintltst/bocu1tst.c
	../../../extern/icu/source/test/cintltst/callcoll.c
	../../../extern/icu/source/test/cintltst/calltest.c
	../../../extern/icu/source/test/cintltst/capitst.c
	../../../extern/icu/source/test/cintltst/cbiapts.c
	../../../extern/icu/source/test/cintltst/cbididat.c              	
	../../../extern/icu/source/test/cintltst/cbiditst.c
	../../../extern/icu/source/test/cintltst/cbkittst.c
	../../../extern/icu/source/test/cintltst/ccaltst.c
	../../../extern/icu/source/test/cintltst/ccapitst.c
	../../../extern/icu/source/test/cintltst/ccolltst.c
	../../../extern/icu/source/test/cintltst/cconvtst.c
	../../../extern/icu/source/test/cintltst/cctest.c
	../../../extern/icu/source/test/cintltst/ccurrtst.c
	../../../extern/icu/source/test/cintltst/cdantst.c
	../../../extern/icu/source/test/cintltst/cdattst.c
	../../../extern/icu/source/test/cintltst/cdetst.c
	../../../extern/icu/source/test/cintltst/cdtdptst.c
	../../../extern/icu/source/test/cintltst/cdtrgtst.c
	../../../extern/icu/source/test/cintltst/cestst.c
	../../../extern/icu/source/test/cintltst/cfintst.c
	../../../extern/icu/source/test/cintltst/cformtst.c
	../../../extern/icu/source/test/cintltst/cfrtst.c
	../../../extern/icu/source/test/cintltst/cg7coll.c
	../../../extern/icu/source/test/cintltst/chashtst.c
	../../../extern/icu/source/test/cintltst/cintltst.c
	../../../extern/icu/source/test/cintltst/citertst.c
	../../../extern/icu/source/test/cintltst/cjaptst.c
	../../../extern/icu/source/test/cintltst/cloctst.c
	../../../extern/icu/source/test/cintltst/cmsccoll.c
	../../../extern/icu/source/test/cintltst/cmsgtst.c
	../../../extern/icu/source/test/cintltst/cnmdptst.c
	../../../extern/icu/source/test/cintltst/cnormtst.c
	../../../extern/icu/source/test/cintltst/cnumtst.c
	../../../extern/icu/source/test/cintltst/colutil.c
	../../../extern/icu/source/test/cintltst/cposxtst.c
	../../../extern/icu/source/test/cintltst/cregrtst.c
	../../../extern/icu/source/test/cintltst/crestst.c
	../../../extern/icu/source/test/cintltst/creststn.c
	../../../extern/icu/source/test/cintltst/cstrcase.c
	../../../extern/icu/source/test/cintltst/cstrtest.c
	../../../extern/icu/source/test/cintltst/ctstdep.c
	../../../extern/icu/source/test/cintltst/cturtst.c
	../../../extern/icu/source/test/cintltst/cucdapi.c
	../../../extern/icu/source/test/cintltst/cucdtst.c
	../../../extern/icu/source/test/cintltst/custrtrn.c
	../../../extern/icu/source/test/cintltst/custrtst.c
	../../../extern/icu/source/test/cintltst/cutiltst.c
	../../../extern/icu/source/test/cintltst/encoll.c
	../../../extern/icu/source/test/cintltst/eurocreg.c
	../../../extern/icu/source/test/cintltst/hpmufn.c
	../../../extern/icu/source/test/cintltst/mstrmtst.c
	../../../extern/icu/source/test/cintltst/nccbtst.c
	../../../extern/icu/source/test/cintltst/ncnvfbts.c
	../../../extern/icu/source/test/cintltst/ncnvtst.c
	../../../extern/icu/source/test/cintltst/nucnvtst.c
	../../../extern/icu/source/test/cintltst/putiltst.c
	../../../extern/icu/source/test/cintltst/reapits.c
	../../../extern/icu/source/test/cintltst/sorttest.c
	../../../extern/icu/source/test/cintltst/stdnmtst.c
	../../../extern/icu/source/test/cintltst/tracetst.c
	../../../extern/icu/source/test/cintltst/trietest.c
	../../../extern/icu/source/test/cintltst/ucmptst.c
	../../../extern/icu/source/test/cintltst/udatatst.c
	../../../extern/icu/source/test/cintltst/uenumtst.c
	../../../extern/icu/source/test/cintltst/usettest.c
	../../../extern/icu/source/test/cintltst/usrchdat.c
	../../../extern/icu/source/test/cintltst/usrchtst.c
	../../../extern/icu/source/test/cintltst/utf16tst.c
	../../../extern/icu/source/test/cintltst/utf8tst.c
	../../../extern/icu/source/test/cintltst/utransts.c
	../../../extern/icu/source/test/cintltst/idnatest.c
	../../../extern/icu/source/test/cintltst/nfsprep.c
	../../../extern/icu/source/test/cintltst/spreptst.c
	../../../extern/icu/source/test/cintltst/sprpdata.c
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/test/cintltst/callcoll.h
	../../../extern/icu/source/test/cintltst/capitst.h
	../../../extern/icu/source/test/cintltst/cbiapts.h
	../../../extern/icu/source/test/cintltst/cbiditst.h
	../../../extern/icu/source/test/cintltst/ccaltst.h
	../../../extern/icu/source/test/cintltst/ccapitst.h
	../../../extern/icu/source/test/cintltst/ccolltst.h
	../../../extern/icu/source/test/cintltst/ccurrtst.h
	../../../extern/icu/source/test/cintltst/cdantst.h
	../../../extern/icu/source/test/cintltst/cdattst.h
	../../../extern/icu/source/test/cintltst/cdetst.h
	../../../extern/icu/source/test/cintltst/cdtdptst.h
	../../../extern/icu/source/test/cintltst/cdtrgtst.h
	../../../extern/icu/source/test/cintltst/cestst.h
	../../../extern/icu/source/test/cintltst/cfintst.h
	../../../extern/icu/source/test/cintltst/cformtst.h
	../../../extern/icu/source/test/cintltst/cfrtst.h
	../../../extern/icu/source/test/cintltst/cg7coll.h
	../../../extern/icu/source/test/cintltst/cintltst.h
	../../../extern/icu/source/test/cintltst/citertst.h
	../../../extern/icu/source/test/cintltst/cjaptst.h
	../../../extern/icu/source/test/cintltst/cloctst.h
	../../../extern/icu/source/test/cintltst/cmsgtst.h
	../../../extern/icu/source/test/cintltst/cnmdptst.h
	../../../extern/icu/source/test/cintltst/cnormtst.h
	../../../extern/icu/source/test/cintltst/cnumtst.h
	../../../extern/icu/source/test/cintltst/cregrtst.h
	../../../extern/icu/source/test/cintltst/crestst.h
	../../../extern/icu/source/test/cintltst/creststn.h
	../../../extern/icu/source/test/cintltst/cturtst.h
	../../../extern/icu/source/test/cintltst/cucdapi.h
	../../../extern/icu/source/test/cintltst/cucdtst.h
	../../../extern/icu/source/test/cintltst/encoll.h
	../../../extern/icu/source/test/cintltst/nccbtst.h
	../../../extern/icu/source/test/cintltst/ncnvfbts.h
	../../../extern/icu/source/test/cintltst/nucnvtst.h
	../../../extern/icu/source/test/cintltst/nfsprep.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_CONSOLE
	)

## section: add target
ADD_EXECUTABLE (${this_target} ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} icuuc30 icuin30 icudt30 icutu30 ctestfw)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	icuuc30 icuin30 icudt30 icutu30  ctestfw
		)
