cmake_minimum_required (VERSION 2.6)
project (helloworld)
set (Hello_VERSION_BUILD $ENV{TRAVIS_BUILD_NUMBER})

configure_file (
	"${PROJECT_SOURCE_DIR}/HelloConfig.h.in"
	"${PROJECT_BINARY_DIR}/HelloConfig.h"
)

SET(CPACK_GENERATOR "DEB")
SET(CPACK_DEBIAN_PACKAGE_MAINTAINER "Aleksei Zakharov")

add_executable(helloworld main.cxx)
INSTALL(TARGETS helloworld DESTINATION /usr/local/bin/)
INCLUDE(CPack)
