# How to build

- mkdir build
- cd build
- conan install .. --build missing
- cmake .. [additional CMake options if you want]
- cmake --build .
- ctest --output-on-failure


