cmake_minimum_required(VERSION 3.12.0)
project(plv VERSION 0.0.1)

include(CTest)

message(STATUS "Build Type: ${CMAKE_BUILD_TYPE}")
message(STATUS "CMAKE Generator: ${CMAKE_GENERATOR}")
message(STATUS "CMake ProjSourceDir: ${PROJECT_SOURCE_DIR}")

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/build/x64/)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/build/x64/)

if (NOT MSVC)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wpedantic -Wextra -Wno-unused-function -Wno-unused-parameter")
endif()

add_subdirectory(deps/pll)
add_executable(plv "src/main.cpp")

target_link_libraries(plv pll)
target_include_directories(plv PUBLIC ${PROJECT_SOURCE_DIR}/deps/pll/include)

set_target_properties(plv PROPERTIES
	CXX_STANDARD 17
	CXX_STANDARD_REQUIRED ON
	CXX_EXTENSIONS OFF
)
