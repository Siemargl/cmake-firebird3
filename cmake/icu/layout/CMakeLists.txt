# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace layout with binary name. e.g. mbase or FBase
SET (this_target layout)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
  ../../../../extern/icu/source/../include;
  ../../../../extern/icu/source/tools/ctestfw;
  ../../../../extern/icu/source/common;
  ../../../../extern/icu/source;
  ../../../../extern/icu/source/i18n;
  ../../../../extern/icu/source/tools/toolutil
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../extern/icu/source/layout/AlternateSubstSubtables.cpp
	../../../extern/icu/source/layout/AnchorTables.cpp
	../../../extern/icu/source/layout/ArabicLayoutEngine.cpp
	../../../extern/icu/source/layout/ArabicLigatureData.cpp
	../../../extern/icu/source/layout/ArabicShaping.cpp
	../../../extern/icu/source/layout/CanonData.cpp
	../../../extern/icu/source/layout/ClassDefinitionTables.cpp
	../../../extern/icu/source/layout/ContextualGlyphSubstProc.cpp
	../../../extern/icu/source/layout/ContextualSubstSubtables.cpp
	../../../extern/icu/source/layout/CoverageTables.cpp
	../../../extern/icu/source/layout/CursiveAttachmentSubtables.cpp
	../../../extern/icu/source/layout/DeviceTables.cpp
	../../../extern/icu/source/layout/ExtensionSubtables.cpp
	../../../extern/icu/source/layout/Features.cpp
	../../../extern/icu/source/layout/GDEFMarkFilter.cpp
	../../../extern/icu/source/layout/GlyphDefinitionTables.cpp
	../../../extern/icu/source/layout/GlyphIterator.cpp
	../../../extern/icu/source/layout/GlyphPositioningTables.cpp
	../../../extern/icu/source/layout/GlyphPosnLookupProc.cpp
	../../../extern/icu/source/layout/GlyphSubstitutionTables.cpp
	../../../extern/icu/source/layout/GlyphSubstLookupProc.cpp
	../../../extern/icu/source/layout/GXLayoutEngine.cpp
	../../../extern/icu/source/layout/HanLayoutEngine.cpp
	../../../extern/icu/source/layout/HebrewLigatureData.cpp
	../../../extern/icu/source/layout/HebrewShaping.cpp
	../../../extern/icu/source/layout/IndicClassTables.cpp
	../../../extern/icu/source/layout/IndicLayoutEngine.cpp
	../../../extern/icu/source/layout/IndicRearrangementProcessor.cpp
	../../../extern/icu/source/layout/IndicReordering.cpp
	../../../extern/icu/source/layout/layout.rc
	../../../extern/icu/source/layout/LayoutEngine.cpp
	../../../extern/icu/source/layout/LEFontInstance.cpp
	../../../extern/icu/source/layout/LEGlyphStorage.cpp
	../../../extern/icu/source/layout/LEInsertionList.cpp
	../../../extern/icu/source/layout/LigatureSubstProc.cpp
	../../../extern/icu/source/layout/LigatureSubstSubtables.cpp
	../../../extern/icu/source/layout/loengine.cpp
	../../../extern/icu/source/layout/LookupProcessor.cpp
	../../../extern/icu/source/layout/Lookups.cpp
	../../../extern/icu/source/layout/LookupTables.cpp
	../../../extern/icu/source/layout/MarkArrays.cpp
	../../../extern/icu/source/layout/MarkToBasePosnSubtables.cpp
	../../../extern/icu/source/layout/MarkToLigaturePosnSubtables.cpp
	../../../extern/icu/source/layout/MarkToMarkPosnSubtables.cpp
	../../../extern/icu/source/layout/MorphTables.cpp
	../../../extern/icu/source/layout/MPreFixups.cpp
	../../../extern/icu/source/layout/MultipleSubstSubtables.cpp
	../../../extern/icu/source/layout/NonContextualGlyphSubstProc.cpp
	../../../extern/icu/source/layout/OpenTypeLayoutEngine.cpp
	../../../extern/icu/source/layout/OpenTypeUtilities.cpp
	../../../extern/icu/source/layout/PairPositioningSubtables.cpp
	../../../extern/icu/source/layout/ScriptAndLanguage.cpp
	../../../extern/icu/source/layout/ScriptAndLanguageTags.cpp
	../../../extern/icu/source/layout/SegmentArrayProcessor.cpp
	../../../extern/icu/source/layout/SegmentSingleProcessor.cpp
	../../../extern/icu/source/layout/SimpleArrayProcessor.cpp
	../../../extern/icu/source/layout/SinglePositioningSubtables.cpp
	../../../extern/icu/source/layout/SingleSubstitutionSubtables.cpp
	../../../extern/icu/source/layout/SingleTableProcessor.cpp
	../../../extern/icu/source/layout/StateTableProcessor.cpp
	../../../extern/icu/source/layout/SubstitutionLookups.cpp
	../../../extern/icu/source/layout/SubtableProcessor.cpp
	../../../extern/icu/source/layout/ThaiLayoutEngine.cpp
	../../../extern/icu/source/layout/ThaiShaping.cpp
	../../../extern/icu/source/layout/ThaiStateTables.cpp
	../../../extern/icu/source/layout/TrimmedArrayProcessor.cpp
	../../../extern/icu/source/layout/ValueRecords.cpp
	../../../extern/icu/source/layout/GlyphLookupTables.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../extern/icu/source/layout/AlternateSubstSubtables.h
	../../../extern/icu/source/layout/AnchorTables.h
	../../../extern/icu/source/layout/ArabicLayoutEngine.h
	../../../extern/icu/source/layout/ArabicShaping.h
	../../../extern/icu/source/layout/AttachmentPosnSubtables.h
	../../../extern/icu/source/layout/CanonShaping.h
	../../../extern/icu/source/layout/CharSubstitutionFilter.h
	../../../extern/icu/source/layout/ClassDefinitionTables.h
	../../../extern/icu/source/layout/ContextualGlyphInsertion.h
	../../../extern/icu/source/layout/ContextualGlyphSubstitution.h
	../../../extern/icu/source/layout/ContextualGlyphSubstProc.h
	../../../extern/icu/source/layout/ContextualSubstSubtables.h
	../../../extern/icu/source/layout/CoverageTables.h
	../../../extern/icu/source/layout/CursiveAttachmentSubtables.h
	../../../extern/icu/source/layout/DefaultCharMapper.h
	../../../extern/icu/source/layout/DeviceTables.h
	../../../extern/icu/source/layout/ExtensionSubtables.h
	../../../extern/icu/source/layout/Features.h
	../../../extern/icu/source/layout/GDEFMarkFilter.h
	../../../extern/icu/source/layout/GlyphDefinitionTables.h
	../../../extern/icu/source/layout/GlyphIterator.h
	../../../extern/icu/source/layout/GlyphPositionAdjustments.h
	../../../extern/icu/source/layout/GlyphPositioningTables.h
	../../../extern/icu/source/layout/GlyphPosnLookupProc.h
	../../../extern/icu/source/layout/GlyphSubstitutionTables.h
	../../../extern/icu/source/layout/GlyphSubstLookupProc.h
	../../../extern/icu/source/layout/GXLayoutEngine.h
	../../../extern/icu/source/layout/HanLayoutEngine.h
	../../../extern/icu/source/layout/HebrewShaping.h
	../../../extern/icu/source/layout/HindiFeatureTags.h
	../../../extern/icu/source/layout/IndicLayoutEngine.h
	../../../extern/icu/source/layout/IndicRearrangement.h
	../../../extern/icu/source/layout/IndicRearrangementProcessor.h
	../../../extern/icu/source/layout/IndicReordering.h
	../../../extern/icu/source/layout/LayoutEngine.h
	../../../extern/icu/source/layout/LayoutTables.h
	../../../extern/icu/source/layout/LEFontInstance.h
	../../../extern/icu/source/layout/LEGlyphFilter.h
	../../../extern/icu/source/layout/LEGlyphStorage.h
	../../../extern/icu/source/layout/LEInsertionList.h
	../../../extern/icu/source/layout/LELanguages.h
	../../../extern/icu/source/layout/LEScripts.h
	../../../extern/icu/source/layout/LESwaps.h
	../../../extern/icu/source/layout/LETypes.h
	../../../extern/icu/source/layout/LigatureSubstitution.h
	../../../extern/icu/source/layout/LigatureSubstProc.h
	../../../extern/icu/source/layout/LigatureSubstSubtables.h
	../../../extern/icu/source/layout/LookupProcessor.h
	../../../extern/icu/source/layout/Lookups.h
	../../../extern/icu/source/layout/LookupTables.h
	../../../extern/icu/source/layout/MarkArrays.h
	../../../extern/icu/source/layout/MarkToBasePosnSubtables.h
	../../../extern/icu/source/layout/MarkToLigaturePosnSubtables.h
	../../../extern/icu/source/layout/MarkToMarkPosnSubtables.h
	../../../extern/icu/source/layout/MorphStateTables.h
	../../../extern/icu/source/layout/MorphTables.h
	../../../extern/icu/source/layout/MPreFixups.h
	../../../extern/icu/source/layout/MultipleSubstSubtables.h
	../../../extern/icu/source/layout/NonContextualGlyphSubst.h
	../../../extern/icu/source/layout/NonContextualGlyphSubstProc.h
	../../../extern/icu/source/layout/OpenTypeLayoutEngine.h
	../../../extern/icu/source/layout/OpenTypeTables.h
	../../../extern/icu/source/layout/OpenTypeUtilities.h
	../../../extern/icu/source/layout/PairPositioningSubtables.h
	../../../extern/icu/source/layout/ScriptAndLanguage.h
	../../../extern/icu/source/layout/ScriptAndLanguageTags.h
	../../../extern/icu/source/layout/SegmentArrayProcessor.h
	../../../extern/icu/source/layout/SegmentSingleProcessor.h
	../../../extern/icu/source/layout/SimpleArrayProcessor.h
	../../../extern/icu/source/layout/SinglePositioningSubtables.h
	../../../extern/icu/source/layout/SingleSubstitutionSubtables.h
	../../../extern/icu/source/layout/SingleTableProcessor.h
	../../../extern/icu/source/layout/StateTableProcessor.h
	../../../extern/icu/source/layout/StateTables.h
	../../../extern/icu/source/layout/SubstitutionLookups.h
	../../../extern/icu/source/layout/SubtableProcessor.h
	../../../extern/icu/source/layout/ThaiLayoutEngine.h
	../../../extern/icu/source/layout/ThaiShaping.h
	../../../extern/icu/source/layout/TrimmedArrayProcessor.h
	../../../extern/icu/source/layout/unicode/loengine.h
	../../../extern/icu/source/layout/ValueRecords.h
	../../../extern/icu/source/layout/GlyphLookupTables.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-DU_LAYOUT_IMPLEMENTATION
	)

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} icuuc30 icuin30 icudt30 icutu30)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	icuuc30 icuin30 icudt30 icutu30
		)
