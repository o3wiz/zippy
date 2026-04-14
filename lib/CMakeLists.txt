add_library(zippy)

# public headers
set(INCD_DIR "${CMAKE_CURRENT_LIST_DIR}/include")
set(HDRS_DIR "${INCD_DIR}/zippy")
file(GLOB_RECURSE HDR_FILES CONFIGURE_DEPENDS "${HDRS_DIR}/*.hpp")
target_sources(zippy
  PUBLIC
  FILE_SET HEADERS
  BASE_DIRS ${INCD_DIR}
  FILES ${HDR_FILES}
)

# internal headers
set(INT_HDRS_DIR "${CMAKE_CURRENT_LIST_DIR}/internal")
set(INT_HDR_FILES "${INT_HDRS_DIR}/*.hpp")
target_sources(zippy
  PRIVATE
  FILE_SET internalHeaders
  TYPE HEADERS
  BASE_DIRS ${INT_HDR_FILES}
)

# sources
set(SRCS_DIR "${CMAKE_CURRENT_LIST_DIR}/source")
file(GLOB_RECURSE SRC_FILES CONFIGURE_DEPENDS "${SRCS_DIR}/*.cpp")
target_sources(zippy PRIVATE ${SRC_FILES})

target_compile_features(zippy PUBLIC cxx_std_23)
