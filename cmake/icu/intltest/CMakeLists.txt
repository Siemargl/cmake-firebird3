# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace intltest with binary name. e.g. mbase or FBase
SET (this_target intltest)
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
	../../../extern/icu/source/test/intltest/allcoll.cpp
	../../../extern/icu/source/test/intltest/apicoll.cpp
	../../../extern/icu/source/test/intltest/astrotst.cpp
	../../../extern/icu/source/test/intltest/calcasts.cpp
	../../../extern/icu/source/test/intltest/callimts.cpp
	../../../extern/icu/source/test/intltest/calregts.cpp
	../../../extern/icu/source/test/intltest/caltest.cpp
	../../../extern/icu/source/test/intltest/caltztst.cpp
	../../../extern/icu/source/test/intltest/canittst.cpp
	../../../extern/icu/source/test/intltest/citrtest.cpp
	../../../extern/icu/source/test/intltest/cntabcol.cpp
	../../../extern/icu/source/test/intltest/convtest.cpp
	../../../extern/icu/source/test/intltest/cpdtrtst.cpp
	../../../extern/icu/source/test/intltest/currcoll.cpp
	../../../extern/icu/source/test/intltest/dacoll.cpp
	../../../extern/icu/source/test/intltest/dadrcoll.cpp
	../../../extern/icu/source/test/intltest/dcfmapts.cpp
	../../../extern/icu/source/test/intltest/decoll.cpp
	../../../extern/icu/source/test/intltest/dtfmapts.cpp
	../../../extern/icu/source/test/intltest/dtfmrgts.cpp
	../../../extern/icu/source/test/intltest/dtfmtrtts.cpp
	../../../extern/icu/source/test/intltest/dtfmttst.cpp
	../../../extern/icu/source/test/intltest/encoll.cpp
	../../../extern/icu/source/test/intltest/escoll.cpp
	../../../extern/icu/source/test/intltest/ficoll.cpp
	../../../extern/icu/source/test/intltest/frcoll.cpp
	../../../extern/icu/source/test/intltest/g7coll.cpp
	../../../extern/icu/source/test/intltest/icusvtst.cpp
	../../../extern/icu/source/test/intltest/idnaref.cpp
	../../../extern/icu/source/test/intltest/incaltst.cpp
	../../../extern/icu/source/test/intltest/intltest.cpp
	../../../extern/icu/source/test/intltest/itercoll.cpp
	../../../extern/icu/source/test/intltest/itformat.cpp
	../../../extern/icu/source/test/intltest/itmajor.cpp
	../../../extern/icu/source/test/intltest/itrbbi.cpp
	../../../extern/icu/source/test/intltest/itrbnf.cpp
	../../../extern/icu/source/test/intltest/itrbnfp.cpp
	../../../extern/icu/source/test/intltest/itrbnfrt.cpp
	../../../extern/icu/source/test/intltest/ittrans.cpp
	../../../extern/icu/source/test/intltest/itutil.cpp
	../../../extern/icu/source/test/intltest/jacoll.cpp
	../../../extern/icu/source/test/intltest/jamotest.cpp
	../../../extern/icu/source/test/intltest/lcukocol.cpp
	../../../extern/icu/source/test/intltest/loctest.cpp
	../../../extern/icu/source/test/intltest/miscdtfm.cpp
	../../../extern/icu/source/test/intltest/mnkytst.cpp
	../../../extern/icu/source/test/intltest/msfmrgts.cpp
	../../../extern/icu/source/test/intltest/nmfmapts.cpp
	../../../extern/icu/source/test/intltest/nmfmtrt.cpp
	../../../extern/icu/source/test/intltest/normconf.cpp
	../../../extern/icu/source/test/intltest/nptrans.cpp
	../../../extern/icu/source/test/intltest/numfmtst.cpp
	../../../extern/icu/source/test/intltest/numrgts.cpp
	../../../extern/icu/source/test/intltest/pptest.cpp
	../../../extern/icu/source/test/intltest/punyref.c
	../../../extern/icu/source/test/intltest/rbbiapts.cpp
	../../../extern/icu/source/test/intltest/rbbitst.cpp
	../../../extern/icu/source/test/intltest/regcoll.cpp
	../../../extern/icu/source/test/intltest/regextst.cpp
	../../../extern/icu/source/test/intltest/reptest.cpp
	../../../extern/icu/source/test/intltest/restest.cpp
	../../../extern/icu/source/test/intltest/restsnew.cpp
	../../../extern/icu/source/test/intltest/sdtfmtts.cpp
	../../../extern/icu/source/test/intltest/sfwdchit.cpp
	../../../extern/icu/source/test/intltest/srchtest.cpp
	../../../extern/icu/source/test/intltest/strcase.cpp
	../../../extern/icu/source/test/intltest/strtest.cpp
	../../../extern/icu/source/test/intltest/tchcfmt.cpp
	../../../extern/icu/source/test/intltest/testidn.cpp
	../../../extern/icu/source/test/intltest/testidna.cpp
	../../../extern/icu/source/test/intltest/testutil.cpp
	../../../extern/icu/source/test/intltest/textfile.cpp
	../../../extern/icu/source/test/intltest/tfsmalls.cpp
	../../../extern/icu/source/test/intltest/thcoll.cpp
	../../../extern/icu/source/test/intltest/tmsgfmt.cpp
	../../../extern/icu/source/test/intltest/tokiter.cpp
	../../../extern/icu/source/test/intltest/transapi.cpp
	../../../extern/icu/source/test/intltest/transrt.cpp
	../../../extern/icu/source/test/intltest/transtst.cpp
	../../../extern/icu/source/test/intltest/trcoll.cpp
	../../../extern/icu/source/test/intltest/trnserr.cpp
	../../../extern/icu/source/test/intltest/tscoll.cpp
	../../../extern/icu/source/test/intltest/tsdate.cpp
	../../../extern/icu/source/test/intltest/tsdcfmsy.cpp
	../../../extern/icu/source/test/intltest/tsdtfmsy.cpp
	../../../extern/icu/source/test/intltest/tsmthred.cpp
	../../../extern/icu/source/test/intltest/tsnmfmt.cpp
	../../../extern/icu/source/test/intltest/tsputil.cpp
	../../../extern/icu/source/test/intltest/tstnorm.cpp
	../../../extern/icu/source/test/intltest/tstnrapi.cpp
	../../../extern/icu/source/test/intltest/tzbdtest.cpp
	../../../extern/icu/source/test/intltest/tzregts.cpp
	../../../extern/icu/source/test/intltest/tztest.cpp
	../../../extern/icu/source/test/intltest/ucaconf.cpp
	../../../extern/icu/source/test/intltest/ucdtest.cpp
	../../../extern/icu/source/test/intltest/uobjtest.cpp
	../../../extern/icu/source/test/intltest/usettest.cpp
	../../../extern/icu/source/test/intltest/ustrtest.cpp
	../../../extern/icu/source/test/intltest/v32test.cpp
	../../../extern/icu/source/test/intltest/svccoll.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/test/intltest/allcoll.h
	../../../extern/icu/source/test/intltest/apicoll.h
	../../../extern/icu/source/test/intltest/astrotst.h
	../../../extern/icu/source/test/intltest/calcasts.h
	../../../extern/icu/source/test/intltest/callimts.h
	../../../extern/icu/source/test/intltest/calregts.h
	../../../extern/icu/source/test/intltest/caltest.h
	../../../extern/icu/source/test/intltest/caltztst.h
	../../../extern/icu/source/test/intltest/canittst.h
	../../../extern/icu/source/test/intltest/citrtest.h
	../../../extern/icu/source/test/intltest/cntabcol.h
	../../../extern/icu/source/test/intltest/convtest.h
	../../../extern/icu/source/test/intltest/cpdtrtst.h
	../../../extern/icu/source/test/intltest/currcoll.h
	../../../extern/icu/source/test/intltest/dacoll.h
	../../../extern/icu/source/test/intltest/dadrcoll.h
	../../../extern/icu/source/test/intltest/dcfmapts.h
	../../../extern/icu/source/test/intltest/decoll.h
	../../../extern/icu/source/test/intltest/dtfmapts.h
	../../../extern/icu/source/test/intltest/dtfmrgts.h
	../../../extern/icu/source/test/intltest/dtfmtrtts.h
	../../../extern/icu/source/test/intltest/dtfmttst.h
	../../../extern/icu/source/test/intltest/encoll.h
	../../../extern/icu/source/test/intltest/escoll.h
	../../../extern/icu/source/test/intltest/ficoll.h
	../../../extern/icu/source/test/intltest/frcoll.h
	../../../extern/icu/source/test/intltest/g7coll.h
	../../../extern/icu/source/test/intltest/icusvtst.h
	../../../extern/icu/source/test/intltest/idnaref.h
	../../../extern/icu/source/test/intltest/incaltst.h
	../../../extern/icu/source/test/intltest/intltest.h
	../../../extern/icu/source/test/intltest/itercoll.h
	../../../extern/icu/source/test/intltest/itformat.h
	../../../extern/icu/source/test/intltest/itmajor.h
	../../../extern/icu/source/test/intltest/itrbbi.h
	../../../extern/icu/source/test/intltest/itrbnf.h
	../../../extern/icu/source/test/intltest/itrbnfp.h
	../../../extern/icu/source/test/intltest/itrbnfrt.h
	../../../extern/icu/source/test/intltest/ittrans.h
	../../../extern/icu/source/test/intltest/itutil.h
	../../../extern/icu/source/test/intltest/jacoll.h
	../../../extern/icu/source/test/intltest/jamotest.h
	../../../extern/icu/source/test/intltest/lcukocol.h
	../../../extern/icu/source/test/intltest/loctest.h
	../../../extern/icu/source/test/intltest/miscdtfm.h
	../../../extern/icu/source/test/intltest/mnkytst.h
	../../../extern/icu/source/test/intltest/msfmrgts.h
	../../../extern/icu/source/test/intltest/nmfmapts.h
	../../../extern/icu/source/test/intltest/nmfmtrt.h
	../../../extern/icu/source/test/intltest/normconf.h
	../../../extern/icu/source/test/intltest/nptrans.h
	../../../extern/icu/source/test/intltest/numfmtst.h
	../../../extern/icu/source/test/intltest/numrgts.h
	../../../extern/icu/source/test/intltest/pptest.h
	../../../extern/icu/source/test/intltest/punyref.h
	../../../extern/icu/source/test/intltest/rbbiapts.h
	../../../extern/icu/source/test/intltest/rbbitst.h
	../../../extern/icu/source/test/intltest/regcoll.h
	../../../extern/icu/source/test/intltest/regextst.h
	../../../extern/icu/source/test/intltest/reptest.h
	../../../extern/icu/source/test/intltest/restest.h
	../../../extern/icu/source/test/intltest/restsnew.h
	../../../extern/icu/source/test/intltest/sdtfmtts.h
	../../../extern/icu/source/test/intltest/sfwdchit.h
	../../../extern/icu/source/test/intltest/srchtest.h
	../../../extern/icu/source/test/intltest/strtest.h
	../../../extern/icu/source/test/intltest/tchcfmt.h
	../../../extern/icu/source/test/intltest/testidna.h
	../../../extern/icu/source/test/intltest/testutil.h
	../../../extern/icu/source/test/intltest/textfile.h
	../../../extern/icu/source/test/intltest/tfsmalls.h
	../../../extern/icu/source/test/intltest/thcoll.h
	../../../extern/icu/source/test/intltest/tmsgfmt.h
	../../../extern/icu/source/test/intltest/tokiter.h
	../../../extern/icu/source/test/intltest/transapi.h
	../../../extern/icu/source/test/intltest/transrt.h
	../../../extern/icu/source/test/intltest/transtst.h
	../../../extern/icu/source/test/intltest/trcoll.h
	../../../extern/icu/source/test/intltest/trnserr.h
	../../../extern/icu/source/test/intltest/tscoll.h
	../../../extern/icu/source/test/intltest/tsdate.h
	../../../extern/icu/source/test/intltest/tsdcfmsy.h
	../../../extern/icu/source/test/intltest/tsdtfmsy.h
	../../../extern/icu/source/test/intltest/tsmthred.h
	../../../extern/icu/source/test/intltest/tsnmfmt.h
	../../../extern/icu/source/test/intltest/tsputil.h
	../../../extern/icu/source/test/intltest/tstnorm.h
	../../../extern/icu/source/test/intltest/tzbdtest.h
	../../../extern/icu/source/test/intltest/tzregts.h
	../../../extern/icu/source/test/intltest/tztest.h
	../../../extern/icu/source/test/intltest/ucaconf.h
	../../../extern/icu/source/test/intltest/ucdtest.h
	../../../extern/icu/source/test/intltest/uobjtest.h
	../../../extern/icu/source/test/intltest/usettest.h
	../../../extern/icu/source/test/intltest/ustrtest.h
	../../../extern/icu/source/test/intltest/v32test.h
	../../../extern/icu/source/test/intltest/svccoll.h
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
	icuuc30 icuin30 icudt30 icutu30 ctestfw
		)
