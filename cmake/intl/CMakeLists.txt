# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace intl with binary name. e.g. mbase or FBase
SET (this_target fbintl)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../src/include,../../../src/include/gen
  ../../../extern/icu/include
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/intl/cs_big5.cpp
	../../../src/intl/cs_gb2312.cpp
	../../../src/intl/cs_icu.cpp
	../../../src/intl/cs_jis.cpp
	../../../src/intl/cs_ksc.cpp
	../../../src/intl/cs_narrow.cpp
	../../../src/intl/cs_unicode_fss.cpp
	../../../src/intl/cs_unicode_ucs2.cpp
	../../../src/intl/cv_big5.cpp
	../../../src/intl/cv_gb2312.cpp
	../../../src/intl/cv_icu.cpp
	../../../src/intl/cv_jis.cpp
	../../../src/intl/cv_ksc.cpp
	../../../src/intl/cv_narrow.cpp
	../../../src/intl/cv_unicode_fss.cpp
	../../../src/intl/kanji.cpp
	../../../src/intl/lc_ascii.cpp
	../../../src/intl/lc_big5.cpp
	../../../src/intl/lc_dos.cpp
	../../../src/intl/lc_gb2312.cpp
	../../../src/intl/lc_icu.cpp
	../../../src/intl/lc_iso8859_1.cpp
	../../../src/intl/lc_iso8859_13.cpp
	../../../src/intl/lc_iso8859_2.cpp
	../../../src/intl/lc_jis.cpp
	../../../src/intl/lc_ksc.cpp
	../../../src/intl/lc_narrow.cpp
	../../../src/intl/lc_unicode_ucs2.cpp
	../../../src/intl/ld.cpp
	../../../src/jrd/version.rc
	../defs/intl.def
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/intl/charsets.h
	../../../src/intl/charsets/cs_437.h
	../../../src/intl/charsets/cs_737.h
	../../../src/intl/charsets/cs_775.h
	../../../src/intl/charsets/cs_850.h
	../../../src/intl/charsets/cs_852.h
	../../../src/intl/charsets/cs_857.h
	../../../src/intl/charsets/cs_858.h
	../../../src/intl/charsets/cs_860.h
	../../../src/intl/charsets/cs_861.h
	../../../src/intl/charsets/cs_862.h
	../../../src/intl/charsets/cs_863.h
	../../../src/intl/charsets/cs_864.h
	../../../src/intl/charsets/cs_865.h
	../../../src/intl/charsets/cs_866.h
	../../../src/intl/charsets/cs_869.h
	../../../src/intl/charsets/cs_big5.h
	../../../src/intl/charsets/cs_cyrl.h
	../../../src/intl/charsets/cs_gb2312.h
	../../../src/intl/charsets/cs_iso8859_1.h
	../../../src/intl/charsets/cs_iso8859_13.h
	../../../src/intl/charsets/cs_iso8859_2.h
	../../../src/intl/charsets/cs_iso8859_3.h
	../../../src/intl/charsets/cs_iso8859_4.h
	../../../src/intl/charsets/cs_iso8859_5.h
	../../../src/intl/charsets/cs_iso8859_6.h
	../../../src/intl/charsets/cs_iso8859_7.h
	../../../src/intl/charsets/cs_iso8859_8.h
	../../../src/intl/charsets/cs_iso8859_9.h
	../../../src/intl/charsets/cs_jis_0208_1990.h
	../../../src/intl/charsets/cs_koi8r.h
	../../../src/intl/charsets/cs_koi8u.h
	../../../src/intl/charsets/cs_ksc5601.h
	../../../src/intl/charsets/cs_next.h
	../../../src/intl/charsets/cs_sjis.h
	../../../src/intl/charsets/cs_w1250.h
	../../../src/intl/charsets/cs_w1251.h
	../../../src/intl/charsets/cs_w1252.h
	../../../src/intl/charsets/cs_w1253.h
	../../../src/intl/charsets/cs_w1254.h
	../../../src/intl/charsets/cs_w1255.h
	../../../src/intl/charsets/cs_w1256.h
	../../../src/intl/charsets/cs_w1257.h
	../../../src/intl/charsets/cs_w1258.h
	../../../src/intl/collations/bl88591ca0.h
	../../../src/intl/collations/bl88591da0.h
	../../../src/intl/collations/bl88591de0.h
	../../../src/intl/collations/bl88591es0.h
	../../../src/intl/collations/bl88591fi0.h
	../../../src/intl/collations/bl88591fr0.h
	../../../src/intl/collations/bl88591is0.h
	../../../src/intl/collations/bl88591it0.h
	../../../src/intl/collations/bl88591nl0.h
	../../../src/intl/collations/bl88591no0.h
	../../../src/intl/collations/bl88591pt0.h
	../../../src/intl/collations/bl88591ptbr0.h
	../../../src/intl/collations/bl88591sv0.h
	../../../src/intl/collations/bl88591uk0.h
	../../../src/intl/collations/bl88591us0.h
	../../../src/intl/collations/blNEXTde0.h
	../../../src/intl/collations/blNEXTes0.h
	../../../src/intl/collations/blNEXTfr0.h
	../../../src/intl/collations/blNEXTit0.h
	../../../src/intl/collations/blNEXTus0.h
	../../../src/intl/collations/db437de0.h
	../../../src/intl/collations/db437es1.h
	../../../src/intl/collations/db437fi0.h
	../../../src/intl/collations/db437fr0.h
	../../../src/intl/collations/db437it0.h
	../../../src/intl/collations/db437nl0.h
	../../../src/intl/collations/db437sv0.h
	../../../src/intl/collations/db437uk0.h
	../../../src/intl/collations/db437us0.h
	../../../src/intl/collations/db850cf0.h
	../../../src/intl/collations/db850de0.h
	../../../src/intl/collations/db850es0.h
	../../../src/intl/collations/db850fr0.h
	../../../src/intl/collations/db850it1.h
	../../../src/intl/collations/db850nl0.h
	../../../src/intl/collations/db850pt0.h
	../../../src/intl/collations/db850sv1.h
	../../../src/intl/collations/db850uk0.h
	../../../src/intl/collations/db850us0.h
	../../../src/intl/collations/db852cz0.h
	../../../src/intl/collations/db852po0.h
	../../../src/intl/collations/db852sl0.h
	../../../src/intl/collations/db857tr0.h
	../../../src/intl/collations/db860pt0.h
	../../../src/intl/collations/db863cf1.h
	../../../src/intl/collations/db865da0.h
	../../../src/intl/collations/db865no0.h
	../../../src/intl/collations/db866ru0.h
	../../../src/intl/collations/koi8r_ru.h
	../../../src/intl/collations/koi8u_ua.h
	../../../src/intl/collations/pd437intl.h
	../../../src/intl/collations/pd437swedfin.h
	../../../src/intl/collations/pd852czech.h
	../../../src/intl/collations/pd852hundc.h
	../../../src/intl/collations/pd852polish.h
	../../../src/intl/collations/pd852slovene.h
	../../../src/intl/collations/pd861iceland.h
	../../../src/intl/collations/pd865nordan40.h
	../../../src/intl/collations/pd866cyrr.h
	../../../src/intl/collations/pw1250czech.h
	../../../src/intl/collations/pw1250hun.h
	../../../src/intl/collations/pw1250hundc.h
	../../../src/intl/collations/pw1250polish.h
	../../../src/intl/collations/pw1250slov.h
	../../../src/intl/collations/pw1251cyrr.h
	../../../src/intl/collations/pw1252i850.h
	../../../src/intl/collations/pw1252intl.h
	../../../src/intl/collations/pw1252nor4.h
	../../../src/intl/collations/pw1252ptbr.h
	../../../src/intl/collations/pw1252span.h
	../../../src/intl/collations/pw1252swfn.h
	../../../src/intl/collations/pw1253greek1.h
	../../../src/intl/collations/pw1254turk.h
	../../../src/intl/collations/win_cz.h
	../../../src/intl/collations/win_cz_ci_ai.h
	../../../src/intl/collations/win1250bsba.h
	../../../src/intl/collations/win1257_ee.h
	../../../src/intl/collations/win1257_lt.h
	../../../src/intl/collations/win1257_lv.h
	../../../src/intl/collations/xx1251_ua.h
	../../../src/intl/collations/xx885913lt.h
	../../../src/intl/collations/xx88592czech.h
	../../../src/intl/collations/xx88592hun.h
	../../../src/intl/collations/xx88592plk.h
	../../../src/intl/conversions/tx437_865.h
	../../../src/intl/conversions/tx437_lat1.h
	../../../src/intl/conversions/tx865_lat1.h
	../../../src/intl/country_codes.h
	../../../src/intl/cs_icu.h
	../../../src/intl/cv_big5.h
	../../../src/intl/cv_gb2312.h
	../../../src/intl/cv_icu.h
	../../../src/intl/cv_jis.h
	../../../src/intl/cv_ksc.h
	../../../src/intl/cv_narrow.h
	../../../src/intl/cv_unicode_fss.h
	../../../src/intl/kanji.h
	../../../src/intl/kanji_proto.h
	../../../src/intl/lc_ascii.h
	../../../src/intl/lc_big5.h
	../../../src/intl/lc_dos.h
	../../../src/intl/lc_icu.h
	../../../src/intl/lc_narrow.h
	../../../src/intl/ld.h
	../../../src/intl/ld_proto.h
	../../../src/intl/ldcommon.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_USRDLL -DINTL_EXPORTS -DWINDOWS_ONLY -DSUPERCLIENT
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} comctl32 ws2_32 mpr version 
	common icuuc30 fbclient alice)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	comctl32 ws2_32 mpr version 
	common fbclient alice
	${CMAKE_BINARY_DIR}/icu/common/icuuc30.lib
)
