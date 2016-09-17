add_definitions(-DSOURCE_VERSION="${SOURCE_VERSION}")

include_directories(
    ${JANSSON_INCLUDE_DIRS}
    ${ZLIB_INCLUDE_DIRS}
)

add_executable(alfred-json
    main.c
    output_json.c
    zcat.c
)

target_link_libraries(alfred-json
    ${JANSSON_LIBRARIES}
    ${ZLIB_LIBRARIES}
)

set_target_properties(alfred-json PROPERTIES COMPILE_FLAGS "-std=gnu99 -Wall -pedantic -Wextra -Wshadow -O3")

install(TARGETS alfred-json RUNTIME DESTINATION bin)
