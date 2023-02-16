cmake_minimum_required(VERSION 3.15)

set(PROJECT_NAME Particulier)

project(${PROJECT_NAME})

set(CMAKE_CXX_STANDARD 23)

include_directories(include)

add_executable(${PROJECT_NAME}
        sources/main.cpp sources/main.cpp)


find_package(SFML COMPONENTS system window graphics network audio)

if(SFML_FOUND)

    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${PROJECT_NAME}
            sfml-system
            sfml-window
            sfml-graphics
    )

    # all
    #
    # OU
    #
    # sfml-system
    # sfml-window
    # sfml-network
    # sfml-graphics
    # sfml-audio
    # sfml-main

else()
    message("Download SFML")
endif()