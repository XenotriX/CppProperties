cmake_minimum_required(VERSION 3.17)

project(
    cppproperties
    VERSION 0.1.0
    LANGUAGES CXX
    HOMEPAGE_URL "https://github.com/text/cppproperties"
)


option(BUILD_EXAMPLES "Whether to build examples" ON)

# Include examples (if supposed to)
if (BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()

# Add the actual library
add_subdirectory(lib)


################################################################################
# CPack                                                                        #
################################################################################
set(CPACK_PACKAGE_VENDOR "Joel Bodenmann")
set(CPACK_PACKAGE_DESCRIPTION_SUMMARY "A library to bring a property system to modern C++.")
set(CPACK_PACKAGE_VERSION_MAJOR ${PROJECT_VERSION_MAJOR})
set(CPACK_PACKAGE_VERSION_MINOR ${PROJECT_VERSION_MINOR})
set(CPACK_PACKAGE_VERSION_PATCH ${PROJECT_VERSION_PATCH})
set(CPACK_RESOURCE_FILE_LICENSE "${CMAKE_CURRENT_SOURCE_DIR}/LICENSE")
set(CPACK_RESOURCE_FILE_README "${CMAKE_CURRENT_SOURCE_DIR}/readme.md")
include(CPack)
