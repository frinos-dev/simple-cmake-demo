# Using Different Build Generators on Windows with CMake
This demo will show how to use CMake to build a basic C++ application with CMake on Windows using three different build systems.<br/>
The code in this repository is very basic and consists of just a main.cpp source file and a CMakelists.txt script. The idea is to understand the kinds of tools that need to be installed for CMake to work.<br/>
First a few different build generators are installed and then used with CMake to build the application.

## Installing Build Generators
The build generators used in this demo are 
- **Visual Studio 17 2022** which will build Visual Studio projects, 
- **MinGW Makefiles** which will generate MinGW makefiles,
- **Ninja** which will generate ninja build configurations.

### Install MSVC Build Tools
1. Install the Visual Studio 2022 build tools by following instructions at https://code.visualstudio.com/docs/cpp/config-msvc

### Install MinGW-x64 Toolset
1. Install the MinGW-x64 by following instructions at https://code.visualstudio.com/docs/languages/cpp#_example-install-mingwx64 
2. Download the latest **ninja-win.zip** build generator from https://github.com/ninja-build/ninja/releases
3. Extract the **ninja.exe** from the **ninja-win.zip** file to a new folder and add this folder to the user PATH environment variable

Note that this will also install the gcc compiler as well as the MinGW build system.

## Building the helloworld Application
Now we use the build generators to build the helloworld application

### Using the Visual Studio 2022 Generator
1. Create a folder called build_vs2022<br/>**mkdir build_vs2022**
2. Change directory to the new folder<br/>**cd build_vs2022**
3. Generate the CMake build files<br/>**cmake -S ../ -B ./ -G "Visual Studio 17 2022"**
4. Build the application<br/>**cmake --build .**

### Using the Ninja Build Generator
1. Create a folder called build_ninja<br/>**mkdir build_ninja**
2. Change directory to the new folder<br/>**cd build_ninja**
3. Generate the CMake build files<br/>**cmake -S ../ -B ./ -G "Ninja"**
4. Build the application<br/>**cmake --build .**

### Using the Mingw Build Generator
1. Create a folder called build_mingw<br/>**mkdir build_mingw**
2. Change directory to the new folder<br/>**cd build_mingw**
3. Generate the CMake build files<br/>**cmake -S ../ -B ./ -G "MinGW Makefiles"**
4. Build the application<br/>**cmake --build .**

The options used with CMake are
* **-S** the location of the CMakeLists.txt file
* **-B** the location of the build folder into which CMake will write the build config
* **-G** the build generator to use (see https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html)
