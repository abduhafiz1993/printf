# 0x11. C - printf
>project done in 5 days

![Betty style](https://img.shields.io/badge/betty-style%20guide-purple?style=round-square)

## Learning Objectives
>needed to be [explaied](https://fs.blog/feynman-learning-technique/) after the project.
* [Sectrets of Printf](https://www.academia.edu/10297206/Secrets_of_printf_)

## Authorized functions and macros
* write (man 2 write)
* malloc (man 3 malloc)
* free (man 3 free)
* va_start (man 3 va_start)
* va_end (man 3 va_end)
* va_copy (man 3 va_copy)
* va_arg (man 3 va_arg)

## Compilation

Your code will be compiled this way: `$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c`

   + As a consequence, be careful not to push any c file containing a `main` function in the root directory of your project (you could have a `test` folder containing all your tests files including main functions)
   + the main files will include your `main` header file (`main.h`): `#include main.h`
   + You might want to look at the `gcc` flag `-Wno-format` when testing with your `_printf` and the standard `printf`. Example of test file that you could use:
```c
alex@ubuntu:~/c/printf$ cat main.c 
#include <limits.h>
#include <stdio.h>
#include "main.h"

/**
 * main - Entry point
 *
 * Return: Always 0
 */
int main(void)
{
    int len;
    int len2;
    unsigned int ui;
    void *addr;

    len = _printf("Let's try to printf a simple sentence.\n");
    len2 = printf("Let's try to printf a simple sentence.\n");
    ui = (unsigned int)INT_MAX + 1024;
    addr = (void *)0x7ffe637541f0;
    _printf("Length:[%d, %i]\n", len, len);
    printf("Length:[%d, %i]\n", len2, len2);
    _printf("Negative:[%d]\n", -762534);
    printf("Negative:[%d]\n", -762534);
    _printf("Unsigned:[%u]\n", ui);
    printf("Unsigned:[%u]\n", ui);
    _printf("Unsigned octal:[%o]\n", ui);
    printf("Unsigned octal:[%o]\n", ui);
    _printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    _printf("Character:[%c]\n", 'H');
    printf("Character:[%c]\n", 'H');
    _printf("String:[%s]\n", "I am a string !");
    printf("String:[%s]\n", "I am a string !");
    _printf("Address:[%p]\n", addr);
    printf("Address:[%p]\n", addr);
    len = _printf("Percent:[%%]\n");
    len2 = printf("Percent:[%%]\n");
    _printf("Len:[%d]\n", len);
    printf("Len:[%d]\n", len2);
    _printf("Unknown:[%r]\n");
    printf("Unknown:[%r]\n");
    return (0);
}
alex@ubuntu:~/c/printf$ gcc -Wall -Wextra -Werror -pedantic -std=gnu89 -Wno-format *.c
alex@ubuntu:~/c/printf$ ./printf
Let's try to printf a simple sentence.
Let's try to printf a simple sentence.
Length:[39, 39]
Length:[39, 39]
Negative:[-762534]
Negative:[-762534]
Unsigned:[2147484671]
Unsigned:[2147484671]
Unsigned octal:[20000001777]
Unsigned octal:[20000001777]
Unsigned hexadecimal:[800003ff, 800003FF]
Unsigned hexadecimal:[800003ff, 800003FF]
Character:[H]
Character:[H]
String:[I am a string !]
String:[I am a string !]
Address:[0x7ffe637541f0]
Address:[0x7ffe637541f0]
Percent:[%]
Percent:[%]
Len:[12]
Len:[12]
Unknown:[%r]
Unknown:[%r]
alex@ubuntu:~/c/printf$
```
## Tasks

+ [x] 0\. I'm not going anywhere. You can print that wherever you want to. I'm here and I'm a Spur for life<br/>_ Write a function that produces output according to a format.
   + Prototype: `int _printf(const char *format, ...);`
   + Returns: the number of characters printed (excluding the null byte used to end output to strings)
   + write output to stdout, the standard output stream
   + `format` is a character string. The format string is composed of zero or more directives. See `man 3 printf` for more detail. You need to handle the following conversion specifiers:
     + `c`
     + `s`
     + `%`
   + You don’t have to reproduce the buffer handling of the C library `printf` function
   + You don’t have to handle the flag characters
   + You don’t have to handle field width
   + You don’t have to handle precision
   + You don’t have to handle the length modifiers
+ [x] 1\. Education is when you read the fine print. Experience is what you get if you don't<br/>_ Handle the following conversion specifiers:
     + `d`
     + `i`
   + You don’t have to handle the flag characters
   + You don’t have to handle field width
   + You don’t have to handle precision
   + You don’t have to handle the length modifiers
