cmake_minimum_required(VERSION 3.4)

project(mathing VERSION 0.1 LANGUAGES CXX)
include(CTest)

# Create a library called mathing which includes the source files.
add_library(mathing
	src/matrix.cpp
	src/vector.cpp
	src/quaternion.cpp)

# Define headers for this library. PUBLIC headers are used for
# compiling the library, and will be added to consumers' build
# paths.
target_include_directories(mathing PUBLIC
	$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
	PUBLIC $<INSTALL_INTERFACE:include>
	PRIVATE src)

# If we have compiler requirements for this library, list them
# here:
# target_compile_features(mathing
#    PUBLIC cxx_auto_type
#    PRIVATE cxx_variadic_templates)

add_subdirectory(test)