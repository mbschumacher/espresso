set(Scafacos_SRC
    Scafacos.cpp
)
add_library(Scafacos SHARED ${Scafacos_SRC})
if (${SCAFACOS_INCLUDE_DIRS})
    target_include_directories(Scafacos ${SCAFACOS_INCLUDE_DIRS})
endif()
install(TARGETS Scafacos DESTINATION ${PYTHON_INSTDIR}/espressomd)
add_dependencies(Scafacos EspressoConfig)
target_include_directories(Scafacos PRIVATE ${CMAKE_SOURCE_DIR}/src/core ${CMAKE_BINARY_DIR}/src/core)
target_link_libraries(Scafacos ${SCAFACOS_LDFLAGS})
