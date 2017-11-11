cmake_minimum_required(VERSION 3.1.0)

project (dicttoolkit)

# Use C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
message(STATUS "C++11 support has been enabled by default.")

# Creates and names a library, sets it as either STATIC
# or SHARED, and provides the relative paths to its source code.
# You can define multiple libraries, and CMake builds them for you.
# Gradle automatically packages shared libraries with your APK.

add_definitions(-Werror -Wall -Wextra -Weffc++ -Wformat=2 -Wcast-qual -Wcast-align
                -Wwrite-strings -Wfloat-equal -Wpointer-arith -Winit-self -Wredundant-decls
                -Woverloaded-virtual -Wsign-promo -Wno-system-headers -Wno-unused-parameter -Wno-unused-function)

include_directories(../jni/src src)
    
FILE(GLOB_RECURSE CC_FILES "src/*.cpp" "src/*.h")

FILE(GLOB_RECURSE JNI_DICT_FILES "../jni/src/*.cpp" "../jni/src/*.h")

FILE(GLOB JNI_CC_FILES "../jni/*.cpp" "../jni/*.h")

find_library( # Sets the name of the path variable.
              log-lib

              # Specifies the name of the NDK library that
              # you want CMake to locate.
              log )

add_executable( # Sets the name of the library.
                ${PROJECT_NAME}

                 # Provides a relative path to your source file(s).
                 ${CC_FILES} ${JNI_DICT_FILES} ${JNI_CC_FILES} dict_toolkit_main.cpp)

target_link_libraries( # Specifies the target library.
                       ${PROJECT_NAME}

                       # Links the target library to the log library
                       # included in the NDK.
                       ${log-lib})