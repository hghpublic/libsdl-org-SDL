cmake_minimum_required(VERSION 4.4)

project(examples C)

set(CMAKE_C_STANDARD 23)

include(FetchContent)
FetchContent_Declare(
  SDL3
  GIT_REPOSITORY https://github.com/libsdl-org/SDL.git
  GIT_TAG main
)

FetchContent_MakeAvailable(SDL3)

if(0)
find_package(SDL3 CONFIG REQUIRED)
# target_link_libraries(main PRIVATE SDL3::SDL3)
endif()

add_subdirectory(examples)
