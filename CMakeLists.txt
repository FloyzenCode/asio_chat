cmake_minimum_required(VERSION 3.20)
project(learn_boost_asio)
set(CMAKE_CXX_STANDARD 11)
set(Boost_INCLUDE_DIR /Users/floyz/cpp-tools/boost_1_82_0) # change path
set(Boost_LIBRARY_DIR /Users/floyz/cpp-tools/boost_1_82_0/stage/lib) # change path
set(Boost_USE_STATIC_LIBS ON)
find_package(Boost COMPONENTS filesystem thread REQUIRED)
include_directories(${Boost_INCLUDE_DIR})
link_directories(${Boost_LIBRARY_DIR})
add_executable(server chat_server.cpp)
add_executable(client chat_client.cpp)
target_link_libraries(server ${Boost_LIBRARIES})
target_link_libraries(client ${Boost_LIBRARIES})