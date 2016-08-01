#
#   If people don't build test don't add gtest
#
IF(BUILD_TESTING)
    ADD_SUBDIRECTORY(gtest)
ENDIF(BUILD_TESTING)

IF (BUILD_BENCHMARK)
    ADD_SUBDIRECTORY(hayai)
    INCLUDE_DIRECTORIES(hayai/src)
ENDIF(BUILD_BENCHMARK)

# Configure IMGUI dependencies
# ============================

add_subdirectory(glfw)

SET(GL3W_SRC 
    ${CMAKE_CURRENT_SOURCE_DIR}/gl3w/GL/gl3w.c
    PARENT_SCOPE
)

SET(IMGUI_SRC
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/imgui/imgui_draw.cpp
    PARENT_SCOPE
)
