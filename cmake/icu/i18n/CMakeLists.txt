# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace i18n with binary name. e.g. mbase or FBase
SET (this_target icuin30)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/../include;../../../../extern/icu/source/common;
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/icu/source/i18n/anytrans.cpp
	../../../extern/icu/source/i18n/astro.cpp
	../../../extern/icu/source/i18n/bocsu.c
	../../../extern/icu/source/i18n/buddhcal.cpp
	../../../extern/icu/source/i18n/calendar.cpp
	../../../extern/icu/source/i18n/chnsecal.cpp
	../../../extern/icu/source/i18n/choicfmt.cpp
	../../../extern/icu/source/i18n/coleitr.cpp
	../../../extern/icu/source/i18n/coll.cpp
	../../../extern/icu/source/i18n/cpdtrans.cpp
	../../../extern/icu/source/i18n/curramt.cpp
	../../../extern/icu/source/i18n/currfmt.cpp
	../../../extern/icu/source/i18n/currunit.cpp
	../../../extern/icu/source/i18n/datefmt.cpp
	../../../extern/icu/source/i18n/dcfmtsym.cpp
	../../../extern/icu/source/i18n/decimfmt.cpp
	../../../extern/icu/source/i18n/digitlst.cpp
	../../../extern/icu/source/i18n/dtfmtsym.cpp
	../../../extern/icu/source/i18n/esctrn.cpp
	../../../extern/icu/source/i18n/fmtable.cpp
	../../../extern/icu/source/i18n/format.cpp
	../../../extern/icu/source/i18n/funcrepl.cpp
	../../../extern/icu/source/i18n/gregocal.cpp
	../../../extern/icu/source/i18n/gregoimp.cpp
	../../../extern/icu/source/i18n/hebrwcal.cpp
	../../../extern/icu/source/i18n/i18n.rc
	../../../extern/icu/source/i18n/islamcal.cpp
	../../../extern/icu/source/i18n/japancal.cpp
	../../../extern/icu/source/i18n/measfmt.cpp
	../../../extern/icu/source/i18n/measure.cpp
	../../../extern/icu/source/i18n/msgfmt.cpp
	../../../extern/icu/source/i18n/name2uni.cpp
	../../../extern/icu/source/i18n/nfrs.cpp
	../../../extern/icu/source/i18n/nfrule.cpp
	../../../extern/icu/source/i18n/nfsubs.cpp
	../../../extern/icu/source/i18n/nortrans.cpp
	../../../extern/icu/source/i18n/nultrans.cpp
	../../../extern/icu/source/i18n/numfmt.cpp
	../../../extern/icu/source/i18n/olsontz.cpp
	../../../extern/icu/source/i18n/quant.cpp
	../../../extern/icu/source/i18n/rbnf.cpp
	../../../extern/icu/source/i18n/rbt.cpp
	../../../extern/icu/source/i18n/rbt_data.cpp
	../../../extern/icu/source/i18n/rbt_pars.cpp
	../../../extern/icu/source/i18n/rbt_rule.cpp
	../../../extern/icu/source/i18n/rbt_set.cpp
	../../../extern/icu/source/i18n/regexcmp.cpp
	../../../extern/icu/source/i18n/regexst.cpp
	../../../extern/icu/source/i18n/rematch.cpp
	../../../extern/icu/source/i18n/remtrans.cpp
	../../../extern/icu/source/i18n/repattrn.cpp
	../../../extern/icu/source/i18n/search.cpp
	../../../extern/icu/source/i18n/simpletz.cpp
	../../../extern/icu/source/i18n/smpdtfmt.cpp
	../../../extern/icu/source/i18n/sortkey.cpp
	../../../extern/icu/source/i18n/strmatch.cpp
	../../../extern/icu/source/i18n/strrepl.cpp
	../../../extern/icu/source/i18n/stsearch.cpp
	../../../extern/icu/source/i18n/tblcoll.cpp
	../../../extern/icu/source/i18n/timezone.cpp
	../../../extern/icu/source/i18n/titletrn.cpp
	../../../extern/icu/source/i18n/tolowtrn.cpp
	../../../extern/icu/source/i18n/toupptrn.cpp
	../../../extern/icu/source/i18n/translit.cpp
	../../../extern/icu/source/i18n/transreg.cpp
	../../../extern/icu/source/i18n/tridpars.cpp
	../../../extern/icu/source/i18n/ucal.cpp
	../../../extern/icu/source/i18n/ucln_in.c
	../../../extern/icu/source/i18n/ucol.cpp
	../../../extern/icu/source/i18n/ucol_bld.cpp
	../../../extern/icu/source/i18n/ucol_cnt.cpp
	../../../extern/icu/source/i18n/ucol_elm.cpp
	../../../extern/icu/source/i18n/ucol_sit.cpp
	../../../extern/icu/source/i18n/ucol_tok.cpp
	../../../extern/icu/source/i18n/ucol_wgt.c
	../../../extern/icu/source/i18n/ucoleitr.cpp
	../../../extern/icu/source/i18n/ucurr.cpp
	../../../extern/icu/source/i18n/udat.cpp
	../../../extern/icu/source/i18n/ulocdata.c
	../../../extern/icu/source/i18n/umsg.cpp
	../../../extern/icu/source/i18n/unesctrn.cpp
	../../../extern/icu/source/i18n/uni2name.cpp
	../../../extern/icu/source/i18n/unum.cpp
	../../../extern/icu/source/i18n/uregex.cpp
	../../../extern/icu/source/i18n/usearch.cpp
	../../../extern/icu/source/i18n/utrans.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/i18n/anytrans.h
	../../../extern/icu/source/i18n/astro.h
	../../../extern/icu/source/i18n/bocsu.h
	../../../extern/icu/source/i18n/buddhcal.h
	../../../extern/icu/source/i18n/chnsecal.h
	../../../extern/icu/source/i18n/cpdtrans.h
	../../../extern/icu/source/i18n/currfmt.h
	../../../extern/icu/source/i18n/digitlst.h
	../../../extern/icu/source/i18n/esctrn.h
	../../../extern/icu/source/i18n/funcrepl.h
	../../../extern/icu/source/i18n/gregoimp.h
	../../../extern/icu/source/i18n/hebrwcal.h
	../../../extern/icu/source/i18n/islamcal.h
	../../../extern/icu/source/i18n/japancal.h
	../../../extern/icu/source/i18n/name2uni.h
	../../../extern/icu/source/i18n/nfrlist.h
	../../../extern/icu/source/i18n/nfrs.h
	../../../extern/icu/source/i18n/nfrule.h
	../../../extern/icu/source/i18n/nfsubs.h
	../../../extern/icu/source/i18n/nortrans.h
	../../../extern/icu/source/i18n/nultrans.h
	../../../extern/icu/source/i18n/olsontz.h
	../../../extern/icu/source/i18n/quant.h
	../../../extern/icu/source/i18n/rbt.h
	../../../extern/icu/source/i18n/rbt_data.h
	../../../extern/icu/source/i18n/rbt_pars.h
	../../../extern/icu/source/i18n/rbt_rule.h
	../../../extern/icu/source/i18n/rbt_set.h
	../../../extern/icu/source/i18n/regexcmp.h
	../../../extern/icu/source/i18n/regexcst.h
	../../../extern/icu/source/i18n/regeximp.h
	../../../extern/icu/source/i18n/regexst.h
	../../../extern/icu/source/i18n/remtrans.h
	../../../extern/icu/source/i18n/strmatch.h
	../../../extern/icu/source/i18n/titletrn.h
	../../../extern/icu/source/i18n/tolowtrn.h
	../../../extern/icu/source/i18n/toupptrn.h
	../../../extern/icu/source/i18n/transreg.h
	../../../extern/icu/source/i18n/tridpars.h
	../../../extern/icu/source/i18n/ucln_in.h
	../../../extern/icu/source/i18n/ucol_bld.h
	../../../extern/icu/source/i18n/ucol_cnt.h
	../../../extern/icu/source/i18n/ucol_elm.h
	../../../extern/icu/source/i18n/ucol_imp.h
	../../../extern/icu/source/i18n/ucol_tok.h
	../../../extern/icu/source/i18n/ucol_wgt.h
	../../../extern/icu/source/i18n/ucurrimp.h
	../../../extern/icu/source/i18n/umsg_imp.h
	../../../extern/icu/source/i18n/unesctrn.h
	../../../extern/icu/source/i18n/uni2name.h
	../../../extern/icu/source/i18n/unicode/calendar.h
	../../../extern/icu/source/i18n/unicode/choicfmt.h
	../../../extern/icu/source/i18n/unicode/coleitr.h
	../../../extern/icu/source/i18n/unicode/coll.h
	../../../extern/icu/source/i18n/unicode/curramt.h
	../../../extern/icu/source/i18n/unicode/currunit.h
	../../../extern/icu/source/i18n/unicode/datefmt.h
	../../../extern/icu/source/i18n/unicode/dcfmtsym.h
	../../../extern/icu/source/i18n/unicode/decimfmt.h
	../../../extern/icu/source/i18n/unicode/dtfmtsym.h
	../../../extern/icu/source/i18n/unicode/fieldpos.h
	../../../extern/icu/source/i18n/unicode/fmtable.h
	../../../extern/icu/source/i18n/unicode/format.h
	../../../extern/icu/source/i18n/unicode/gregocal.h
	../../../extern/icu/source/i18n/unicode/measfmt.h
	../../../extern/icu/source/i18n/unicode/measunit.h
	../../../extern/icu/source/i18n/unicode/measure.h
	../../../extern/icu/source/i18n/unicode/msgfmt.h
	../../../extern/icu/source/i18n/unicode/numfmt.h
	../../../extern/icu/source/i18n/unicode/rbnf.h
	../../../extern/icu/source/i18n/unicode/regex.h
	../../../extern/icu/source/i18n/unicode/search.h
	../../../extern/icu/source/i18n/unicode/simpletz.h
	../../../extern/icu/source/i18n/unicode/smpdtfmt.h
	../../../extern/icu/source/i18n/unicode/sortkey.h
	../../../extern/icu/source/i18n/unicode/stsearch.h
	../../../extern/icu/source/i18n/unicode/tblcoll.h
	../../../extern/icu/source/i18n/unicode/timezone.h
	../../../extern/icu/source/i18n/unicode/translit.h
	../../../extern/icu/source/i18n/unicode/ucal.h
	../../../extern/icu/source/i18n/unicode/ucol.h
	../../../extern/icu/source/i18n/unicode/ucoleitr.h
	../../../extern/icu/source/i18n/unicode/ucurr.h
	../../../extern/icu/source/i18n/unicode/udat.h
	../../../extern/icu/source/i18n/unicode/ulocdata.h
	../../../extern/icu/source/i18n/unicode/umsg.h
	../../../extern/icu/source/i18n/unicode/unirepl.h
	../../../extern/icu/source/i18n/unicode/unum.h
	../../../extern/icu/source/i18n/unicode/uregex.h
	../../../extern/icu/source/i18n/unicode/usearch.h
	../../../extern/icu/source/i18n/unicode/utrans.h
	../../../extern/icu/source/i18n/usrchimp.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DU_I18N_IMPLEMENTATION
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} icuuc30)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	icuuc30
)

