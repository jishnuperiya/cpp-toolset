cmake_minimum_required(VERSION 3.16)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES C CXX)

add_library(Library STATIC my_lib.cc) #later in the course static and shared is described

add_executable(Executable main.cc)

target_link_libraries(Executable PUBLIC Library) # you have to make sure the executable get linked to the library. we have different keywords(public, private and interface - discussed later in course)


#note: here there are 2 targets. one is the Executable and one is the Library. you can choose to build only one target as well without bulding the whole project.
# lets say we want to check if the library is working or not. then we can build only library. command for that is :
# go to build folder after configuring the prject (cmake .. command) type: cmake --build . --target Library

# to build executable. cmake --build . --target Executable ( here since the Executable is also linked with Library, just building the executable also bild library)

