set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

set(SYMBOLMAP "-Wl,-version-script=\"${CMAKE_SOURCE_DIR}/src/symbolmap\"")

add_library(widevine SHARED
    chromecdm.cc
    entrypoint.cc
    firefoxcdm.cc
)

target_link_libraries(widevine ${SYMBOLMAP} clearkey-excerpts)
