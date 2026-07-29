# Data Types and Variables

```cpp
int a = 10;
```
- Here `int` is a data type, `a` is a variable, and `10` is the value
- Data types tell the computer how to store values and how much memory to allocate
- Common data types:
    - char - 1 byte
    - short - 2 bytes
    - int - 4 bytes
    - long - 4 bytes
    - long long - 8 bytes
    - float - 4 bytes
    - double - 8 bytes
    - bool - 1 byte
- The main difference between data types is the amount of memory allocated
```cpp
char a = 65;
cout<<a;
```
Output:
```cpp
A
```
- Here, even though we defined the variable `a` as `char`, we assigned a number, but the output is `A` because character `A` is associated with ASCII value 65, and the `char` data type prints it as a character
- We can do the reverse as well, storing a character in an `int` data type variable and when we print we see the ASCII value associated with that character.
- To store decimal values use float or double according to the required size.
- bool is a data type which is used to store `true` or `false`, which is 1 or 0
  - bool data type is of 1 byte, but we are storing either 1 or 0, so why not 1 bit, so answer is  because we cant access bits in computer, we can access only bytes and write only bytes
- Operator to know the size of data type: `sizeof()`

# Functions
```cpp
int multiply(int a, int b){
    return a*b;
}
```
`int : return type`
`multiply : function name`
`int a, int b : parameters of the function`
- Used to simplify the code and reduce the repetation of using same code
- That doesnt mean each and every line should be converted in to function
- When we call a function there is a stack created and the functions are pushed into the stack
Example:
```cpp
fun1();
fun2();
fun3();
```
```cpp
Stack:
    fun1()
    fun2()
    fun3()
```
And the upper most of the stack is run first
- `main()` function is a special function, even though the return type  of `main()` is `int`, if we dont return anything then the default return 0 will be done.