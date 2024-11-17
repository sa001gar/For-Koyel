# C Data Structures: Declaration and Initialization

 An easy-to-understand explanation of **declaration** and **initialization** in C for Arrays, Strings, Structures, Enums, and Pointers.

 #### Ei leh koyel tor jonno likhe dilam.💕

---

## 1. Array  
An array is a collection of elements of the same type stored in contiguous memory locations.

### Declaration
```c
int arr[5];  // Declares an integer array of size 5.
```
### Initialization
```c
arr[0] = 10;  // Initializing individual elements.
arr[1] = 20;
arr[2] = 30;
arr[3] = 40;
arr[4] = 50;
```
### Complete Example
```c
#include <stdio.h>
int main() {
    int arr[5];  // Declaration
    // Initialization
    arr[0] = 10;  
    arr[1] = 20;  
    arr[2] = 30;  
    arr[3] = 40;  
    arr[4] = 50;

    // Accessing elements
    for (int i = 0; i < 5; i++) {
        printf("arr[%d] = %d\n", i, arr[i]);
    }
    return 0;
}
```
## 2. Strings (Character Array)
A string is an array of characters terminated by a null character \0.

### Declaration
```c
char str[20];  // Declares a character array to hold up to 19 characters (1 reserved for '\0').
```
### Initialization
```c
str[0] = 'H';  
str[1] = 'e';  
str[2] = 'l';  
str[3] = 'l';  
str[4] = 'o';  
str[5] = '\0';  // Null-terminator
```
### Complete Example
```c
#include <stdio.h>
int main() {
    char str[20];  // Declaration
    // Initialization
    str[0] = 'H';  
    str[1] = 'e';  
    str[2] = 'l';  
    str[3] = 'l';  
    str[4] = 'o';  
    str[5] = '\0';  // Null terminator

    printf("String: %s\n", str);
    return 0;
}
```
## 3. Structure
A structure is a user-defined data type to group variables of different types.

### Declaration
```c
struct Student {
    int id;
    char name[20];
};
struct Student s1;  // Declares a variable of type Student.
```
### Initialization
```c
s1.id = 1;  
strcpy(s1.name, "John");  // String copy to initialize name.
```
### Complete Example
```c
#include <stdio.h>
#include <string.h>  // Required for strcpy
struct Student {
    int id;
    char name[20];
};

int main() {
    struct Student s1;  // Declaration
    // Initialization
    s1.id = 1;
    strcpy(s1.name, "John");  

    printf("ID: %d\n", s1.id);
    printf("Name: %s\n", s1.name);
    return 0;
}
```
## 4. Enum
An enum is a user-defined type consisting of named integer constants.

### Declaration
```c
enum Color {RED, GREEN, BLUE};  // Declares an enumeration.
enum Color favoriteColor;       // Declares a variable of type enum Color.
```
### Initialization
```c
favoriteColor = GREEN;  // Assigns a value from the enum.
```
### Complete Example
```c
#include <stdio.h>
enum Color {RED, GREEN, BLUE};

int main() {
    enum Color favoriteColor;  // Declaration
    // Initialization
    favoriteColor = GREEN;

    printf("Favorite Color (as integer): %d\n", favoriteColor);
    return 0;
}
```
## 5. Pointers
A pointer stores the memory address of another variable.

### Declaration
```c
int *p;  // Declares a pointer to an integer.
int x = 10;  
```
### Initialization
```c
p = &x;  // Assigns the address of x to the pointer p.
```
### Complete Example
```c
#include <stdio.h>
int main() {
    int x = 10;  
    int *p;  // Declaration
    // Initialization
    p = &x;

    printf("Value of x: %d\n", x);
    printf("Address of x: %p\n", p);
    printf("Value at address p points to: %d\n", *p);
    return 0;
}
```
## Summary Table

| **Data Type**   | **Declaration**                     | **Initialization**                                 |
|------------------|-------------------------------------|---------------------------------------------------|
| **Array**        | `int arr[5];`                      | `arr[0] = 10;`                                   |
| **String**       | `char str[20];`                    | `str[0] = 'H'; str[5] = '\0';`                   |
| **Structure**    | `struct Student {int id;};`        | `s1.id = 1; strcpy(s1.name, "John");`            |
| **Enum**         | `enum Color {RED, GREEN};`         | `favoriteColor = GREEN;`                         |
| **Pointer**      | `int *p; int x = 10;`              | `p = &x;`                                        |
