add_executable(ptxinfo ptxinfo.cpp)
add_definitions(-DPTEX_VER="${PTEX_VER} \(${PTEX_SHA}\)")
if (PTEX_BUILD_STATIC_LIBS)
    add_definitions(-DPTEX_STATIC)
endif()

if (PTEX_BUILD_STATIC_LIBS)
    target_link_libraries(ptxinfo ${PTEX_LIBRARY} ${ZLIB_LIBRARIES})
else()
    target_link_libraries(ptxinfo ${PTEX_LIBRARY})
endif()

install(TARGETS ptxinfo DESTINATION ${CMAKE_INSTALL_BINDIR})
