# CONFIGURE_DEPENDS requires 3.12
cmake_minimum_required(VERSION 3.12)
project(alien VERSION 1.0.0)
add_executable(alien)
find_package(log4cpp CONFIG)

file(GLOB_RECURSE sources CONFIGURE_DEPENDS *[!.test].cpp)

target_sources(alien PRIVATE ${sources})
target_link_libraries(alien
    PRIVATE log4cpp::log4cpp)

install(TARGETS alien)
include(CPack)
