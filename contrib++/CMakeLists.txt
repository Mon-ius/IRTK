cmake_minimum_required(VERSION 2.8.10)
project(CONTRIB C)

include_directories(${PROJECT_SOURCE_DIR}/include)

file(GLOB CONTRIB_INCLUDES include/*.h)
file(GLOB CONTRIB_SRCS src/*.cc)

add_library(${PROJECT_NAME} STATIC ${CONTRIB_SRCS})

set(${PROJECT_NAME}_INCLUDE_DIRS ${PROJECT_SOURCE_DIR}/include
    CACHE INTERNAL "${PROJECT_NAME}: Include Directories" FORCE)

set_target_properties(${PROJECT_NAME} PROPERTIES OUTPUT_NAME ${PROJECT_NAME})

install(TARGETS 
    # ${PROJECT_NAME} 
    ${PROJECT_NAME} 
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)

install(FILES ${CONTRIB_INCLUDES} DESTINATION include)
