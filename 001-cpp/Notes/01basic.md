# C++
## What is C++?
- C++ is a general-purpose, cross-platform programming language developed by Bjarne Stroustrup as an extension of the C programming language.
---
## How C++ Works?
```c++
#include<iostream>

int main(){
    std::cout<<"Hello World"<<std::endl;
}
```
- The `#include` is a preprocessor directive that tells the preprocessor to include the contents of a header file before compilation.
- `main()` is the entry point of a C++ program. Program execution begins here, and statements are executed sequentially unless control flow changes (loops, conditionals, function calls, etc.).
- `iostream` is the header file included with the help of `#include`.
- Header files are not compiled on their own; only .cpp files are compiled. Header files are compiled after they are included in .cpp files.
- **.cpp** files are compiled into objects with the **.obj** extension.
- Multiple **.obj** files are linked together by the linker.
- For example:

main.cpp
```c++
#include<iostream>

void fun(const char* message);

int main(){
    fun("Hello world");
}
```
fun.cpp
```c++
void fun(const char* message){
    std::cout<<message<<std::endl;
}
```
- There are two files, `main.cpp` and `fun.cpp`. To use the function from `fun.cpp`, you need to declare the function in `main.cpp`. This is called a **declaration**.
- **Declaration**: A statement that indicates a function, symbol, or variable exists.
- The `main.cpp` and `fun.cpp` files are compiled into `main.obj` and `fun.obj` respectively. The linker then combines these multiple objects into a single executable(`.exe`).
---
## How the compiler actually works
- The first step of compilation is to convert the .cpp file to a preprocessed file with the .i extension. All preprocessing directives such as #include, #define, #if, #ifndef, etc., are expanded in the .i file.
- Next, the preprocessed .i file is translated to a human-readable assembly file (commonly .asm; some toolchains may use other extensions).
- The assembler converts this assembly file into an object file (.obj or .o, depending on the platform).
- These object files are then combined by the linker to produce the final executable.
- Example to illustrate the compilation stages

##### End_brace.h
```h
}
```

##### math.cpp
```cpp
int add(int a, int b){
    int result = a + b;
#include "End_brace.h"
```
##### math.i
```cpp
int add(int a, int b){
    int result = a + b;
}
```
##### math.asm
```asm
; Assembly code generated from math.i
; Actual output depends on the compiler and target architecture.
```
- The compiler converts the preprocessed `.i` file to an assembly `.asm` file.
- The assembler converts `.asm` into an object file `.obj` (object contents not shown).
- So as we can see above, the `.i` file is the preprocessed source before assembly and `.asm` is the assembly version before object file generation.
- And this `math.asm` is converted to `math.obj`
---
## Linker
- The linker is responsible for stitching together multiple object files produced throughout the project into a single executable.
- The linker resolves symbols such as function calls and global variables across object files.
- A starting point is required for the linked program, and that starting point is usually `int main()`.
- If there is no `int main()`, the compiler may still compile individual `.cpp` files to object files, but the linker will fail because it cannot find the program entry point.
- The most common linker error is `unresolved external symbol`.
- This error occurs when a function or variable is declared or used, but its definition is not found in any of the linked object files or libraries.
- Example:
main.cpp
```c++
#include <iostream>

void Log(const char* msg);

int main() {
    Log("Hello");
}
```
log.cpp
```c++
#include <iostream>

void Logr(const char* msg) {
    std::cout << msg << std::endl;
}
```
- Even though `main.cpp` declares and uses `Log`, `log.cpp` defines `Logr` instead. This name mismatch causes the linker to fail with an `unresolved external symbol` for `Log`.
- If `log.cpp` is not compiled and linked, or if its function name doesn't match the declaration in `main.cpp`, the linker reports an `unresolved external symbol`.
- If the declaration in `main.cpp` does not match the actual definition in `fun.cpp` (for example, different function name, parameter types, or return type), the compiler may still compile each file, but the linker will fail because it cannot find a matching definition for the declared symbol.
- The declaration `void Log(const char* msg);` in `main.cpp` is not enough by itself; the definition must be available to the linker and must have the same name and signature.
- The linker also combines startup code and libraries with the object files to produce the final executable.
---
## Header Files
- Header files are used to store declarations such as function declarations, variable declarations, and macro declarations.
- `#pragma once` prevents a header file from being included multiple times in a single translation unit.
- The traditional way to avoid multiple inclusions is with include guards:
```cpp
#ifndef HEADER_NAME_H
#define HEADER_NAME_H
<body>
#endif
```
- `#pragma once` is the newer and widely accepted approach.
- `#include <iostream>` is commonly used in C++, while `#include <stdio.h>` is used in C. The `.h` extension is common in C, but in C++ it is not required for standard headers; this is simply a convention established by the language's evolution.
