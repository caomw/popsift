set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR})

add_executable( popsift-demo main.cpp pgmread.cpp pgmread.h )

target_include_directories( popsift-demo PRIVATE
                            ${CMAKE_SOURCE_DIR}/src
                            )

target_link_libraries( popsift-demo popsift
                               ${CUDA_LIBRARIES}
			       ${CUDA_CUDADEVRT_LIBRARY}
			       ${Boost_LIBRARIES} )

install(TARGETS popsift-demo DESTINATION bin EXPORT popsift-targets)

