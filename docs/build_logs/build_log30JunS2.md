- Date : 30 Jun 2026 (Session 2)
Duration : 2 Hours 30 mins
Goal():
continuation in Resolving the errors in gtest to check for the testcases using gtest.

Problem:
D:\googletest\build>cmake --system-information | findstr CMAKE_GENERATOR CMAKE_GENERATOR "Visual Studio 17 2022" CMAKE_GENERATOR_INSTANCE "C:/Program Files (x86)/Microsoft Visual Studio/2022/BuildTools" CMAKE_GENERATOR_NO_COMPILER_ENV "1" CMAKE_GENERATOR_PLATFORM "" CMAKE_GENERATOR_RC "rc" CMAKE_GENERATOR_TOOLSET "" CMAKE_GENERATOR:INTERNAL=MinGW Makefiles CMAKE_GENERATOR_INSTANCE:INTERNAL= CMAKE_GENERATOR_PLATFORM:INTERNAL= CMAKE_GENERATOR_TOOLSET:INTERNAL=

after running this it made clear that it was firslty been made my mingw and configured by visual studio due to which it get mixed or corrupted
Lets now move in Steps:

Step 1:
Delete the entire build floder in googletest

Step 2:Create new build folder
cd D:\googletest
mkdir build
cd build

Step 3:Visual studio code explicitly call krenge
cmake .. -G "Visual Studio 17 2022"

Step 4: Build 
cmake --build . --config Debug

Step 5: Ab check kre
dir /s *.lib

So succesfully we have completed the build google tesst 

Now moving to Cmake list
problem
target_link_directories(RedisLiteTests PRIVATE
    D:/googletest/build/lib
) 
I have written this earlier but the actual file is at
D:\googletest\build\lib\Debug\
    gtest.lib
    gtest_main.lib

After this completed 

Now we will be firslty deleteing the build folder which exists in the project folder and then we will again have some set of commands to run 
mkdir build
cd build

cmake .. -G "Visual Studio 17 2022" -A x64

cmake --build . --config Debug
This will rebuild fir the same cmakelists 
PS D:\GITN\PROJECT-01-SUPERCODERS\build> cmake --build . --config Debug
 MSBuild version 17.14.23+b0019275e for .NET Framework 
 1>Checking Build System Building Custom Rule D:/GITN/PROJECT-01-SUPERCODERS/CMakeLists.txt 
 main.cpp 
 Redislite.cpp 
 CLI.cpp
  CommandParser.cpp 
  Generating Code... 
  RedisLite.vcxproj -> 
  D:\GITN\PROJECT-01-SUPERCODERS\build\Debug\RedisLite.exe 
  Building Custom Rule D:/GITN/PROJECT-01-SUPERCODERS/CMakeLists.txt 
  test_append.cpp 
  test_assignment.cpp 
  test_capacity.cpp 
  test_constructor.cpp 
  test_coopy_constructor.cpp 
  test_empty.cpp 
  test_get.cpp 
  test_insert.cpp 
  test_operator_access.cpp 
  test_pop_back.cpp 
  test_remove.cpp 
  test_size.cpp
   Generating Code... 
   RedisLiteTests.vcxproj -> 
   D:\GITN\PROJECT-01-SUPERCODERS\build\Debug\RedisLiteTests.exe 
   Building Custom Rule D:/GITN/PROJECT-01-SUPERCODERS/CMakeLists.txt

Now we have completely resolved the error and now we will run the testcases.
