# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace common with binary name. e.g. mbase or FBase
SET (this_target icuuc30)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/../include;../../../../extern/icu/source/tools/ctestfw;../../../../extern/icu/source/common;../../../../extern/icu/source/i18n;../../../../extern/icu/source/tools/toolutil
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/icu/source/common/brkdict.cpp
	../../../extern/icu/source/common/brkiter.cpp
	../../../extern/icu/source/common/caniter.cpp
	../../../extern/icu/source/common/chariter.cpp
	../../../extern/icu/source/common/cmemory.c
	../../../extern/icu/source/common/common.rc
	../../../extern/icu/source/common/cstring.c
	../../../extern/icu/source/common/cwchar.c
	../../../extern/icu/source/common/dbbi.cpp
	../../../extern/icu/source/common/dbbi_tbl.cpp
	../../../extern/icu/source/common/filestrm.c
	../../../extern/icu/source/common/iculserv.cpp
	../../../extern/icu/source/common/icunotif.cpp
	../../../extern/icu/source/common/icuserv.cpp
	../../../extern/icu/source/common/locbased.cpp
	../../../extern/icu/source/common/locid.cpp
	../../../extern/icu/source/common/locmap.c
	../../../extern/icu/source/common/normlzr.cpp
	../../../extern/icu/source/common/parsepos.cpp
	../../../extern/icu/source/common/propname.cpp
	../../../extern/icu/source/common/punycode.c
	../../../extern/icu/source/common/putil.c
	../../../extern/icu/source/common/rbbi.cpp
	../../../extern/icu/source/common/rbbidata.cpp
	../../../extern/icu/source/common/rbbinode.cpp
	../../../extern/icu/source/common/rbbirb.cpp
	../../../extern/icu/source/common/rbbiscan.cpp
	../../../extern/icu/source/common/rbbisetb.cpp
	../../../extern/icu/source/common/rbbistbl.cpp
	../../../extern/icu/source/common/rbbitblb.cpp
	../../../extern/icu/source/common/resbund.cpp
	../../../extern/icu/source/common/ruleiter.cpp
	../../../extern/icu/source/common/schriter.cpp
	../../../extern/icu/source/common/uarrsort.c
	../../../extern/icu/source/common/ubidi.c
	../../../extern/icu/source/common/ubidiln.c
	../../../extern/icu/source/common/ubidiwrt.c
	../../../extern/icu/source/common/ubrk.cpp
	../../../extern/icu/source/common/ucat.c
	../../../extern/icu/source/common/uchar.c
	../../../extern/icu/source/common/uchriter.cpp
	../../../extern/icu/source/common/ucln_cmn.c
	../../../extern/icu/source/common/ucmndata.c
	../../../extern/icu/source/common/ucmp8.c
	../../../extern/icu/source/common/ucnv.c
	../../../extern/icu/source/common/ucnv_bld.c
	../../../extern/icu/source/common/ucnv_cb.c
	../../../extern/icu/source/common/ucnv_cnv.c
	../../../extern/icu/source/common/ucnv_err.c
	../../../extern/icu/source/common/ucnv_ext.c
	../../../extern/icu/source/common/ucnv_io.c
	../../../extern/icu/source/common/ucnv_lmb.c
	../../../extern/icu/source/common/ucnv_u16.c
	../../../extern/icu/source/common/ucnv_u32.c
	../../../extern/icu/source/common/ucnv_u7.c
	../../../extern/icu/source/common/ucnv_u8.c
	../../../extern/icu/source/common/ucnv2022.c
	../../../extern/icu/source/common/ucnvbocu.c
	../../../extern/icu/source/common/ucnvhz.c
	../../../extern/icu/source/common/ucnvisci.c
	../../../extern/icu/source/common/ucnvlat1.c
	../../../extern/icu/source/common/ucnvmbcs.c
	../../../extern/icu/source/common/ucnvscsu.c
	../../../extern/icu/source/common/ucol_swp.c
	../../../extern/icu/source/common/udata.c
	../../../extern/icu/source/common/udatamem.c
	../../../extern/icu/source/common/udataswp.c
	../../../extern/icu/source/common/uenum.c
	../../../extern/icu/source/common/uhash.c
	../../../extern/icu/source/common/uhash_us.cpp
	../../../extern/icu/source/common/uidna.cpp
	../../../extern/icu/source/common/uiter.cpp
	../../../extern/icu/source/common/uloc.c
	../../../extern/icu/source/common/umapfile.c
	../../../extern/icu/source/common/umemstrm.c
	../../../extern/icu/source/common/umutex.c
	../../../extern/icu/source/common/unames.c
	../../../extern/icu/source/common/unifilt.cpp
	../../../extern/icu/source/common/unifunct.cpp
	../../../extern/icu/source/common/uniset.cpp
	../../../extern/icu/source/common/unistr.cpp
	../../../extern/icu/source/common/unorm.cpp
	../../../extern/icu/source/common/unorm_it.c
	../../../extern/icu/source/common/uobject.cpp
	../../../extern/icu/source/common/uprops.c
	../../../extern/icu/source/common/uresbund.c
	../../../extern/icu/source/common/uresdata.c
	../../../extern/icu/source/common/usc_impl.c
	../../../extern/icu/source/common/uscript.c
	../../../extern/icu/source/common/uset.cpp
	../../../extern/icu/source/common/usetiter.cpp
	../../../extern/icu/source/common/ushape.c
	../../../extern/icu/source/common/usprep.cpp
	../../../extern/icu/source/common/ustack.cpp
	../../../extern/icu/source/common/ustrcase.c
	../../../extern/icu/source/common/ustrenum.cpp
	../../../extern/icu/source/common/ustrfmt.c
	../../../extern/icu/source/common/ustring.c
	../../../extern/icu/source/common/ustrtrns.c
	../../../extern/icu/source/common/utf_impl.c
	../../../extern/icu/source/common/util.cpp
	../../../extern/icu/source/common/utrace.c
	../../../extern/icu/source/common/utrie.c
	../../../extern/icu/source/common/uvector.cpp
	../../../extern/icu/source/common/uvectr32.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/common/brkdict.h
	../../../extern/icu/source/common/charstr.h
	../../../extern/icu/source/common/cmemory.h
	../../../extern/icu/source/common/cpputils.h
	../../../extern/icu/source/common/cstring.h
	../../../extern/icu/source/common/cwchar.h
	../../../extern/icu/source/common/dbbi_tbl.h
	../../../extern/icu/source/common/filestrm.h
	../../../extern/icu/source/common/hash.h
	../../../extern/icu/source/common/iculserv.h
	../../../extern/icu/source/common/icunotif.h
	../../../extern/icu/source/common/icuserv.h
	../../../extern/icu/source/common/locbased.h
	../../../extern/icu/source/common/locmap.h
	../../../extern/icu/source/common/mutex.h
	../../../extern/icu/source/common/propname.h
	../../../extern/icu/source/common/punycode.h
	../../../extern/icu/source/common/rbbidata.h
	../../../extern/icu/source/common/rbbinode.h
	../../../extern/icu/source/common/rbbirb.h
	../../../extern/icu/source/common/rbbirpt.h
	../../../extern/icu/source/common/rbbiscan.h
	../../../extern/icu/source/common/rbbisetb.h
	../../../extern/icu/source/common/rbbitblb.h
	../../../extern/icu/source/common/ruleiter.h
	../../../extern/icu/source/common/sprpimpl.h
	../../../extern/icu/source/common/uarrsort.h
	../../../extern/icu/source/common/uassert.h
	../../../extern/icu/source/common/ubidiimp.h
	../../../extern/icu/source/common/ucln.h
	../../../extern/icu/source/common/ucln_cmn.h
	../../../extern/icu/source/common/ucmndata.h
	../../../extern/icu/source/common/ucmp8.h
	../../../extern/icu/source/common/ucnv_bld.h
	../../../extern/icu/source/common/ucnv_cnv.h
	../../../extern/icu/source/common/ucnv_ext.h
	../../../extern/icu/source/common/ucnv_imp.h
	../../../extern/icu/source/common/ucnv_io.h
	../../../extern/icu/source/common/ucnvmbcs.h
	../../../extern/icu/source/common/ucol_swp.h
	../../../extern/icu/source/common/udatamem.h
	../../../extern/icu/source/common/udataswp.h
	../../../extern/icu/source/common/uenumimp.h
	../../../extern/icu/source/common/uhash.h
	../../../extern/icu/source/common/ulocimp.h
	../../../extern/icu/source/common/umapfile.h
	../../../extern/icu/source/common/umemstrm.h
	../../../extern/icu/source/common/umutex.h
	../../../extern/icu/source/common/unicode/brkiter.h
	../../../extern/icu/source/common/unicode/caniter.h
	../../../extern/icu/source/common/unicode/chariter.h
	../../../extern/icu/source/common/unicode/dbbi.h
	../../../extern/icu/source/common/unicode/locid.h
	../../../extern/icu/source/common/unicode/normlzr.h
	../../../extern/icu/source/common/unicode/parseerr.h
	../../../extern/icu/source/common/unicode/parsepos.h
	../../../extern/icu/source/common/unicode/putil.h
	../../../extern/icu/source/common/unicode/pwin32.h
	../../../extern/icu/source/common/unicode/rbbi.h
	../../../extern/icu/source/common/unicode/rep.h
	../../../extern/icu/source/common/unicode/resbund.h
	../../../extern/icu/source/common/unicode/schriter.h
	../../../extern/icu/source/common/unicode/strenum.h
	../../../extern/icu/source/common/unicode/symtable.h
	../../../extern/icu/source/common/unicode/ubidi.h
	../../../extern/icu/source/common/unicode/ubrk.h
	../../../extern/icu/source/common/unicode/ucat.h
	../../../extern/icu/source/common/unicode/uchar.h
	../../../extern/icu/source/common/unicode/uchriter.h
	../../../extern/icu/source/common/unicode/uclean.h
	../../../extern/icu/source/common/unicode/ucnv.h
	../../../extern/icu/source/common/unicode/ucnv_cb.h
	../../../extern/icu/source/common/unicode/ucnv_err.h
	../../../extern/icu/source/common/unicode/uconfig.h
	../../../extern/icu/source/common/unicode/udata.h
	../../../extern/icu/source/common/unicode/udeprctd.h
	../../../extern/icu/source/common/unicode/udraft.h
	../../../extern/icu/source/common/unicode/uenum.h
	../../../extern/icu/source/common/unicode/uidna.h
	../../../extern/icu/source/common/unicode/uiter.h
	../../../extern/icu/source/common/unicode/uloc.h
	../../../extern/icu/source/common/unicode/umachine.h
	../../../extern/icu/source/common/unicode/umisc.h
	../../../extern/icu/source/common/unicode/unifilt.h
	../../../extern/icu/source/common/unicode/unifunct.h
	../../../extern/icu/source/common/unicode/unimatch.h
	../../../extern/icu/source/common/unicode/uniset.h
	../../../extern/icu/source/common/unicode/unistr.h
	../../../extern/icu/source/common/unicode/unorm.h
	../../../extern/icu/source/common/unicode/uobject.h
	../../../extern/icu/source/common/unicode/uobslete.h
	../../../extern/icu/source/common/unicode/urename.h
	../../../extern/icu/source/common/unicode/urep.h
	../../../extern/icu/source/common/unicode/ures.h
	../../../extern/icu/source/common/unicode/uscript.h
	../../../extern/icu/source/common/unicode/uset.h
	../../../extern/icu/source/common/unicode/usetiter.h
	../../../extern/icu/source/common/unicode/ushape.h
	../../../extern/icu/source/common/unicode/usprep.h
	../../../extern/icu/source/common/unicode/ustring.h
	../../../extern/icu/source/common/unicode/utf.h
	../../../extern/icu/source/common/unicode/utf_old.h
	../../../extern/icu/source/common/unicode/utf16.h
	../../../extern/icu/source/common/unicode/utf32.h
	../../../extern/icu/source/common/unicode/utf8.h
	../../../extern/icu/source/common/unicode/utrace.h
	../../../extern/icu/source/common/unicode/utypes.h
	../../../extern/icu/source/common/unicode/uversion.h
	../../../extern/icu/source/common/unorm_it.h
	../../../extern/icu/source/common/unormimp.h
	../../../extern/icu/source/common/uprops.h
	../../../extern/icu/source/common/uresdata.h
	../../../extern/icu/source/common/uresimp.h
	../../../extern/icu/source/common/usc_impl.h
	../../../extern/icu/source/common/ustr_imp.h
	../../../extern/icu/source/common/ustrenum.h
	../../../extern/icu/source/common/ustrfmt.h
	../../../extern/icu/source/common/util.h
	../../../extern/icu/source/common/utracimp.h
	../../../extern/icu/source/common/utrie.h
	../../../extern/icu/source/common/uvector.h
	../../../extern/icu/source/common/uvectr32.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DU_COMMON_IMPLEMENTATION
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} icudt30)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	icudt30
)

