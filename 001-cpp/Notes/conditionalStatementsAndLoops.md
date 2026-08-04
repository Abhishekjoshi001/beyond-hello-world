# Conditional Statements and Loops in C++

## 1. if-else

- `if` executes a block only when a condition is true.
- `else` executes when the condition is false.

Syntax:
```cpp
if (condition) {
    // code if condition is true
} else {
    // code if condition is false
}
```

Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int age = 18;

    if (age >= 18) {
        cout << "Eligible to vote" << endl;
    } else {
        cout << "Not eligible to vote" << endl;
    }

    return 0;
}
```

### Branching of `if-else`

- `if` checks the first condition.
- If false, it goes to `else`.
- Only one branch runs.

### `else if`

`else if` is not a keyword by itself. It is simply:

```cpp
else {
    if (condition) {
        // code
    }
}
```

Expanded form:
```cpp
if (condition1) {
    // code 1
} else if (condition2) {
    // code 2
} else {
    // default code
}
```

Example:
```cpp
int marks = 75;

if (marks >= 90) {
    cout << "A" << endl;
} else if (marks >= 75) {
    cout << "B" << endl;
} else {
    cout << "C" << endl;
}
```

## 2. switch

- `switch` is used when comparing one value against many possible cases.
- It works by matching the expression with each `case`.
- `break` stops execution from falling into the next case.
- `default` runs when no case matches.

Syntax:
```cpp
switch (expression) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code
}
```

Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int day = 3;

    switch (day) {
        case 1:
            cout << "Monday" << endl;
            break;
        case 2:
            cout << "Tuesday" << endl;
            break;
        case 3:
            cout << "Wednesday" << endl;
            break;
        default:
            cout << "Invalid day" << endl;
    }

    return 0;
}
```

## 3. Loops

### `for` loop

- Used when the number of iterations is known.

Syntax:
```cpp
for (initialization; condition; update) {
    // code
}
```

Example:
```cpp
for (int i = 0; i < 5; i++) {
    cout << i << endl;
}
```

### `while` loop

- Runs while the condition is true.
- Condition is checked before every iteration.

Syntax:
```cpp
while (condition) {
    // code
}
```

Example:
```cpp
int i = 0;
while (i < 5) {
    cout << i << endl;
    i++;
}
```

### `do-while` loop

- Runs at least once.
- Condition is checked after executing the block.

Syntax:
```cpp
do {
    // code
} while (condition);
```

Example:
```cpp
int i = 0;
do {
    cout << i << endl;
    i++;
} while (i < 5);
```

## 4. Control Statements

### `continue`

- Used only inside loops.
- Skips the remaining statements in the current iteration.
- Moves to the next iteration.

Example:
```cpp
for (int i = 0; i < 5; i++) {
    if (i == 2) {
        continue;
    }
    cout << i << endl;
}
```

### `break`

- Exits the loop immediately.
- Also used in `switch` statements to stop falling through.

Example:
```cpp
for (int i = 0; i < 5; i++) {
    if (i == 3) {
        break;
    }
    cout << i << endl;
}
```

### `return`

- Ends the current function and returns control to the caller.
- Can also return a value.

Example:
```cpp
int add(int a, int b) {
    return a + b;
}
```
