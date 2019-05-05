cmake_minimum_required(VERSION 3.12)

project(VulkanTuto)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(SOURCE_FILES main.cpp)
add_executable(${PROJECT_NAME} ${SOURCE_FILES})



find_package(glfw3 3.2 REQUIRED)

include_directories(${GLFW_INCLUDE_DIRS})

find_package(Vulkan REQUIRED)

find_package(OpenGL REQUIRED)

include_directories(${OPENGL_INCLUDE_DIR})

target_link_libraries(${PROJECT_NAME} glfw ${Vulkan_LIBRARIES} ${OPENGL_LIBRARIES})
