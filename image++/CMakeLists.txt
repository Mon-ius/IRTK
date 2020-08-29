cmake_minimum_required(VERSION 2.8.10)
project(IMAGE C)

include_directories(include ${CONTRIB_INCLUDE_DIRS})

file(GLOB IMAGE_INCLUDES include/*.h)
file(GLOB IMAGE_SRCS src/*.cc)

add_library(${PROJECT_NAME} STATIC ${IMAGE_SRCS})

set(${PROJECT_NAME}_INCLUDE_DIRS ${PROJECT_SOURCE_DIR}/include
    CACHE INTERNAL "${PROJECT_NAME}: Include Directories" FORCE)

set_target_properties(${PROJECT_NAME} PROPERTIES OUTPUT_NAME ${PROJECT_NAME})

if(UNIX AND NOT ${CMAKE_SYSTEM_NAME} MATCHES "Darwin")
  TARGET_LINK_LIBRARIES(${PROJECT_NAME} rt)
endif()

install(TARGETS 
    # ${PROJECT_NAME} 
    ${PROJECT_NAME} 
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)

install(FILES ${IMAGE_INCLUDES} DESTINATION include)
