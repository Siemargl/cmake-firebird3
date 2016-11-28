This Cmake build created for work using only command line tools

Can use MSVC .NET 2003 or higher, MingGW 4.5.0

It's now generates not all of firebird 3.0, but almost all (binaries and data)
To end this, see end of this file
Cheers =),  Siemargl
23-03-2011

30-03-2011 updated MinGW support and readme


General use:
0. Put all this file in firebird3/builds/cmake
1. Install Cmake for windows (adding in path not required)
2. Run Visual C++ command prompt, if global environment var not point to vc 
--- building ICU libs ---
3. Create firebird3\gen\icu directory and go in
4. Run 
	>Cmake ..\..\builds\cmake\icu -G "NMake Makefiles"
   (or use cmake-gui 
	source-dir=firebird3/builds/cmake 
	binaries-dir=firebird3/gen/icu
	generate + configure)
5. Run 
	>nmake
   wait (about 2 minutes) ending message "Test data is built. All targets are up to date"
6. Here we have built ICU libs. After copying they, no rebuild with ICU needed
--- building first stage firebird databases and binaries ---
7. Go in firebird3\gen and run 
	>Cmake ..\builds\cmake -G "NMake Makefiles" -DBOOT=Y
	>nmake
   wait (about 5 minutes) for "[100%] Built"
(sometimes FireBird server crashes on "Creating databases...", but after his work done - ignore this)
6. Here we have base binaries and files. This operation run once.
--- regular build, change FB code etc ---
7. Genegate basic makefile:
	>del cmakecache.txt  (or remove variable BOOT from it) 	
	>Cmake ..\builds\cmake -G "NMake Makefiles" 
7. Every time you change code, run	
	>nmake

8. Remember copy MSVCRT and MSVCP appropriate versions to Firebird bin directory


---------------------------------------------------------------------
Using free command line compiler
1. Install Visual Studio .NET 2003 Tools
2. Install MS Windows SDK 
(you may need to modify changing "_VARIANT_BOOL bool" to "_VARIANT_BOOL _bool"
in propidl.h && oaidl.h)
3. Add SDK path, include and lib in vcvars.bat
3. Add lib.exe && nmake.exe to VC2003 bin directory
4. Slightly modify FireBird source code (see msvc2003_modified dir)

May also use MinGW, but it's very slow, don't support SEH (need check), 
and requries change more source code and defines to compile FB3

---------------------------------------------------------------------
I've used vcproj2cmake.ps1  for semi-automatically converting VS8 projects
If it runs with errors, just see ang manual change in resulting cmakefiles.txt:
-SET(${this_target}_HEADER_FILES    - usually remove <include>
-ADD_DEPENDENCIES(${this_target} )  - usually comment

---------------------------------------------------------------------
MinGW 
Compiler defines you may see in main Cmakefiles.txt in section IF(MINGW).
Base test was done for version 4.5.0 - seems to work.

In near future may be inpossible build without msvcr80|90. Then you get in
manifest problem - mingw linker incorrectly bind manifest to DLL - use MS mt.exe

Gprof'ed build won't run.

MinGW ICU building notes
-need adding somewhere <stdint.h> (uint64)
-copy manually to firebird3\extern\icu\win\release\bin dll's
 libicudt30.dll libicuin30.dll libicuio30.dll libicutu30.dll libicuuc30.dll 
-for generating data you need MS nmake, link + mspdb71.dll 
-after run you get firebird3\extern\icu\win\release\bin\icudt30.dll - 
 rename it to libicudt30.dll

---------------------------------------------------------------------
todo's
a)finish compile all units - see end of main cmakefile.txt
b)Create and check release/debug/profiler (Cmake have some automatic)
c)Create and check ix32/amd64 (Cmake have some automatic)
d)Remove, if need, dependency from makefiles in ICU build
e)Remove, if need, dependency from create_msgs.bat è preprocess.bat
f)Finish building examples and installer
g)Check or add VS manifest files creation and linking

