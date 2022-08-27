cmake_minimum_required(VERSION 3.0.0)

set(PROJECT_NAME rnnoise)

project(${PROJECT_NAME})

set(SOURCES
  rnnoise/src/denoise.c
  rnnoise/src/rnn.c
  rnnoise/src/rnn_data.c
  rnnoise/src/rnn_reader.c
  rnnoise/src/pitch.c
  rnnoise/src/kiss_fft.c
  rnnoise/src/celt_lpc.c
  )

set(HEADERS
  rnnoise/include/rnnoise.h
  )

include_directories(
  rnnoise/include
  )

if(WIN32)
  add_definitions(
    "-D_USE_MATH_DEFINES"
    )
endif()

add_library(${PROJECT_NAME} STATIC
  ${SOURCES}
  )

set_target_properties(${PROJECT_NAME} PROPERTIES
  PUBLIC_HEADER "${HEADERS}"
  )

if("${CMAKE_INSTALL_INCLUDEDIR}" STREQUAL "")
  set(CMAKE_INSTALL_INCLUDEDIR ${CMAKE_INSTALL_PREFIX}/include)
endif()

if("${CMAKE_INSTALL_LIBDIR}" STREQUAL "")
  set(CMAKE_INSTALL_LIBDIR ${CMAKE_INSTALL_PREFIX}/lib)
endif()

install(TARGETS ${PROJECT_NAME}
  PUBLIC_HEADER DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}
  ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
 )