# common include files
SET (${this_target}_COPY_FILES
unicode/ubidi.h
unicode/ushape.h
unicode/brkiter.h
unicode/dbbi.h
unicode/rbbi.h
unicode/ubrk.h
unicode/strenum.h
unicode/uenum.h
unicode/putil.h
unicode/pwin32.h
unicode/uconfig.h
unicode/udeprctd.h
unicode/udraft.h
unicode/umachine.h
unicode/uobslete.h
unicode/urename.h
unicode/utrace.h
unicode/utypes.h
unicode/uversion.h
unicode/ucnv.h
unicode/ucnv_cb.h
unicode/ucnv_err.h
unicode/uclean.h
unicode/udata.h
unicode/uobject.h
unicode/parseerr.h
unicode/parsepos.h
unicode/umisc.h
unicode/uidna.h
unicode/resbund.h
unicode/ucat.h
unicode/uloc.h
unicode/ures.h
unicode/caniter.h
unicode/normlzr.h
unicode/unorm.h
unicode/symtable.h
unicode/uchar.h
unicode/unifilt.h
unicode/unifunct.h
unicode/unimatch.h
unicode/uniset.h
unicode/uscript.h
unicode/uset.h
unicode/usetiter.h
unicode/usprep.h
unicode/utrace.h
unicode/chariter.h
unicode/rep.h
unicode/schriter.h
unicode/uchriter.h
unicode/uiter.h
unicode/unistr.h
unicode/urep.h
unicode/ustring.h
unicode/utf.h
unicode/utf16.h
unicode/utf32.h
unicode/utf8.h
unicode/utf_old.h
)


FILE(MAKE_DIRECTORY ../../../../extern/icu/include/unicode)    

foreach(var ${${this_target}_COPY_FILES})
    FILE(COPY ../../../../extern/icu/source/common/${var} 
	DESTINATION ../../../extern/icu/include/unicode)
endforeach()


