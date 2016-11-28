# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace engine12 with binary name. e.g. mbase or FBase
SET (this_target engine12)
#PROJECT(${this_target})

##zws
#SET(OutputDirectory "..\..\..\temp\$(PlatformName)\$(ConfigurationName)\firebird\plugins\")


## section: include directory

INCLUDE_DIRECTORIES(
  ../../../src/include
	../../../src/include/gen
	../../../extern/icu/include
	../../../src/vulcan
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	DdlNodes.cpp
	metd.cpp
	PackageNodes.cpp
	dfw.cpp
	dpm.cpp
	dyn.cpp
	dyn_def.cpp
	dyn_del.cpp
	dyn_mod.cpp
	dyn_util.cpp
	fun.cpp
	Function.cpp
	grant.cpp
	ini.cpp
	met.cpp
	pcmet.cpp
	scl.cpp
	dba.cpp
	../../../src/dsql/AggNodes.cpp
	../../../src/dsql/BlrWriter.cpp
	../../../src/dsql/BoolNodes.cpp
	../../../src/dsql/ddl.cpp
	../../../src/dsql/DdlNodes.epp
	../../../src/dsql/dsql.cpp
	../../../src/dsql/DsqlCompilerScratch.cpp
	../../../src/dsql/DSqlDataTypeUtil.cpp
	../../../src/dsql/errd.cpp
	../../../src/dsql/ExprNodes.cpp
	../../../src/dsql/gen.cpp
	../../../src/dsql/make.cpp
	../../../src/dsql/metd.epp
	../../../src/dsql/movd.cpp
	../../../src/dsql/PackageNodes.epp
	../../../src/dsql/parse.cpp
	../../../src/dsql/parse.y
	../../../src/dsql/Parser.cpp
	../../../src/dsql/pass1.cpp
	../../../src/dsql/StmtNodes.cpp
	../../../src/dsql/utld.cpp
	../../../src/dsql/WinNodes.cpp
	../../../src/jrd/Attachment.cpp
	../../../src/jrd/blb.cpp
	../../../src/jrd/blob_filter.cpp
	../../../src/jrd/btn.cpp
	../../../src/jrd/btr.cpp
	../../../src/jrd/builtin.cpp
	../../../src/jrd/cch.cpp
	../../../src/jrd/cmp.cpp
	../../../src/jrd/Collation.cpp
	../../../src/jrd/cvt.cpp
	../../../src/jrd/cvt2.cpp
	../../../src/jrd/Database.cpp
	../../../src/jrd/DatabaseSnapshot.cpp
	../../../src/jrd/DataTypeUtil.cpp
	../../../src/jrd/DebugInterface.cpp
	../../../src/jrd/dfw.epp
	../../../src/jrd/dpm.epp
	../../../src/jrd/dyn.epp
	../../../src/jrd/dyn_def.epp
	../../../src/jrd/dyn_del.epp
	../../../src/jrd/dyn_mod.epp
	../../../src/jrd/dyn_util.epp
	../../../src/jrd/err.cpp
	../../../src/jrd/ErrorImpl.cpp
	../../../src/jrd/event.cpp
	../../../src/jrd/evl.cpp
	../../../src/jrd/exe.cpp
	../../../src/jrd/ext.cpp
	../../../src/jrd/extds/ExtDS.cpp
	../../../src/jrd/extds/InternalDS.cpp
	../../../src/jrd/extds/IscDS.cpp
	../../../src/jrd/ExtEngineManager.cpp
	../../../src/jrd/filters.cpp
	../../../src/jrd/flu.cpp
	../../../src/jrd/fun.epp
	../../../src/jrd/Function.epp
	../../../src/jrd/GlobalRWLock.cpp
	../../../src/jrd/grant.epp
	../../../src/jrd/idx.cpp
	../../../src/jrd/inf.cpp
	../../../src/jrd/ini.epp
	../../../src/jrd/intl.cpp
	../../../src/jrd/intl_builtin.cpp
	../../../src/jrd/IntlManager.cpp
	../../../src/jrd/jrd.cpp
	../../../src/jrd/JrdStatement.cpp
	../../../src/jrd/lck.cpp
	../../../src/jrd/met.epp
	../../../src/jrd/mov.cpp
	../../../src/jrd/nbak.cpp
	../../../src/jrd/nodebug.cpp
	../../../src/jrd/ods.cpp
	../../../src/jrd/opt.cpp
	../../../src/jrd/Optimizer.cpp
	../../../src/jrd/os/win32/ibinitdll.cpp
	../../../src/jrd/os/win32/thd_priority.cpp
	../../../src/jrd/os/win32/winnt.cpp
	../../../src/jrd/pag.cpp
	../../../src/jrd/par.cpp
	../../../src/jrd/pcmet.epp
	../../../src/jrd/PreparedStatement.cpp
	../../../src/jrd/RandomGenerator.cpp
	../../../src/jrd/RecordBuffer.cpp
	../../../src/jrd/RecordSourceNodes.cpp
	../../../src/jrd/recsrc/AggregatedStream.cpp
	../../../src/jrd/recsrc/BitmapTableScan.cpp
	../../../src/jrd/recsrc/BufferedStream.cpp
	../../../src/jrd/recsrc/ConditionalStream.cpp
	../../../src/jrd/recsrc/Cursor.cpp
	../../../src/jrd/recsrc/ExternalTableScan.cpp
	../../../src/jrd/recsrc/FilteredStream.cpp
	../../../src/jrd/recsrc/FirstRowsStream.cpp
	../../../src/jrd/recsrc/FullOuterJoin.cpp
	../../../src/jrd/recsrc/FullTableScan.cpp
	../../../src/jrd/recsrc/HashJoin.cpp
	../../../src/jrd/recsrc/IndexTableScan.cpp
	../../../src/jrd/recsrc/LockedStream.cpp
	../../../src/jrd/recsrc/MergeJoin.cpp
	../../../src/jrd/recsrc/NestedLoopJoin.cpp
	../../../src/jrd/recsrc/ProcedureScan.cpp
	../../../src/jrd/recsrc/RecordSource.cpp
	../../../src/jrd/recsrc/RecursiveStream.cpp
	../../../src/jrd/recsrc/SingularStream.cpp
	../../../src/jrd/recsrc/SkipRowsStream.cpp
	../../../src/jrd/recsrc/SortedStream.cpp
	../../../src/jrd/recsrc/Union.cpp
	../../../src/jrd/recsrc/VirtualTableScan.cpp
	../../../src/jrd/recsrc/WindowedStream.cpp
	../../../src/jrd/Relation.cpp
	../../../src/jrd/ResultSet.cpp
	../../../src/jrd/rlck.cpp
	../../../src/jrd/rpb_chain.cpp
	../../../src/jrd/RuntimeStatistics.cpp
	../../../src/jrd/scl.epp
	../../../src/jrd/sdw.cpp
	../../../src/jrd/shut.cpp
	../../../src/jrd/sort.cpp
	../../../src/jrd/sqz.cpp
	../../../src/jrd/status.cpp
	../../../src/jrd/svc.cpp
	../../../src/jrd/svc_tab.cpp
	../../../src/jrd/SysFunction.cpp
	../../../src/jrd/TempSpace.cpp
	../../../src/jrd/tpc.cpp
	../../../src/jrd/tra.cpp
	../../../src/jrd/trace/TraceCmdLine.cpp
	../../../src/jrd/trace/TraceConfigStorage.cpp
	../../../src/jrd/trace/TraceLog.cpp
	../../../src/jrd/trace/TraceManager.cpp
	../../../src/jrd/trace/TraceObjects.cpp
	../../../src/jrd/trace/TraceService.cpp
	../../../src/jrd/UserManagement.cpp
	../../../src/jrd/validation.cpp
	../../../src/jrd/ValueImpl.cpp
	../../../src/jrd/ValuesImpl.cpp
	../../../src/jrd/version.rc
	../../../src/jrd/vio.cpp
	../../../src/jrd/VirtualTable.cpp
	../../../src/lock/lock.cpp
	../../../src/utilities/gsec/gsec.cpp
	../../../src/utilities/gstat/dba.epp
	../../../src/utilities/gstat/ppg.cpp
	../../../src/utilities/nbackup/nbackup.cpp
	../defs/plugin.def
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/dsql/AggNodes.h
	../../../src/dsql/BlrWriter.h
	../../../src/dsql/BoolNodes.h
	../../../src/dsql/chars.h
	../../../src/dsql/ddl_proto.h
	../../../src/dsql/DdlNodes.h
	../../../src/dsql/dsql.h
	../../../src/dsql/dsql_proto.h
	../../../src/dsql/DsqlCompilerScratch.h
	../../../src/dsql/DSqlDataTypeUtil.h
	../../../src/dsql/errd_proto.h
	../../../src/dsql/ExprNodes.h
	../../../src/dsql/gen_proto.h
	../../../src/dsql/make_proto.h
	../../../src/dsql/metd_proto.h
	../../../src/dsql/movd_proto.h
	../../../src/dsql/node.h
	../../../src/dsql/Nodes.h
	../../../src/dsql/PackageNodes.h
	../../../src/dsql/Parser.h
	../../../src/dsql/pass1_proto.h
	../../../src/dsql/sqlda.h
	../../../src/dsql/sqlda_pub.h
	../../../src/dsql/StmtNodes.h
	../../../src/dsql/sym.h
	../../../src/dsql/utld_proto.h
	../../../src/dsql/Visitors.h
	../../../src/dsql/WinNodes.h
	../../../src/include/fb_api_proto.h
	../../../src/include/fb_blk.h
	../../../src/include/gen/codetext.h
	../../../src/include/gen/iberror.h
	../../../src/include/gen/ids.h
	../../../src/include/gen/msg_facs.h
	../../../src/include/gen/msgs.h
	../../../src/include/gen/sql_code.h
	../../../src/intl/kanji.h
	../../../src/intl/kanji_proto.h
	../../../src/jrd/acl.h
	../../../src/jrd/align.h
	../../../src/jrd/Attachment.h
	../../../src/jrd/blb.h
	../../../src/jrd/blb_proto.h
	../../../src/jrd/blf_proto.h
	../../../src/jrd/blob_filter.h
	../../../src/jrd/blp.h
	../../../src/jrd/blr.h
	../../../src/jrd/BlrReader.h
	../../../src/jrd/btn.h
	../../../src/jrd/btr.h
	../../../src/jrd/btr_proto.h
	../../../src/jrd/build_no.h
	../../../src/jrd/cch.h
	../../../src/jrd/cch_proto.h
	../../../src/jrd/cmp_proto.h
	../../../src/jrd/Collation.h
	../../../src/jrd/constants.h
	../../../src/jrd/cvt_proto.h
	../../../src/jrd/cvt2_proto.h
	../../../src/jrd/Database.h
	../../../src/jrd/DatabaseSnapshot.h
	../../../src/jrd/DataTypeUtil.h
	../../../src/jrd/DebugInterface.h
	../../../src/jrd/dflt.h
	../../../src/jrd/dfw_proto.h
	../../../src/jrd/dpm_proto.h
	../../../src/jrd/drq.h
	../../../src/jrd/dyn.h
	../../../src/jrd/dyn_df_proto.h
	../../../src/jrd/dyn_dl_proto.h
	../../../src/jrd/dyn_md_proto.h
	../../../src/jrd/dyn_proto.h
	../../../src/jrd/dyn_ut_proto.h
	../../../src/jrd/err_proto.h
	../../../src/jrd/ErrorImpl.h
	../../../src/jrd/event.h
	../../../src/jrd/event_proto.h
	../../../src/jrd/evl_proto.h
	../../../src/jrd/evl_string.h
	../../../src/jrd/exe.h
	../../../src/jrd/exe_proto.h
	../../../src/jrd/ext.h
	../../../src/jrd/ext_proto.h
	../../../src/jrd/extds/ExtDS.h
	../../../src/jrd/extds/InternalDS.h
	../../../src/jrd/extds/IscDS.h
	../../../src/jrd/ExtEngineManager.h
	../../../src/jrd/fields.h
	../../../src/jrd/filte_proto.h
	../../../src/jrd/flags.h
	../../../src/jrd/flu.h
	../../../src/jrd/flu_proto.h
	../../../src/jrd/fun_proto.h
	../../../src/jrd/Function.h
	../../../src/jrd/GlobalRWLock.h
	../../../src/jrd/grant_proto.h
	../../../src/jrd/ibase.h
	../../../src/jrd/ibsetjmp.h
	../../../src/jrd/idx.h
	../../../src/jrd/idx_proto.h
	../../../src/jrd/inf_proto.h
	../../../src/jrd/inf_pub.h
	../../../src/jrd/ini.h
	../../../src/jrd/ini_proto.h
	../../../src/jrd/intl.h
	../../../src/jrd/intl_classes.h
	../../../src/jrd/intl_proto.h
	../../../src/jrd/IntlManager.h
	../../../src/jrd/irq.h
	../../../src/jrd/isc_version.h
	../../../src/jrd/jrd.h
	../../../src/jrd/jrd_proto.h
	../../../src/jrd/JrdStatement.h
	../../../src/jrd/lck.h
	../../../src/jrd/lck_proto.h
	../../../src/jrd/license.h
	../../../src/jrd/lls.h
	../../../src/jrd/met.h
	../../../src/jrd/met_proto.h
	../../../src/jrd/mov_proto.h
	../../../src/jrd/msg.h
	../../../src/jrd/msg_encode.h
	../../../src/jrd/names.h
	../../../src/jrd/nbak.h
	../../../src/jrd/ntrace.h
	../../../src/jrd/obj.h
	../../../src/jrd/ods.h
	../../../src/jrd/ods_proto.h
	../../../src/jrd/opt_proto.h
	../../../src/jrd/Optimizer.h
	../../../src/jrd/os/pio.h
	../../../src/jrd/os/pio_proto.h
	../../../src/jrd/os/thd_priority.h
	../../../src/jrd/os/win32/win9x_nt.h
	../../../src/jrd/pag.h
	../../../src/jrd/pag_proto.h
	../../../src/jrd/par_proto.h
	../../../src/jrd/pcmet_proto.h
	../../../src/jrd/PreparedStatement.h
	../../../src/jrd/que.h
	../../../src/jrd/RandomGenerator.h
	../../../src/jrd/RecordBuffer.h
	../../../src/jrd/RecordNumber.h
	../../../src/jrd/RecordSourceNodes.h
	../../../src/jrd/recsrc/Cursor.h
	../../../src/jrd/recsrc/RecordSource.h
	../../../src/jrd/Relation.h
	../../../src/jrd/relations.h
	../../../src/jrd/req.h
	../../../src/jrd/ResultSet.h
	../../../src/jrd/rlck_proto.h
	../../../src/jrd/Routine.h
	../../../src/jrd/rpb_chain.h
	../../../src/jrd/rse.h
	../../../src/jrd/RuntimeStatistics.h
	../../../src/jrd/sbm.h
	../../../src/jrd/scl.h
	../../../src/jrd/scl_proto.h
	../../../src/jrd/sdw.h
	../../../src/jrd/sdw_proto.h
	../../../src/jrd/shut_proto.h
	../../../src/jrd/SimilarToMatcher.h
	../../../src/jrd/sort.h
	../../../src/jrd/sqz.h
	../../../src/jrd/status.h
	../../../src/jrd/svc.h
	../../../src/jrd/svc_tab.h
	../../../src/jrd/svc_undoc.h
	../../../src/jrd/SysFunction.h
	../../../src/jrd/TempSpace.h
	../../../src/jrd/thread_proto.h
	../../../src/jrd/tpc.h
	../../../src/jrd/tpc_proto.h
	../../../src/jrd/tra.h
	../../../src/jrd/tra_proto.h
	../../../src/jrd/trace/TraceConfigStorage.h
	../../../src/jrd/trace/TraceDSQLHelpers.h
	../../../src/jrd/trace/TraceJrdHelpers.h
	../../../src/jrd/trace/TraceLog.h
	../../../src/jrd/trace/TraceManager.h
	../../../src/jrd/trace/TraceObjects.h
	../../../src/jrd/trace/TraceService.h
	../../../src/jrd/trace/TraceSession.h
	../../../src/jrd/trace/traceswi.h
	../../../src/jrd/trig.h
	../../../src/jrd/types.h
	../../../src/jrd/UserManagement.h
	../../../src/jrd/val.h
	../../../src/jrd/val_proto.h
	../../../src/jrd/ValueImpl.h
	../../../src/jrd/ValuesImpl.h
	../../../src/jrd/vio_debug.h
	../../../src/jrd/vio_proto.h
	../../../src/jrd/VirtualTable.h
	../../../src/utilities/gsec/gsec.h
	../../../src/utilities/gsec/gsec_proto.h
	../../../src/utilities/gsec/gsecswi.h
	../../../src/utilities/gstat/dba_proto.h
	../../../src/utilities/gstat/dbaswi.h
	../../../src/utilities/gstat/ppg_proto.h
	../../../src/utilities/nbackup/nbk_proto.h
	../../../src/utilities/nbackup/nbkswi.h
	)

