# GoogleTest

Provides support for GoogleTest 1.7 (r711) and CMake (3.2.2) on:
- OSX (x86_64)
- iOS (armv7, arm64)
- Android (armeabi-v7a)
- Emscripten

More info in the [Wiki](https://github.com/arielm/chronotext-gtest/wiki)...

## Setup...
```
cd chronotext-gtest
./setup.sh
```
This will download and unpack a version of GoogleTest adapted to the relevant platforms.

## Build...
```
./build-osx.sh
./build-ios.sh
./build-android.sh
./build-emscripten.sh
```
This will build static libs for the relevant platforms, and package everything as follows:
```
|--include
|  |--gtest
|--lib
   |--osx
   |  |--libgtest.a
   |  |--libgtest_main.a
   |--ios
   |  |--libgtest.a
   |  |--libgtest_main.a
   |--android
   |  |--libgtest.a
   |  |--libgtest_main.a
   |--emscripten
      |--libgtest.a
      |--libgtest_main.a
```

## Run...
```
cd test

ctest -S run.cmake -VV -DPLATFORM=osx
ctest -S run.cmake -VV -DPLATFORM=ios
ctest -S run.cmake -VV -DPLATFORM=android
ctest -S run.cmake -VV -DPLATFORM=emscripten
```
This will build a simple test, and execute it on the relevant platforms.
