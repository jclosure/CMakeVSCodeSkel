cmake_minimum_required(VERSION 3.0.0)

# set(CC, gcc-13)
# set(CXX, g++-13)

# enable_language(C)
# enable_language(CXX)

# target 1
project(Hello VERSION 0.1.0)
include(CTest)
enable_testing()
add_executable(Hello main.cpp)

# for macos
set(OpenCV_DIR "/opt/homebrew/include/opencv4")

# target 2
project( DisplayImage LANGUAGES CXX )
find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
add_executable( DisplayImage DisplayImage.cpp )
target_link_libraries( DisplayImage ${OpenCV_LIBS} )

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)