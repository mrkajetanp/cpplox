cmake_minimum_required(VERSION 3.10)

project(cpplox)

set(TARGET_NAME cpplox)

set(CMAKE_C_COMPILER clang)
set(CMAKE_CXX_COMPILER clang++)
set(CMAKE_EXPORT_COMPILE_COMMANDS 1)

find_path(TCLAP_INCLUDE_DIRS "tclap/Arg.h")

add_executable(${TARGET_NAME} src/main.cpp)

target_compile_features(${TARGET_NAME} PUBLIC cxx_std_23)

target_include_directories(${TARGET_NAME} PRIVATE ${TCLAP_INCLUDE_DIRS})