# common include files
SET (${this_target}_COPY_FILES
unicode/coleitr.h
unicode/coll.h
unicode/search.h
unicode/sortkey.h
unicode/stsearch.h
unicode/tblcoll.h
unicode/ucol.h
unicode/ucoleitr.h
unicode/usearch.h
unicode/calendar.h
unicode/choicfmt.h
unicode/curramt.h
unicode/currunit.h
unicode/datefmt.h
unicode/dcfmtsym.h
unicode/decimfmt.h
unicode/dtfmtsym.h
unicode/fieldpos.h
unicode/fmtable.h
unicode/format.h
unicode/gregocal.h
unicode/measfmt.h
unicode/measunit.h
unicode/measure.h
unicode/msgfmt.h
unicode/numfmt.h
unicode/rbnf.h
unicode/simpletz.h
unicode/smpdtfmt.h
unicode/timezone.h
unicode/ucal.h
unicode/ucurr.h
unicode/udat.h
unicode/ulocdata.h
unicode/umsg.h
unicode/unum.h
unicode/regex.h
unicode/uregex.h
unicode/translit.h
unicode/unirepl.h
unicode/utrans.h
)


FILE(MAKE_DIRECTORY ../../../../extern/icu/include/unicode)    

foreach(var ${${this_target}_COPY_FILES})
    FILE(COPY ../../../../extern/icu/source/i18n/${var} 
	DESTINATION ../../../extern/icu/include/unicode)
endforeach()


