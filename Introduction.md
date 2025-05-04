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
           unsigned int h = 255;
           
           printf("%d %ld %lld %hd %.2f %.15f %c %u\n", a, b, c, d, e, f, g, h);
           return 0;
       }
       
SEE ALSO
       C standard, <stdio.h> (for IO operations)
```
