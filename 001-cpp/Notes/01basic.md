# C++
## What is C++?
- C++ is a general-purpose, cross-platform programming language developed by Bjarne Stroustrup as an extension of the C programming language.

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

# How the compiler actually works
## Preprocessing
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
#### math.i
```cpp
int add(int a, int b){
    int result = a + b;
}
```
#### math.asm
```asm
; Assembly code generated from math.i
; Actual output depends on the compiler and target architecture.
```
- The compiler converts the preprocessed `.i` file to an assembly `.asm` file.
- The assembler converts `.asm` into an object file `.obj` (object contents not shown).
- So as we can see above, the `.i` file is the preprocessed source before assembly and `.asm` is the assembly version before object file generation.
- And this `math.asm` is converted to `math.obj`
