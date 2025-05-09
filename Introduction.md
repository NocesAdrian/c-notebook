# Introduction to c programming language
C is a fast, low-level language used to build operating systems, embedded systems, and robotics. It teaches you how computers really think—through memory, logic, and control. Mastering C is like holding the Divergence Meter of programming: precise, powerful, and foundational.

#### navigation
- [structure](#syntax) 
- [data types](#data-types) 

## Syntax
```cpp
#include <stdio.h>  // standard input output header

void someFunction() {
       //code
}

int main() {
    // code block
    printf("Hello, world!\n");
    return 0;
}

```

## Data types
```cpp
NAME
       data types - C language primitive data types

SYNOPSIS
       int     standard integer type
       long    long integer type
       long long    long long integer type
       short   short integer type
       float   floating-point type
       double  double precision floating-point type
       char    character type
       unsigned int     unsigned integer type
       unsigned long    unsigned long integer type
       unsigned long long    unsigned long long integer type
       unsigned short   unsigned short integer type
       signed int       signed integer type
       signed long      signed long integer type
       signed long long signed long long integer type
       signed short     signed short integer type
       size_t  unsigned type for size values
       ptrdiff_t        signed type for pointer differences

DESCRIPTION
       C provides several primitive data types. These types are the building blocks for variables and constants. They can represent integers, floating-point values, and characters.

       int     A standard integer type. Typically 32-bits wide, it can represent values in the range of:
               -2,147,483,648 to 2,147,483,647 (for a 32-bit system).

       long    A long integer type. On most systems, it is 32 or 64-bits wide:
               For a 32-bit system: -2,147,483,648 to 2,147,483,647
               For a 64-bit system: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

       long long    A type for integers with a wider range than `long`. It is typically 64-bits wide:
                   -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

       short   A short integer type, typically 16-bits wide. It can represent values in the range of:
               -32,768 to 32,767

       float   A single-precision floating-point type, typically represented by 32-bits:
               Range: approximately ±3.4E-38 to ±3.4E+38
               Precision: ~6-7 decimal digits

       double  A double-precision floating-point type, typically represented by 64-bits:
               Range: approximately ±1.7E-308 to ±1.7E+308
               Precision: ~15-16 decimal digits

       char    A type used to represent single characters, typically 8-bits wide:
               Signed: -128 to 127
               Unsigned: 0 to 255

       unsigned int     An unsigned integer type, typically 32-bits wide:
                        0 to 4,294,967,295

       unsigned long    An unsigned long type, typically 32 or 64-bits wide:
                        For a 32-bit system: 0 to 4,294,967,295
                        For a 64-bit system: 0 to 18,446,744,073,709,551,615

       unsigned long long An unsigned type, typically 64-bits wide:
                            0 to 18,446,744,073,709,551,615

       unsigned short   An unsigned short type, typically 16-bits wide:
                        0 to 65,535

       signed int       A signed version of int, it can represent both negative and positive values:
                        -2,147,483,648 to 2,147,483,647 (32-bit system)

       signed long      A signed long integer type, it can represent both negative and positive values:
                        For a 32-bit system: -2,147,483,648 to 2,147,483,647
                        For a 64-bit system: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

       signed long long A signed long long integer type, it can represent both negative and positive values:
                        -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807

       size_t  An unsigned type used to represent sizes of objects:
               Typically, 32-bits on 32-bit systems and 64-bits on 64-bit systems:
               For a 32-bit system: 0 to 4,294,967,295
               For a 64-bit system: 0 to 18,446,744,073,709,551,615

       ptrdiff_t        A signed type used to represent the difference between two pointers:
                        -2,147,483,648 to 2,147,483,647 (for a 32-bit system)

EXAMPLES
       #include <stdio.h>
       
       int main() {
           int a = 10;
           long b = 100000L;
           long long c = 10000000000LL;
           short d = 50;
           float e = 3.14f;
           double f = 2.718281828459045;
           char g = 'A';
           char str[] = "Hello, world!";
           unsigned int h = 255;
           
           printf("%d %ld %lld %hd %.2f %.15f %c %s %u\n", a, b, c, d, e, f, g, str, h);
           return 0;
       }
       
SEE ALSO
       C standard, <stdio.h> (for IO operations)
```
## Constant 
```cpp
.CONSTANT_C(7)                   C Library Manual                  CONSTANT_C(7)

NAME
       constant_c - Writing constants in the C programming language

SYNOPSIS
       #define NAME value
       const type NAME = value;

DESCRIPTION
       Constants in C can be defined in two main ways: using the preprocessor
       directive #define or the const keyword.

   #define
       The #define directive is used to create macro constants. It has no type
       checking and performs a simple textual substitution before compilation.

       Example:
           #define PI 3.14159

       Notes:
           - No memory is allocated.
           - Cannot be debugged easily.
           - Best for compile-time constants and macro definitions.

   const
       The const keyword defines a variable whose value cannot be changed after
       initialization. Unlike #define, const respects C’s type system.

       Example:
           const float pi = 3.14159;

       Notes:
           - Type-safe.
           - Can be stored in memory (RAM or flash).
           - Supports debugging and scope rules.

EXAMPLES
       // Using #define
       #define MAX_BUFFER_SIZE 1024

       // Using const
       const int maxBufferSize = 1024;

       // Better practice: prefer const for type safety

FILES
       Not applicable.

SEE ALSO
       gcc(1), cpp(1), const(5), define(5)
```
