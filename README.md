# CMake sum 静态库作业

## 1. 运行环境与 CMake 版本
- 系统：Linux
- CMake 版本：3.26
- 编译器：g++

## 2. 配置、构建、运行命令
```bash
cmake -S . -B build
cmake --build build
./build/exe
```

实际输出：
```text
3 + 5 = 8
```

## 3. 文件作用
- include/sum.h：声明mymath::sum(int, int)
- src/sum.cpp：实现 mymath::sum，返回两数之和
- src/main.cpp：调用 mymath::sum(3, 5)，输出 `3 + 5 = 8`。
- 头文件只放声明，源文件负责定义实现

## 4. Target 说明
- mymath：静态库 Target，生成 libmymath.a
- exe：可执行 Target，链接 mymath
- PUBLIC 头文件目录：让链接 `mymath` 的程序也能找到 sum.h
- target_link_libraries(exe PRIVATE mymath)：让 exe 链接 mymath，获得 sum 的实现

## 5. 遇到的报错及解决过程
无
