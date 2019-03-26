cmake_minimum_required (VERSION 2.6)
project (Hello)
set (Hello_VERSION_BUILD $ENV{TRAVIS_BUILD_NUMBER})

configure_file (
	"${PROJECT_SOURCE_DIR}/HelloConfig.h.in"
	"${PROJECT_BINARY_DIR}/HelloConfig.h"
)
add_executable(helloworld main.cxx)
