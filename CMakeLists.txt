cmake_minimum_required(VERSION 3.15)
project(cmakeTest)

add_executable(main main.cpp SimpleIndex.cpp)

find_package(libOTe REQUIRED HINTS ../libOTe)  # You may need to modify the path here.

set(CMAKE_BUILD_TYPE Release)
# set(CMAKE_BUILD_TYPE DEBUG)

target_compile_options(main PUBLIC $<$<COMPILE_LANGUAGE:CXX>:-std=c++17> -lpthread)

# target_link_libraries(main oc::libOTe)

target_link_libraries(main oc::libOTe)

# set any other operties like cpp version