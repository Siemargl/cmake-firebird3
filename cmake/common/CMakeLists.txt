# -*- cmake -*-
# written by Darren Ha(darren.ha@samsung.com)

# replace common with binary name. e.g. mbase or FBase
SET (this_target common)
#PROJECT(${this_target})

## section: include directory

INCLUDE_DIRECTORIES(
	../../../src/include
	../../../src/include/gen
  	../../../extern/icu/include
  )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
	../../../src/common/Auth.cpp
	../../../src/common/call_service.cpp
	../../../src/common/CharSet.cpp
	../../../src/common/classes/alloc.cpp
	../../../src/common/classes/BaseStream.cpp
	../../../src/common/classes/ClumpletReader.cpp
	../../../src/common/classes/ClumpletWriter.cpp
	../../../src/common/classes/DbImplementation.cpp
	../../../src/common/classes/fb_string.cpp
	../../../src/common/classes/init.cpp
	../../../src/common/classes/locks.cpp
	../../../src/common/classes/MetaName.cpp
	../../../src/common/classes/MsgPrint.cpp
	../../../src/common/classes/PublicHandle.cpp
	../../../src/common/classes/SafeArg.cpp
	../../../src/common/classes/semaphore.cpp
	../../../src/common/classes/Switches.cpp
	../../../src/common/classes/TempFile.cpp
	../../../src/common/classes/timestamp.cpp
	../../../src/common/classes/UserBlob.cpp
	../../../src/common/config/config.cpp
	../../../src/common/config/config_file.cpp
	../../../src/common/config/ConfigCache.cpp
	../../../src/common/config/dir_list.cpp
	../../../src/common/config/os/win32/config_root.cpp
	../../../src/common/cvt.cpp
	../../../src/common/db_alias.cpp
	../../../src/common/dllinst.cpp
	../../../src/common/dsc.cpp
	../../../src/common/enc.cpp
	../../../src/common/fb_exception.cpp
	../../../src/common/IntlUtil.cpp
	../../../src/common/isc.cpp
	../../../src/common/isc_file.cpp
	../../../src/common/isc_sync.cpp
	../../../src/common/os/win32/fbsyslog.cpp
	../../../src/common/os/win32/guid.cpp
	../../../src/common/os/win32/isc_ipc.cpp
	../../../src/common/os/win32/mod_loader.cpp
	../../../src/common/os/win32/os_utils.cpp
	../../../src/common/os/win32/path_utils.cpp
	../../../src/common/pretty.cpp
	../../../src/common/quad.cpp
	../../../src/common/ScanDir.cpp
	../../../src/common/sdl.cpp
	../../../src/common/security.cpp
	../../../src/common/sha.cpp
	../../../src/common/StatusArg.cpp
	../../../src/common/StatusHolder.cpp
	../../../src/common/TextType.cpp
	../../../src/common/thd.cpp
	../../../src/common/ThreadData.cpp
	../../../src/common/ThreadStart.cpp
	../../../src/common/unicode_util.cpp
	../../../src/common/utils.cpp
	../../../src/common/UtilSvc.cpp
	../../../src/common/xdr.cpp
	)

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
	../../../src/common/Auth.h
	../../../src/common/call_service.h
	../../../src/common/cdbtable.h
	../../../src/common/CharSet.h
	../../../src/common/classes/Aligner.h
	../../../src/common/classes/alloc.h
	../../../src/common/classes/array.h
	../../../src/common/classes/auto.h
	../../../src/common/classes/BaseStream.h
	../../../src/common/classes/ByteChunk.h
	../../../src/common/classes/ClumpletReader.h
	../../../src/common/classes/ClumpletWriter.h
	../../../src/common/classes/condition.h
	../../../src/common/classes/DbImplementation.h
	../../../src/common/classes/fb_atomic.h
	../../../src/common/classes/fb_pair.h
	../../../src/common/classes/fb_string.h
	../../../src/common/classes/fb_tls.h
	../../../src/common/classes/File.h
	../../../src/common/classes/FpeControl.h
	../../../src/common/classes/GenericMap.h
	../../../src/common/classes/Hash.h
	../../../src/common/classes/ImplementHelper.h
	../../../src/common/classes/init.h
