CMAKE_MINIMUM_REQUIRED (VERSION 2.6)
PROJECT(gain CXX)

# fmi2Function.h, fmi2FunctionTypes.h and fmi2TypesPlatform.h
INCLUDE_DIRECTORIES($ENV{FMI_HEADERS} inc/ )


FILE(GLOB_RECURSE SRC_FILES *.cc)

ADD_LIBRARY(${PROJECT_NAME} SHARED ${SRC_FILES})
add_definitions(-Wno-write-strings -fPIC)
TARGET_LINK_LIBRARIES(${PROJECT_NAME})
SET_TARGET_PROPERTIES(${PROJECT_NAME}  PROPERTIES ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib PREFIX "")
