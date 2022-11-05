# Building various flavours of helloworld using CMake

# Install MSVC Build Tools
1. Install the Visual Studio 2022 build tools by following instructions at https://code.visualstudio.com/docs/cpp/config-msvc

# Install gcc for Windows
1. Install Install MinGW-x64 by following instructions at https://code.visualstudio.com/docs/languages/cpp#_example-install-mingwx64 
2. Download the latest ninja-win.zip build generator from https://github.com/ninja-build/ninja/releases
3. Unzip ninja-win.zip to a folder and add this folder to the user PATH environment variable

# Building helloworld using MSVC
1. Create a folder called build_vs2022 (mkdir build_vs2022)
2. Change directory to the new folder (cd build_vs2022)
3. Generate the CMake build files (cmake -S ../ -B ./ -G "Visual Studio 17 2022")
4. Build helloworld (cmake --build -S ../ -B ./)

# Building helloworld using gcc on Windows
1. Create a folder called build_gcc (mkdir build_gcc)
2. Change directory to the new folder (cd build_gcc)
3. Generate the CMake build files (cmake -S ../ -B ./ -G Ninja)
4. Build helloworld (cmake --build -S ../ -B ./)
