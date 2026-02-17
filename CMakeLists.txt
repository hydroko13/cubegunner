cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(cubegunner)

include(FetchContent)

add_executable(${PROJECT_NAME}

    "${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp"

)

FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw.git
    GIT_TAG 3.4
)

FetchContent_Declare(
    glm
    GIT_REPOSITORY https://github.com/g-truc/glm.git
    GIT_TAG 1.0.3
)

FetchContent_MakeAvailable(glfw)

FetchContent_MakeAvailable(glm)

target_link_libraries(${PROJECT_NAME}
    glfw3 glm 
)