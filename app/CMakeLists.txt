# For more information about using CMake with Android Studio, read the
# documentation: https://d.android.com/studio/projects/add-native-code.html

# Sets the minimum version of CMake required to build the native library.

cmake_minimum_required(VERSION 3.4.1)

# Use C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
message(STATUS "C++11 support has been enabled by default.")

set_property(GLOBAL PROPERTY USE_FOLDERS ON) # We folder to separate targets

# Make sure all projects can access each other.
include_directories("../LatinIME/native")

add_subdirectory("../LatinIME/native/dicttoolkit" "LatinIME/native/dicttoolkit")
add_subdirectory("../LatinIME/native/jni" "LatinIME/native/jni")