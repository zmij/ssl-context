#	CMakeLists.txt
#	
#	@author zmij
#	@date Aug 21, 2015

cmake_minimum_required(VERSION 2.6)

set(
    tip_ssl_SRCS
    ssl_context_service.cpp
)
set(
        tip_ssl_HDRS
        ssl_context_service.hpp
)

add_library(tip-ssl SHARED ${tip_ssl_SRCS} ${tip_ssl_HDRS})

set_target_properties(
    tip-ssl 
    PROPERTIES
    VERSION ${PROJECT_VERSION}
    SOVERSION 0
)

target_link_libraries(
    tip-ssl 
    ${Boost_SYSTEM_LIBRARIES}
    ${Boost_FILESYSTEM_LIBRARIES}
    ${OPENSSL_LIBRARIES}
)

install (
    TARGETS tip-ssl
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)
