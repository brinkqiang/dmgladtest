cmake_minimum_required(VERSION 3.8)

PROJECT(dmgladtest)

LIST(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
INCLUDE(cmake/ModuleImport.cmake)
INCLUDE(cmake/ModuleCompileOptions.cmake)
ModuleSetCompileOptions()

find_package(glad CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(OpenGL REQUIRED)

include_directories(${GLFW_INCLUDE_DIRS})
include_directories(${GLAD_INCLUDE_DIRS})
include_directories(${OpenGL_INCLUDE_DIRS})
link_directories(${GLFW_LIBRARY_DIRS})
link_directories(${GLAD_LIBRARY_DIRS})
link_directories(${OpenGL_LIBRARY_DIRS})

ExeImport("test" "glad::glad;glfw;OpenGL::GL")
