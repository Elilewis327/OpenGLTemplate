cmake_minimum_required(VERSION 3.0.0)
project(GameofLife VERSION 0.1.0)

include(CTest)
enable_testing()

include_directories(/opt/homebrew/include)
link_directories(/opt/homebrew/lib)

include_directories(./glad/include)

add_executable(GameofLife main.cpp)

add_subdirectory(glad/)
target_link_libraries(GameofLife glad)

target_link_libraries(GameofLife glfw)
find_package(OpenGL REQUIRED)
target_link_libraries(GameofLife OpenGL::GL)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
