INCLUDE_DIRECTORIES(../src)

MACRO(EXAMPLE_MACRO NAME LIBRARIES) # LIBRARIES
    ADD_EXECUTABLE(${NAME} ${NAME}.cpp)
    TARGET_LINK_LIBRARIES(${NAME} ${LIBRARIES})
    ADD_DEPENDENCIES(${NAME} ${LIBRARIES})
    SET_PROPERTY(TARGET ${NAME} PROPERTY CXX_STANDARD 11)
ENDMACRO(EXAMPLE_MACRO)

