cmake_minimum_required (VERSION 2.6)
project (Hello)
set (Hello_VERSION_BUILD 1)

configure_file (
	"${PROJECT_SOURCE_DIR}/HelloConfig.h.in"
	"${PROJECT_BINARY_DIR}/HelloConfig.h"
)
add_executable(Hello main.cxx)
