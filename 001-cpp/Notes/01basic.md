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