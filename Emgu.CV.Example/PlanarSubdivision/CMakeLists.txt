PROJECT(Example.PlanarSubdivision)

FILE(GLOB_RECURSE SRC_Example_PlanarSubdivision RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} "*.cs")
SET(SRC_Example_PlanarSubdivision ${SRC_Example_PlanarSubdivision} ${CMAKE_CURRENT_SOURCE_DIR}/../../CommonAssemblyInfo.cs)

SET(CS_FLAGS ${CS_FLAGS} ${EMGU_CV_REFERENCE})

COMPILE_CS(${PROJECT_NAME} "winexe" "${SRC_Example_PlanarSubdivision}" ALL)

ADD_DEPENDENCIES(${PROJECT_NAME} Emgu.CV Emgu.CV.UI)

INSTALL(FILES ${LIBRARY_OUTPUT_PATH}/${PROJECT_NAME}.${CS_EXECUTABLE_EXTENSION} DESTINATION bin COMPONENT binary)
