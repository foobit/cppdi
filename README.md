# building

## Install CMake
You will need at least **CMake 3.8** to support the `CMAKE_CXX_STANDARD` setting.

## Build commands
In your platform terminal, navigate to this source directory and enter the commands below.

Create and move into the build folder:
```
mkdir build && cd build
```
Have CMake configure the project:
```
cmake ..
```
Build the project:
```
cmake --build .
```

## Testing various C++ versions
In the `CMakeLists.txt` change the `set(CMAKE_CXX_STANDARD 11)` to the dialect choice.
- CMAKE_CXX_STANDARD 11
- CMAKE_CXX_STANDARD 14
- CMAKE_CXX_STANDARD 17
- CMAKE_CXX_STANDARD 20

Note some compilers do not yet support C++20
