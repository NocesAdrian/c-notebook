# c-notebook
A log of my C journey—documenting what I learn, break, and forget. My personal time machine for C knowledge. For future me.
#### navigation
- [Introduction to c](https://github.com/NocesAdrian/c-notebook/blob/main/Introduction.md)

___

## Pointer
```cpp
SCANF(3)                    GNU C Library Functions                    SCANF(3)

NAME
    scanf - read formatted input from stdin

SYNOPSIS
    #include <stdio.h>

    int scanf(const char *format, ...);

DESCRIPTION
    The scanf function reads input from standard input, according to the format string
    format, and stores the result in the variables provided as additional arguments.
    When dealing with character arrays, scanf reads a string from stdin and stores it
    in a char array until a whitespace or the end of the input is encountered.

    The array passed to scanf is typically a pointer to its first element.

USAGE

    The correct way to use scanf with an array:

        char arr[10];
        scanf("%s", arr);  // arr is a pointer to the first element

    In this example, arr is a pointer to the first element of the array (arr[0]),
    and scanf writes to the array sequentially until it encounters a whitespace or
    the maximum size is reached. A null terminator ('\0') is automatically added at
    the end of the string.

PROBLEM WITH USING &ARR
    If scanf is called with &arr instead of arr, it will not work as expected:

        char arr[10];
        scanf("%s", &arr);  // WRONG: passing the address of the entire array

    This is incorrect because &arr is a pointer to the entire array (char(*)[10]),
    not a pointer to the first element (char*). The types don't match, and this
    causes undefined behavior, potentially preventing scanf from writing correctly
    to the array.

BUFFER OVERFLOW
    Buffer overflow occurs if the input string exceeds the size of the array. If
    the input string is larger than the array's allocated space, it will overflow,
    potentially corrupting adjacent memory.

    Example:

        char arr[5];
        scanf("%s", arr);  // Input: "HelloWorld" causes overflow

    This is problematic because the array arr only has space for 5 characters,
    but the input string "HelloWorld" requires 11 characters, leading to overflow.

AVOIDING BUFFER OVERFLOW
    To prevent buffer overflow, use the width modifier in the format string to
    limit the number of characters read:

        char arr[10];
        scanf("%9s", arr);  // Only reads up to 9 characters, leaving room for
                             // the null terminator.

    This ensures that scanf will read no more than 9 characters, preserving
    space for the null terminator.

FUNCTIONS WITH POINTERS FOR EACH DATA TYPE

    **1. Pointer to int:**
    When working with an integer pointer, you can pass the address of the integer variable to functions.

    Example:
        #include <stdio.h>

        void set_value(int* ptr) {
            *ptr = 42;
        }

        int main() {
            int num;
            set_value(&num);
            printf("num: %d\n", num);  // Output will be 42
            return 0;
        }

    Here, `set_value` takes a pointer to an integer and modifies its value directly using dereferencing (*ptr).

    **2. Pointer to char:**
    Pointers to characters are commonly used for manipulating individual characters or strings.

    Example:
        #include <stdio.h>

        void set_char(char* c) {
            *c = 'A';
        }

        int main() {
            char ch;
            set_char(&ch);
            printf("ch: %c\n", ch);  // Output will be A
            return 0;
        }

    The `set_char` function changes the value of `ch` by dereferencing the pointer `c`.

    **3. Pointer to float:**
    You can pass pointers to floating-point variables, allowing you to manipulate their values.

    Example:
        #include <stdio.h>

        void multiply_by_two(float* ptr) {
            *ptr *= 2.0f;
        }

        int main() {
            float value = 5.5f;
            multiply_by_two(&value);
            printf("value: %.2f\n", value);  // Output will be 11.00
            return 0;
        }

    The `multiply_by_two` function takes a pointer to a float and multiplies the value by 2. This shows how pointers can be used to modify floating-point variables.

    **4. Pointer to double:**
    Similar to float pointers, double pointers allow for the manipulation of double-precision floating-point values.

    Example:
        #include <stdio.h>

        void divide_by_two(double* ptr) {
            *ptr /= 2.0;
        }

        int main() {
            double value = 10.0;
            divide_by_two(&value);
            printf("value: %.2f\n", value);  // Output will be 5.00
            return 0;
        }

    The `divide_by_two` function divides the value of `value` by 2 using the pointer `ptr`.

    **5. Pointer to array (char arr[]):**
    Arrays are always passed as pointers in C, and pointers to arrays can be used to modify the entire array. With `char arr[]`, you’re working with strings as arrays of characters.

    Example:
        #include <stdio.h>

        void initialize_array(char* arr, int size) {
            for (int i = 0; i < size; i++) {
                arr[i] = 'A' + i;  // Initializes with 'A', 'B', 'C', ...
            }
        }

        int main() {
            char arr[5];
            initialize_array(arr, 5);
            for (int i = 0; i < 5; i++) {
                printf("%c ", arr[i]);  // Output will be A B C D E
            }
            return 0;
        }

    Here, the function `initialize_array` modifies each element of the `char arr[]` array by setting them to sequential letters of the alphabet using pointer arithmetic. Since `arr` is already a pointer to the first element, we can directly manipulate the elements inside the array.

SEE ALSO
    printf(3), fgets(3), malloc(3), free(3)

NOTES
    This function is part of the GNU C Library, and its behavior may depend on
    specific implementations. Always validate array sizes and ensure that you
    properly manage memory when working with low-level functions like scanf.
```
