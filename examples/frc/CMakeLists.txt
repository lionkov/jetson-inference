
file(GLOB frcSources *.cpp)
file(GLOB frcIncludes *.h )

cuda_add_executable(frc ${frcSources})

include_directories(${wpiutil_DIR}/include/wpiutil ${ntcore_DIR}/include/ntcore ${cameraserver_DIR}/include/cameraserver ${cscore_DIR}/include/cscore)
target_link_libraries(frc jetson-inference wpiutil wpilibc ntcore cameraserver cscore)
add_definitions(-std=c++17)

install(TARGETS frc DESTINATION bin)
