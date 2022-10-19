# 0x11. C - printf

![Betty style](https://img.shields.io/badge/betty-style%20guide-purple?style=round-square)

## About

This project is an application of the C programming knowledge that [alx School](https://www.alxafrica.com/) cohort 9 students have learned so far.

The `_printf()` function mimics original `printf()` and takes a format string and optional arguments and produce a formatted sequence of characters for output. The format string contains zero or more directives, which are either literal characters for output or encoded conversion specifications that describe how to format an argument in the output.

## Requirement

* All files will be compiled on Ubuntu 20.04 LTS
* Programs and functions will be compiled with gcc 4.8.4 using flags -Wall -Werror -Wextra and -pedantic
* Code must follow the [Betty](https://github.com/holbertonschool/Betty/wiki) style
* Global variables are not allowed
* Authorized functions and macros:
  * ```write``` (man 2 write)
  * ```malloc``` (man 3 malloc)
  * ```free``` (man 3 free)
  * ```va_start``` (man 3 va_start)
  * ```va_end``` (man 3 va_end)
  * ```va_copy``` (man 3 va_copy)
  * ```va_arg``` (man 3 va_arg)

## Mandatory Tasks

* [x] Write function that produces output with conversion specifiers ```c```, ```s```, and ```%```.

* [x] Handle conversion specifiers ```d```, ```i```.

## Advanced Tasks

* [x] Handle conversion specifier ```b```.

* [x] Handle conversion specifiers ```u```, ```o```, ```x```, ```X```.
* [x] Use a local buffer of 1024 chars in order to call write as little as possible.
* [x] Handle conversion specifier ```S```.
* [x] Handle conversion specifier ```p```.
* [x] Handle flag characters ```+```, space, and ```#``` for non-custom conversion specifiers.
* [ ] Handle length modifiers ```l``` and ```h``` for non-custom conversion specifiers.
* [ ] Handle the field width for non-custom conversion specifiers.
* [ ] Handle the precision for non-custom conversion specifiers.
* [ ] Handle the ```0``` flag character for non-custom conversion specifiers.
* [x] Handle the custom conversion specifier ```r``` that prints the reversed string.
* [x] Handle the custom conversion specifier ```R``` that prints the rot13'ed string.
* [ ] All above options should work well together.

## Prototype

`int _printf(const char *, ...);`

## Compilation

`gcc -Wall -Wextra -Werror -pedantic -std=gnu89 -Wno-format *.c`

## How To Use

The `main.h` header must be included before you can use the function. The `_printf` function returns the number of characters that were printed to the stdout stream.

```c
#include "main.h"
int main(void)
{
  int n = _printf("i have %d%s\n", 100, "cars.");
  return (0);
}
```

Output: `i have 100 cars.`

## File Descriptions

**_printf.c**

* contains the  function ```_printf```, which uses the prototype ```int_printf(const char *format, ...);```. The format string is composed of zero or more directives. **_printf**will return the number of characters printed (excluding the null byte used to end output to strings) and will write output to**stdout**, the standard output stream.

**main.h**

*contains all function prototypes used for ```_printf```.

**print....c**

* contains all function of each specifier used for ```_printf```.
* all function have its own description inside the file.

**get_print.c**

* selects the right printing function for ```_printf```.

**get_flag.c**

* turns on flags for ```_printf```.

**converter.c**

* converts number and base into string.

## Directory Descriptions

**tests**

* contains the test cases for ```_printf```.

## Authors

[Bekalu Endrias](https://github.com/bekalue) | [Favour Onyeaso](https://github.com/OnyeasoF)
