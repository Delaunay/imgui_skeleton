# better way ?
INCLUDE_DIRECTORIES(.)

# Source files
# ====================================
#           (Glob is not recommended)

INCLUDE_DIRECTORIES(../dependencies/gl3w)
INCLUDE_DIRECTORIES(../dependencies/glfw/include/)
INCLUDE_DIRECTORIES(../dependencies/imgui)

SET(PROJECT_TEST_HDS
    imgui_impl_glfw_gl3.h
)

SET(PROJECT_TEST_SRC
    imgui_impl_glfw_gl3.cpp
    imgui_demo.cpp
    main.cpp
)

ADD_EXECUTABLE(${PROJECT_NAME}
    ${PROJECT_TEST_SRC} ${PROJECT_TEST_HDS}
    ${IMGUI_SRC} ${GL3W_SRC}
)

TARGET_LINK_LIBRARIES(${PROJECT_NAME} GL glfw)
SET_PROPERTY(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 14)



