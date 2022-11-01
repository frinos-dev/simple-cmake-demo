cmake_minimum_required(VERSION 3.10)

# set the project name
project(
  "helloworld"
  VERSION 1.0
  DESCRIPTION "A simple project to demonstrate basic CMake usage"
  LANGUAGES CXX)
                        
# add the executable
add_executable(helloworld)
target_sources(helloworld PRIVATE src/main.cpp)
