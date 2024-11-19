# C Programming Problem Solving Guide 🚀

## 📋 Navigation Menu
- [String Palindrome](#1-string-palindrome)
- [Reverse Array](#2-reverse-array)
- [String Reverse](#3-string-reverse)
- [Input/Output in Array](#4-inputoutput-in-array)
- [2D Array Methods](#5-2d-array-methods)
- [Pointers and Swapping](#6-pointers)
- [Functions and Recursion](#7-functions-and-recursion)
- [Call by Value & Reference](#8-call-by-value--reference)
- [Structures](#9-structures)
- [Enumerations](#10-enumerations)
- [Additional Concepts](#11-additional-concepts)

## 1. String Palindrome
### Concept
A palindrome is a string that reads the same backward as forward.

### Algorithm
1. Take input string
2. Compare characters from start and end
3. Move towards center
4. If all characters match, it's a palindrome

### Code Implementation
```c
#include <stdio.h>
#include <string.h>

int isPalindrome(char *str) {
    // Get string length
    int length = strlen(str);
    
    // Compare characters from start and end
    for (int i = 0; i < length/2; i++) {
        // If characters don't match, not a palindrome
        if (str[i] != str[length - 1 - i]) {
            return 0;  // False
        }
    }
    return 1;  // True
}

int main() {
    char str[100];
    
    printf("Enter a string: ");
    scanf("%s", str);
    
    if (isPalindrome(str)) {
        printf("Palindrome!\n");
    } else {
        printf("Not a Palindrome!\n");
    }
    
    return 0;
}
```

### Explanation
- `strlen()` gets string length
- Loop compares characters from edges
- Returns 1 if palindrome, 0 if not

## 2. Reverse Array
### Algorithm
1. Create temporary variable
2. Swap elements from start and end
3. Move towards center

### Code Implementation
```c
#include <stdio.h>

void reverseArray(int arr[], int size) {
    // Temporary variable for swapping
    int temp;
    
    // Swap elements from start and end
    for (int i = 0; i < size/2; i++) {
        temp = arr[i];
        arr[i] = arr[size - 1 - i];
        arr[size - 1 - i] = temp;
    }
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    int size = sizeof(arr) / sizeof(arr[0]);
    
    printf("Original Array: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    
    reverseArray(arr, size);
    
    printf("\nReversed Array: ");
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    
    return 0;
}
```

### Key Points
- Uses temporary variable for swapping
- Swap occurs for half the array length
- `sizeof()` calculates array size dynamically

## 3. String Reverse
### Algorithm
1. Find string length
2. Swap characters from start and end
3. Move towards center

### Code Implementation
```c
#include <stdio.h>
#include <string.h>

void reverseString(char *str) {
    // Get string length
    int length = strlen(str);
    
    // Temporary character for swapping
    char temp;
    
    // Swap characters from start and end
    for (int i = 0; i < length/2; i++) {
        temp = str[i];
        str[i] = str[length - 1 - i];
        str[length - 1 - i] = temp;
    }
}

int main() {
    char str[100];
    
    printf("Enter a string: ");
    scanf("%s", str);
    
    reverseString(str);
    
    printf("Reversed String: %s\n", str);
    
    return 0;
}
```

### Explanation
- Similar to array reversal
- Works directly on string characters
- In-place reversal

## 4. Input/Output in Array
### Techniques
- Static array declaration
- Dynamic input
- Printing methods

### Code Implementation
```c
#include <stdio.h>

int main() {
    int n, i;
    
    // Dynamic array size input
    printf("Enter array size: ");
    scanf("%d", &n);
    
    // Declare array with input size
    int arr[n];
    
    // Input elements
    printf("Enter %d elements:\n", n);
    for (i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
    
    // Print elements
    printf("Array elements:\n");
    for (i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    
    return 0;
}
```

### Key Concepts
- Variable-length array
- Input using loops
- Output using loops

## 5. 2D Array Methods
### Matrix Operations
- Addition
- Multiplication

### Code Implementation
```c
#include <stdio.h>

#define MAX 10

// Matrix Addition
void addMatrices(int A[][MAX], int B[][MAX], int result[][MAX], int rows, int cols) {
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            result[i][j] = A[i][j] + B[i][j];
        }
    }
}

// Matrix Multiplication
void multiplyMatrices(int A[][MAX], int B[][MAX], int result[][MAX], 
                      int rowsA, int colsA, int colsB) {
    for (int i = 0; i < rowsA; i++) {
        for (int j = 0; j < colsB; j++) {
            result[i][j] = 0;
            for (int k = 0; k < colsA; k++) {
                result[i][j] += A[i][k] * B[k][j];
            }
        }
    }
}

int main() {
    int A[MAX][MAX], B[MAX][MAX], result[MAX][MAX];
    int rows, cols;
    
    // Input matrix dimensions
    printf("Enter matrix dimensions: ");
    scanf("%d %d", &rows, &cols);
    
    // Input first matrix
    printf("Enter first matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &A[i][j]);
        }
    }
    
    // Input second matrix
    printf("Enter second matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &B[i][j]);
        }
    }
    
    // Perform operations
    addMatrices(A, B, result, rows, cols);
    multiplyMatrices(A, B, result, rows, cols, cols);
    
    return 0;
}
```

### Visualization
```
Matrix A:  Matrix B:   Result:
1 2 3      4 5 6      5  7  9
4 5 6      7 8 9      11 13 15
```

## 6. Pointers
### Pointer Operations
- Swapping using pointers
- Memory addressing

### Code Implementation
```c
#include <stdio.h>

// Swap using pointers
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 10, y = 20;
    
    printf("Before swap: x = %d, y = %d\n", x, y);
    
    swap(&x, &y);
    
    printf("After swap: x = %d, y = %d\n", x, y);
    
    return 0;
}
```

### Pointer Concepts
- `*` for dereferencing
- `&` for address
- Pass by reference

## 7. Functions and Recursion
### Fibonacci Series
```c
#include <stdio.h>

// Recursive Fibonacci
int fibonacci(int n) {
    if (n <= 1) {
        return n;
    }
    return fibonacci(n-1) + fibonacci(n-2);
}

// Iterative Fibonacci
void fibonacciSeries(int n) {
    int first = 0, second = 1, next;
    
    printf("Fibonacci Series: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", first);
        next = first + second;
        first = second;
        second = next;
    }
}

int main() {
    int n;
    printf("Enter number of terms: ");
    scanf("%d", &n);
    
    fibonacciSeries(n);
    
    return 0;
}
```

### Recursion Concepts
- Base case
- Recursive call
- Function stack management

## 8. Call by Value & Reference
### Demonstrating Differences
```c
#include <stdio.h>

// Call by Value
void incrementByValue(int x) {
    x = x + 10;
}

// Call by Reference
void incrementByReference(int *x) {
    *x = *x + 10;
}

int main() {
    int a = 5, b = 5;
    
    incrementByValue(a);
    printf("Call by Value: %d\n", a);  // Still 5
    
    incrementByReference(&b);
    printf("Call by Reference: %d\n", b);  // Now 15
    
    return 0;
}
```

## 9. Structures
### Complex Number Example
```c
#include <stdio.h>

// Define Structure
struct ComplexNumber {
    float real;
    float imaginary;
};

// Function to add complex numbers
struct ComplexNumber addComplex(struct ComplexNumber c1, struct ComplexNumber c2) {
    struct ComplexNumber result;
    result.real = c1.real + c2.real;
    result.imaginary = c1.imaginary + c2.imaginary;
    return result;
}

int main() {
    struct ComplexNumber num1 = {3.5, 2.0};
    struct ComplexNumber num2 = {1.5, 4.0};
    
    struct ComplexNumber sum = addComplex(num1, num2);
    
    printf("Sum: %.2f + %.2fi\n", sum.real, sum.imaginary);
    
    return 0;
}
```

## 10. Enumerations
### Days of Week Example
```c
#include <stdio.h>

// Enum Declaration
enum Days {
    SUNDAY,    // 0
    MONDAY,    // 1
    TUESDAY,   // 2
    WEDNESDAY, // 3
    THURSDAY,  // 4
    FRIDAY,    // 5
    SATURDAY   // 6
};

int main() {
    enum Days today = WEDNESDAY;
    
    switch(today) {
        case SUNDAY:
            printf("Weekend!\n");
            break;
        case WEDNESDAY:
            printf("Midweek\n");
            break;
        default:
            printf("Another day\n");
    }
    
    return 0;
}
```

## 11. Additional Concepts
- Dynamic Memory Allocation
- File Handling
- Error Handling
- Bit Manipulation

### Best Practices
1. Always initialize variables
2. Use meaningful variable names
3. Handle memory carefully
4. Check for errors
5. Comment your code

### Learning Resources
- C Programming Books
- Online Tutorials
- Competitive Coding Platforms
- Practice, Practice, Practice!

## Conclusion
Mastering C requires consistent practice and understanding of fundamental concepts. Start with simple programs and gradually increase complexity. Happy Coding! 🖥️👨‍💻