#	../../../src/common/classes/Interface.h
	../../../src/common/classes/Interlock.h
	../../../src/common/classes/locks.h
	../../../src/common/classes/MetaName.h
	../../../src/common/classes/MsgPrint.h
	../../../src/common/classes/NestConst.h
	../../../src/common/classes/Nullable.h
	../../../src/common/classes/objects_array.h
	../../../src/common/classes/PublicHandle.h
	../../../src/common/classes/QualifiedName.h
	../../../src/common/classes/RefCounted.h
	../../../src/common/classes/RefMutex.h
	../../../src/common/classes/rwlock.h
	../../../src/common/classes/SafeArg.h
	../../../src/common/classes/semaphore.h
	../../../src/common/classes/sparse_bitmap.h
	../../../src/common/classes/stack.h
	../../../src/common/classes/Switches.h
	../../../src/common/classes/TempFile.h
	../../../src/common/classes/timestamp.h
	../../../src/common/classes/tree.h
	../../../src/common/classes/TriState.h
	../../../src/common/classes/UserBlob.h
	../../../src/common/classes/VaryStr.h
	../../../src/common/classes/vector.h
	../../../src/common/common.h
	../../../src/common/config/config.h
	../../../src/common/config/config_file.h
	../../../src/common/config/ConfigCache.h
	../../../src/common/config/dir_list.h
	../../../src/common/config/os/config_root.h
	../../../src/common/CsConvert.h
	../../../src/common/cvt.h
	../../../src/common/db_alias.h
	../../../src/common/dllinst.h
	../../../src/common/dsc.h
	../../../src/common/dsc_proto.h
	../../../src/common/dsc_pub.h
	../../../src/common/dyntable.h
	../../../src/common/enc_proto.h
	../../../src/common/file_params.h
	../../../src/common/gdsassert.h
	../../../src/common/intlobj_new.h
	../../../src/common/IntlUtil.h
	../../../src/common/isc_f_proto.h
	../../../src/common/isc_proto.h
	../../../src/common/isc_s_proto.h
	../../../src/common/os/divorce.h
	../../../src/common/os/fbsyslog.h
	../../../src/common/os/guid.h
	../../../src/common/os/isc_i_proto.h
	../../../src/common/os/mod_loader.h
	../../../src/common/os/os_utils.h
	../../../src/common/os/path_utils.h
	../../../src/common/prett_proto.h
	../../../src/common/quad.h
	../../../src/common/quad_proto.h
	../../../src/common/ScanDir.h
	../../../src/common/sdl.h
	../../../src/common/sdl_proto.h
	../../../src/common/sdltable.h
	../../../src/common/security.h
	../../../src/common/sha.h
	../../../src/common/StatusArg.h
	../../../src/common/StatusHolder.h
	../../../src/common/stuff.h
	../../../src/common/TextType.h
	../../../src/common/thd.h
	../../../src/common/ThreadData.h
	../../../src/common/ThreadStart.h
	../../../src/common/unicode_util.h
	../../../src/common/utils_proto.h
	../../../src/common/UtilSvc.h
	../../../src/common/xdr.h
	../../../src/common/xdr_proto.h
	)

SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})

## section: add definitions
# 	add prefix -D. example> -DSHP
#  - DO NOT add  the following definitions(already defined in ${OSP_DEFINITIONS}:
# 	-DSHP, -DWIN32, -D_WINDOWS, -D_DEBUG, -D_USRDLL, -D_CRT_SECURE_NO_DEPRECATE
ADD_DEFINITIONS(
	-D_LIB -DSUPERSERVER
	)

## section: add target
ADD_LIBRARY (${this_target} STATIC ${${this_target}_SOURCE_FILES} )

## section: add dependency
# dependency determines overall build order.
#ADD_DEPENDENCIES(${this_target} )

## section: set link libraries
TARGET_LINK_LIBRARIES( ${this_target}
		)

