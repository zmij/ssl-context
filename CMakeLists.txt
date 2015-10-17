cmake_minimum_required(VERSION 2.8)
project(ssl-context)
set(PROJECT_VERSION 0.1)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(BOOST_COMPONENTS
        system
        thread
        filesystem
)

find_package(Boost COMPONENTS ${BOOST_COMPONENTS} REQUIRED)
find_package (Threads REQUIRED)
find_package(OpenSSL REQUIRED)

include_directories(${Boost_INCLUDE_DIRS} ${CMAKE_SOURCE_DIR}/src)
add_subdirectory(src/tip/ssl)
