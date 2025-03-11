android平台(arm64-v8a)建议16kb对齐，需要CMakeLists中设置
target_link_options(opus PRIVATE
    "-Wl,-z,max-page-size=16384"
)

需要编译armeabi-v7a arm64-v8a

```shell
rm -rf build
mkdir build
cd build
cmake .. -DCMAKE_TOOLCHAIN_FILE="/C/Program Files/Unity/Hub/Editor/2022.3.59f1/Editor/Data/PlaybackEngines/AndroidPlayer/ndk/build/cmake/android.toolchain.cmake" -DANDROID_ABI=arm64-v8a -DOPUS_BUILD_SHARED_LIBRARY=ON
cmake --build . --config Release
```

windows平台

```shell
rm -rf build
mkdir build
cd build
cmake .. -G "Visual Studio 17 2022" -A x64 -DOPUS_BUILD_SHARED_LIBRARY=ON
cmake --build . --config Release
```