add_custom_command (
  OUTPUT 
	DdlNodes.cpp
	metd.cpp
	PackageNodes.cpp
	dfw.cpp
	dpm.cpp
	dyn.cpp
	dyn_def.cpp
	dyn_del.cpp
	dyn_mod.cpp
	dyn_util.cpp
	fun.cpp
	Function.cpp
	grant.cpp
	ini.cpp
	met.cpp
	pcmet.cpp
	scl.cpp
	dba.cpp
  COMMAND 
	@echo done by preprocess_boot
  COMMAND 
	@copy ..\\dsql\\*.* .
  COMMAND 
	@copy ..\\jrd\\*.* .
  COMMAND 
	@copy ..\\utilities\\gstat\\*.* .
)


SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_LIB -DSUPERSERVER -DNAMESPACE=Vulcan 
	)

#-D__MSVCRT_VERSION__=0x800 -D_WIN32_WINNT=0x0500

## section: add target
ADD_LIBRARY (${this_target} SHARED ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
ADD_DEPENDENCIES(${this_target} 
	mpr preprocess_boot parsinng
	common fbclient alice burp
	${CMAKE_BINARY_DIR}/icu/common
	${CMAKE_BINARY_DIR}/icu/stubdata
	${CMAKE_BINARY_DIR}/icu/i18n
)

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
	remote burp alice common fbclient mpr ws2_32 
	${CMAKE_BINARY_DIR}/icu/common/icuuc30.lib
	${CMAKE_BINARY_DIR}/icu/stubdata/icudt30.lib
	${CMAKE_BINARY_DIR}/icu/i18n/icuin30.lib
)

if(MINGW)
#TARGET_LINK_LIBRARIES( ${this_target} msvcr80)
endif(MINGW)
