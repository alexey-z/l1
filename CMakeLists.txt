cmake_minimum_required (VERSION 2.6)
project (helloworld)
set (Hello_VERSION_BUILD $ENV{TRAVIS_BUILD_NUMBER})

configure_file (
	"${PROJECT_SOURCE_DIR}/HelloConfig.h.in"
	"${PROJECT_BINARY_DIR}/HelloConfig.h"
)

SET(CPACK_GENERATOR "DEB")
SET(CPACK_DEBIAN_PACKAGE_MAINTAINER "Aleksei Zakharov")
SET(CPACK_PACKAGE_VERSION_MAJOR "1")
SET(CPACK_PACKAGE_VERSION_MINOR "0")
SET(CPACK_PACKAGE_VERSION_PATCH ${Hello_VERSION_BUILD})

add_executable(helloworld main.cxx)
INSTALL(TARGETS helloworld DESTINATION /usr/local/bin/)
INCLUDE(CPack)
