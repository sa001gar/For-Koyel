# C Programming Language - Comprehensive Notes

## Table of Contents
1. [Introduction to C](#introduction-to-c)
2. [Basic Syntax](#basic-syntax)
3. [Data Types](#data-types)
4. [Variables and Constants](#variables-and-constants)
5. [Operators](#operators)
6. [Control Structures](#control-structures)
7. [Functions](#functions)
8. [Arrays](#arrays)
9. [Pointers](#pointers)
10. [Structures](#structures)
11. [File Handling](#file-handling)
12. [Memory Management](#memory-management)
13. [Preprocessor Directives](#preprocessor-directives)
14. [Advanced Topics](#advanced-topics)

## Introduction to C
- Developed by Dennis Ritchie at Bell Labs in 1972
- Low-level, compiled programming language
- Provides close access to system resources
- Fundamental to system programming, embedded systems, and operating systems

## Basic Syntax
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```
- Programs start with `main()` function
- Statements end with semicolon `;`
- Case-sensitive language
- Compiled using gcc/clang compilers

## Data Types
### Primitive Types
- `int`: Integer numbers (4 bytes)
- `char`: Single character (1 byte)
- `float`: Floating-point numbers (4 bytes)
- `double`: Double-precision floating-point (8 bytes)

### Derived Types
- Arrays
- Pointers
- Structures
- Unions

## Variables and Constants
### Variable Declaration
```c
int age = 25;
char grade = 'A';
float salary = 5000.50;
```

### Constants
```c
#define PI 3.14159
const int MAX_SIZE = 100;
```

## Operators
### Arithmetic Operators
- `+`: Addition
- `-`: Subtraction
- `*`: Multiplication
- `/`: Division
- `%`: Modulus

### Logical Operators
- `&&`: Logical AND
- `||`: Logical OR
- `!`: Logical NOT

### Bitwise Operators
- `&`: Bitwise AND
- `|`: Bitwise OR
- `^`: Bitwise XOR
- `<<`: Left shift
- `>>`: Right shift

## Control Structures
### Conditional Statements
```c
if (condition) {
    // code
} else if (another_condition) {
    // code
} else {
    // code
}

switch (variable) {
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

### Loops
```c
// For loop
for (int i = 0; i < 10; i++) {
    // code
}

// While loop
while (condition) {
    // code
}

// Do-while loop
do {
    // code
} while (condition);
```

## Functions
### Function Declaration
```c
// Function prototype
int add(int a, int b);

// Function definition
int add(int a, int b) {
    return a + b;
}

// Function call
int result = add(5, 3);
```

### Function Types
- Void functions
- Functions with return values
- Recursive functions
- Inline functions

## Arrays
```c
// 1D Array
int numbers[5] = {1, 2, 3, 4, 5};

// 2D Array
int matrix[3][3] = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};
```

## Pointers
```c
int x = 10;
int *ptr = &x;  // Pointer declaration

// Pointer arithmetic
int arr[5];
int *p = arr;
p++;  // Points to next array element
```

### Pointer Types
- Null pointers
- Void pointers
- Function pointers

## Structures
```c
struct Student {
    char name[50];
    int roll_no;
    float marks;
};

// Structure initialization
struct Student s1 = {"John", 101, 85.5};
```

## File Handling
```c
FILE *fp;
fp = fopen("file.txt", "r");  // Read mode
// File operations
fclose(fp);
```

### File Operations
- Reading files
- Writing files
- Appending
- Error handling

## Memory Management
### Dynamic Memory Allocation
```c
int *ptr = (int*) malloc(5 * sizeof(int));
free(ptr);
```

### Memory Functions
- `malloc()`
- `calloc()`
- `realloc()`
- `free()`

## Preprocessor Directives
```c
#include <stdio.h>
#define MAX 100
#ifdef DEBUG
    // Conditional compilation
#endif
```

## Advanced Topics
- Bit manipulation
- Complex data structures
- Multi-threading
- Network programming
- Embedded systems programming

### Important Libraries
- `<stdio.h>`
- `<stdlib.h>`
- `<string.h>`
- `<math.h>`

## Best Practices
- Use meaningful variable names
- Comment your code
- Handle memory carefully
- Check for errors
- Optimize performance
- Follow coding standards

## Common Pitfalls
- Buffer overflows
- Memory leaks
- Uninitialized pointers
- Integer overflow
- Incorrect type casting

## Compiling and Running
```bash
# Compile
gcc program.c -o program

# Run
./program
```

## References and Resources
- K&R C Programming Book
- Online C tutorials
- GNU Compiler Collection (GCC) documentation

### Practice Platforms
- HackerRank
- LeetCode
- CodeChef
- Project Euler

**Note**: Continuously practice and explore C programming to master the language.